# SpringBoot-Jasper-Report

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; JasperReport เป็น library ทำรายงานโอเพ่นซอร์สที่ได้รับความนิยมมากสำหรับ Java โดยสามารถออกเป็นเอกสารได้หลากหลายรูปแบบเช่น Pdf, Csv Exel Docs


### Lifecycle of JasperReports

![chapter2_1](https://user-images.githubusercontent.com/15135199/89733503-25056100-da80-11ea-9097-7324beb2fb61.png)


CR : http://refermycode.com/jaspertutorial/chapter-2-life-cycle-of-jasper-report/

### Report Bands

 - #### Title
         คือส่วนที่สร้างขึ้นเพียงครั้งเดียวที่จุดเริ่มต้นของรายงาน
 - #### Page Header

### Default Parameters

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; JasperReports มีพารามิเตอร์ในตัว (เป็นพารามิเตอร์ภายในของเครื่องมือสร้างรายงาน) ที่เราอาจอ่านได้เท่านั้นไม่สามารถแก้ไขได้ พารามิเตอร์ที่สำคัญที่สุดคือ "REPORT_CONNECTION" ซึ่งเก็บการเชื่อมต่อ JDBC

| Parameter | Description |
| ------------- | ---------------|
| REPORT_CONTEXT |  |
| REPORT_PARAMETERS_MAP |  |
| JASPER_REPORT |  |
| REPORT_CONNECTION |  JDBC connection ส่งไปยังรายงานเพิ่อทำการสร้าง SQL Query ในตัวรายงาน|
| REPORT_MAX_COUNT | ใช้เพื่อจำกัดจำนวน record ที่แสดงในรายงาน หากไม่ระบุ no limit  |
| REPORT_DATA_SOURCE | Data source ที่ใช้โดยรายงานเมื่อไม่ได้ใช้ JDBC connection |
| REPORT_SCRIPTLET |  |
| REPORT_LOCALE |  |
| REPORT_RESOURCE_BOUNDLE |  |
| REPORT_TIME_ZONE |  |
| REPORT_FORMAT_FACTORY |  |
| REPORT_CLASS_LOADER |  |
| REPORT_URL_HANDLER_FACTORY |  |
| REPORT_FILE_RESOLVER |  |
| REPORT_TEMPLATES |  |
| SORT_FIELDS |  |
| FILTER |  |
| REPORT_VIRTUALIZER |  |
| IS_IGNORE_PAGINATION |  |

#### Image Expression

- java.lang.String 

- java.io.File

- java.net.URL

- java.io.InputStream

- java.awt.Image

- net.sf.jasperreports.engine.JRRenderable

### Example Filter

คลิกขวาที่ไฟล์หลักและเลือก "Dataset and Query"

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/90112516-4a44e880-dd7a-11ea-901c-70cb12a2a193.JPG" width="500">
</p>

ในแท๊ป Filter expression ระบุเงื่อนไขที่ต้องการ

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/90113248-41084b80-dd7b-11ea-8215-f8e3304dfa0d.JPG" width="500">
</p>
