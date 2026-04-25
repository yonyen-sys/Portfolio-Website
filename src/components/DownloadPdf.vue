<template>
  <button class="button button-secondary" @click="exportPdf" :disabled="isExporting" aria-label="Download resume as PDF">
    {{ isExporting ? 'Preparing PDF...' : 'Download PDF' }}
  </button>
</template>

<script>
import jsPDF from 'jspdf';
import html2canvas from 'html2canvas';

export default {
  name: 'DownloadPdf',
  props: {
    targetRef: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      isExporting: false
    };
  },
  methods: {
    async exportPdf() {
      let element = document.getElementById(this.targetRef);
      if (!element && this.targetRef.startsWith('.')) {
        element = document.querySelector(this.targetRef);
      }
      if (!element) {
        element = this.$root.$refs[this.targetRef] || this.$parent.$refs[this.targetRef];
      }
      if (!element) {
        alert('Unable to access the resume content for PDF export.');
        return;
      }

      this.isExporting = true;
      const clone = element.cloneNode(true);
      clone.style.position = 'absolute';
      clone.style.left = '0';
      clone.style.top = '-9999px';
      clone.style.width = '800px';
      clone.style.opacity = '1';
      clone.style.display = 'block';
      clone.style.visibility = 'visible';
      clone.style.pointerEvents = 'none';
      clone.style.zIndex = '9999';
      clone.style.backgroundColor = '#ffffff';
      document.body.appendChild(clone);

      try {
        const canvas = await html2canvas(clone, {
          scale: 2,
          backgroundColor: '#ffffff',
          useCORS: true,
          scrollY: 0,
          width: clone.offsetWidth,
          windowWidth: clone.offsetWidth
        });

        const imgData = canvas.toDataURL('image/png');
        const pdf = new jsPDF({ orientation: 'portrait', unit: 'pt', format: 'a4' });
        const pageWidth = pdf.internal.pageSize.getWidth();
        const pageHeight = pdf.internal.pageSize.getHeight();
        const margin = 20;
        const imgProps = pdf.getImageProperties(imgData);
        const pdfWidth = pageWidth - margin * 2;
        let pdfHeight = (imgProps.height * pdfWidth) / imgProps.width;

        const maxHeight = pageHeight - margin * 2;
        let renderWidth = pdfWidth;
        let renderHeight = pdfHeight;
        if (renderHeight > maxHeight) {
          const scale = maxHeight / renderHeight;
          renderWidth *= scale;
          renderHeight = maxHeight;
        }

        pdf.addImage(imgData, 'PNG', margin, margin, renderWidth, renderHeight);
        pdf.save('YonYen_Final.pdf');
      } catch (error) {
        console.error('PDF export failed:', error);
        alert('PDF export failed. Please try again.');
      } finally {
        document.body.removeChild(clone);
        this.isExporting = false;
      }
    }
  }
};
</script>

<style scoped>
.button-secondary {
  background: white;
  border: 1px solid rgba(37, 99, 235, 0.16);
  color: var(--primary);
}

.button-secondary:disabled {
  opacity: 0.65;
  cursor: not-allowed;
}
</style>
