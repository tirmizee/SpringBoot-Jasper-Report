# SpringBoot-Jasper-Report

### Lifecycle of JasperReports

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/95425186-16e39c00-096e-11eb-9d12-17fa2726ce66.png" width="600">
</p>

### Example 

#### export report to image

    ByteArrayOutputStream byteArrayOutputStream = new ByteArrayOutputStream();
    BufferedImage bufferedImage  = (BufferedImage) JasperPrintManager.printPageToImage(jasperPrint, 0, 2.0f);
    ImageIO.write(bufferedImage, "PNG", byteArrayOutputStream);   

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/95680392-91791980-0c03-11eb-86f6-e1376407d410.png" width="300">
</p>

#### export report to docx

contentTypr : application/vnd.openxmlformats-officedocument.wordprocessingml.document

		JasperPrint jasperPrint = ...;
		ByteArrayOutputStream baos = new ByteArrayOutputStream(); 
		
		SimpleDocxReportConfiguration configuration = new SimpleDocxReportConfiguration();
		
		JRDocxExporter docxExporter = new JRDocxExporter();
		docxExporter.setExporterInput(new SimpleExporterInput(jasperPrint));
		docxExporter.setExporterOutput(new SimpleOutputStreamExporterOutput(baos));
		docxExporter.setConfiguration(configuration);
		docxExporter.exportReport();
