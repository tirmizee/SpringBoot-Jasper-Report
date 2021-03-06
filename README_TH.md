# SpringBoot-Jasper-Report

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; JasperReport เป็น library ทำรายงานโอเพ่นซอร์สที่ได้รับความนิยมมากสำหรับ Java โดยสามารถออกเป็นเอกสารได้หลากหลายรูปแบบเช่น Pdf, Csv Exel Docs


### Lifecycle of JasperReports

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ในการที่เราจะออกรายงานได้มีขั้นตอนต่างๆดังนี้

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/95425186-16e39c00-096e-11eb-9d12-17fa2726ce66.png" width="600">
</p>



#### 1. Design (.jrxml)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ขั้นตอนแรกคือการสร้างไฟล์ .jrxml เป็นข้อมูลรูปแบบ xml อย่างง่าย ซึ่งจะกำหนดโครงร่างรายงานของเราว่าจะมีหน้าตารายงานเป็นยังไงบ้าง คล้ายๆกับไฟล์ html ที่กำหนดหน้าตาของ web เพียงแต่เราไม่ได้เอาไฟล์ jrxml ไปใช้โดยโดยตรงเหมือน html จะต้องผ่านขั้นตอนต่างๆของ Jasper ก่อน ซึ่งจะมี Tool สำหรับสร้างไฟล์ .jrxml เช่น JasperSoft หรือ IReport

#### 2. Compile (.jasper)

#### 3. Execution (.jrprint)

#### 4. Export (.pdf, .xls, .docs)

### Report Bands

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Bands คือ Section การแสดงผลของ Report ประกอบไปด้วยดังนี้

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/91743149-92209800-ebe1-11ea-9bce-00e092d059a2.png" width="500">
</p>

 - #### Title
         คือส่วนที่พิมพ์ขึ้นเพียงครั้งเดียวที่จุดเริ่มต้นของรายงาน และสามารถพิมพ์ในหน้าแยกต่างหากได้ 
         โดยตั้งค่าแอตทริบิวต์ isTitleNewPage = "true"
 - #### Page Header
         คือส่วนหัวเรื่อง(Header)ที่แสดงในจุดเริ่มต้นของแต่ล่ะหน้า ไม่รวมกับ Title และ Summary หาก Report เรามี 10 หน้า 
         มันก็จะแสดงส่วนหัวเรื่องทั้ง 10 หน้า isSummaryWithPageHeaderAndFooter="false"
 - #### Column Header
         คือส่วนหัวของคอลัมน์จะแสดงก่อนส่วนรายละเอียดในแต่ละหน้า
 - #### Detail
         คือส่วนรายละเอียดที่จะแสดงในแต่ล่ะรายการจากแหล่งข้อมูล(Data Source)
 - #### Group Header
 - #### Group Footer
 - #### Column Footer
         คือส่วนที่จะปรากฏด้านล่างส่วนรายละเอียด(Detail)ในแต่ละหน้า สามารถเปลี่ยนเป็นส่วนรายละเอียดสุดท้ายได้โดยการตั้งค่าแอตทริบิวต์
         isFloatColumnFooter="true"
 - #### Page Footer
         คือส่วที่แสดงในจุดท้ายสุดของแต่ล่ะหน้า
 - #### Last Page Footer
 - #### Summary
 - #### Background
 - #### No Data
โดยเราสามารถเลือกใช้ได้ตามที่จำเป็น

### Element

### Parameters

พารามิเตอร์คือตัวแปร Object ที่ถูกส่งเข้ามาเพื่อทำการแสดงข้อมูลในรายงาน ซึ่งสามารถประกาศได้ดังนี้

    <parameter name="ParameterName" class="java.lang.String" />
    
- #### name attribute

name attribute คือชื่อของ parameter เพื่อใช้ในการอ้างถึง

- #### class  attribute

class attribute คือชื่อ class ของ parameter หากไม่ระบุจะมีค่า defualt คือ <b>java.lang.String</b>

การอ้างถึง Parameters ใช้เครื่องหมาย  $P{} ตามด้วยชื่อ parameter ดังนี้ $P{ParameterName} 

