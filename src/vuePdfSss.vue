<style src="./annotationLayer.css"></style>
<script>

	import componentFactory from './componentFactory'
	import pdfjsWrapper from './pdfjsWrapper'

	var PDFJS = require('pdfjs-dist');
	var pdfjsWorker = require('pdfjs-dist/build/pdf.worker.entry');

	if ( process.env.VUE_ENV !== 'server' ) {

		PDFJS.GlobalWorkerOptions.workerSrc = pdfjsWorker;
	}

	var component = componentFactory(pdfjsWrapper(PDFJS));
	component.PDFJS = PDFJS;

	export default component;

</script>