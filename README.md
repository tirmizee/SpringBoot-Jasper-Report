# SpringBoot-Jasper-Report

### Example 

#### export report to image

    ByteArrayOutputStream byteArrayOutputStream = new ByteArrayOutputStream();
    BufferedImage bufferedImage  = (BufferedImage) JasperPrintManager.printPageToImage(jasperPrint, 0, 2.0f);
    ImageIO.write(bufferedImage, "PNG", byteArrayOutputStream);   

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/95680392-91791980-0c03-11eb-86f6-e1376407d410.png" width="300">
</p>