### Default Parameters

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; JasperReports มีพารามิเตอร์ในตัว (เป็นพารามิเตอร์ภายในของเครื่องมือสร้างรายงาน) ที่เราอาจอ่านได้เท่านั้นไม่สามารถแก้ไขได้ พารามิเตอร์ที่สำคัญที่สุดคือ "REPORT_CONNECTION" ซึ่งเก็บการเชื่อมต่อ JDBC

| Parameter | Description |
| ------------- | ---------------|
| REPORT_CONTEXT |  |
| REPORT_PARAMETERS_MAP |  |
| JASPER_REPORT |  |
| REPORT_CONNECTION | JDBC connection ที่ส่งไปยังรายงานเพิ่อทำการสร้าง SQL Query ในตัวรายงาน|
| REPORT_MAX_COUNT | ใช้เพื่อจำกัดจำนวน record ที่แสดงในรายงาน หากไม่ระบุ no limit  |
| REPORT_DATA_SOURCE | Data source ที่ใช้โดยรายงาน(JRDataSource) เมื่อไม่ได้ใช้ JDBC connection |
| REPORT_SCRIPTLET |  |
| REPORT_LOCALE |  |
| REPORT_RESOURCE_BOUNDLE |  |
| REPORT_TIME_ZONE |  |
| REPORT_FORMAT_FACTORY |  |
| REPORT_CLASS_LOADER |  |
| REPORT_URL_HANDLER_FACTORY |  |
| REPORT_FILE_RESOLVER |  |
| REPORT_TEMPLATES |  |
| SORT_FIELDS | ใช้เพื่อเรียงลำดับตามชื่อ Field ที่ระบุ สามาถเลือกการเรียงลำดับจากมากไปน้อยหรือน้อยไปมากได้ |
| FILTER |  |
| REPORT_VIRTUALIZER |  |
| IS_IGNORE_PAGINATION |  |

### Expressions 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Expressions เป็นคุณสมบัติหลักของ JasperReports เป็นกลไกที่ช่วยในการจัดการและแสดงข้อมูลรายงาน สามารถใช้เพื่อประกาศ
ตัวแปรที่ทำการคำนวณต่างๆ ใช้เพื่อจัดกลุ่มข้อมูลในรายงาน หรือปรับแต่งลักษณะของ objects รายงานเพิ่มเติม ซึ่งใน Template ของรายงานมีหมากหลาย Element ที่กำหนด Expression ได้รวมถึง

- variableExpression
- initialValueExpression
- groupExpression
- printWhenExpression
- imageExpression
- textFieldExpression
- ete...

#### Expression Syntax

Expression จะไม่มีประโยชน์หากไม่มีการอ้างอิงถึง Parameter, Field หรือตัวแปร(variables)อื่นๆในรายงาน

- #### $F{FIELD}

      อ้างถึงฟิลด์ชื่อ FIELD

- #### $V{VAR}

      อ้างถึงตัวแปรชื่อ VAR

- #### $P{PARAM}

      อ้างถึงพารามิเตอร์ชื่อ PARAM 

- #### $P!{PARAM}

      อ้างถึงพารามิเตอร์ชื่อ PARAM 

- #### $X{}


- #### $R{keyName}

      ดึงข้อความสตริง โดยใช้โดยใช้คีย์ keyName จาก Resource bundle ที่ส่งเข้ามา
 
#### Conditional Expressions
 
 (condition) ? (statement if true) : (statement if false)
 
#### Expressions Calculator 
 
#### Image Expression Type

- java.lang.String 

- java.io.File

- java.net.URL

- java.io.InputStream

- java.awt.Image

- net.sf.jasperreports.engine.JRRenderable

#### Data Source Type

- JDBC

- Java Bean

- XML, CSV, JSON 

- Empty

### Scriptlets 

### Example Filter

คลิกขวาที่ไฟล์หลักและเลือก "Dataset and Query"

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/90112516-4a44e880-dd7a-11ea-901c-70cb12a2a193.JPG" width="500">
</p>

ในแท๊ป Filter expression ระบุเงื่อนไขที่ต้องการ

<p align="center">
  <img src="https://user-images.githubusercontent.com/15135199/90113248-41084b80-dd7b-11ea-8215-f8e3304dfa0d.JPG" width="500">
</p>
