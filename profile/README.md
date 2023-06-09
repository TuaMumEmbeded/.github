# **โครงงานพัฒนาระบบดูแลผู้ป่วยติดเตียงที่บ้าน <br/> (Home Care for Bedridden Patients)**

โครงงานนี้เป็นส่วนหนึ่งของรายวิชา 01204322 ระบบฝังตัว (Embedded Systems) ภาคปลาย ปีการศึกษา 2565 หมู่ 1

ภาควิชาวิศวกรรมคอมพิวเตอร์ คณะวิศวกรรมศาสตร์ มหาวิทยาลัยเกษตรศาสตร์

> ## **MEMBERS**

- _6310503464_ - พลอยพัชรินทร์ พูลสวัสดิ์กิติกูล < _Backend Developer_ >
- _6310503596_ - อติกานต์ อนุสุทธิ์ < _Hardware Developer_ >
- _6310503600_ - อภิญญา สุทธิโสภาอาภรณ์ < _Frontend Developer_ >
- _6310506471_ - กันตธร วุฒิวิริยะ < _Frontend Developer_ >
- _6310506501_ - จีรพัฒน์ ฉิมมา < _Hardware Developer_ >
- _6310506820_ - สุนิษา อรรควงษ์ < _Backend Developer_ >

> ## **BACKGROUND**

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ในปัจจุบัน มีข่าวเกี่ยวกับผู้ป่วยติดเตียงที่ไม่ได้รับการดูแลอย่างเต็มที่จำนวนมาก อันเนื่องมาจากหลายปัจจัย เช่น ปัจจัยด้านการบริหารเวลา บุคคลในครอบครัวส่วนใหญ่ไม่มีเวลาดูแล เพราะต้องใช้เวลาในการทำงานหาเลี้ยงครอบครัว หรือปัญหาด้านการดูแล ที่มีความยากลำบาก เนื่องจากในบางครั้ง ผู้ดูแลอาจต้องใช้เวลาในการทำกิจกรรมอื่นๆ ด้วย ทำให้ผู้ป่วยติดเตียงไม่ได้รับการดูแลอย่างเต็มที่เท่าที่ควร เราเลยคิดค้นระบบ **Home Care for Bedridden Patients** เหมาะสำหรับครอบครัวที่ต้องการดูแลผู้ป่วยติดเตียงที่บ้าน โดยระบบจะมีสิ่งอำนวยความสะดวกต่างๆ มากมายให้ทั้งผู้ป่วย และผู้ดูแลใช้ ระบบนี้จะทำให้การบริหารเวลาของผู้ดูแลทำได้ง่ายมากขึ้น ลดความกังวลกับสิ่งที่อาจจะเกิดขึ้นกับผู้ป่วยได้ในระดับหนึ่ง อีกทั้งผู้ป่วยยังได้มีเวลาส่วนตัวในการทำกิจกรรมที่อยากทำอีกด้วย

> ## **FEATURES**

### **ส่วนของผู้ป่วย (2 คน)**

- ผู้ป่วยแต่ละคน จะมีถุงมือซึ่งติดเซ็นเซอร์ตรวจจับการโค้งงอของนิ้วมือ (Flex Sensor) ให้ผู้ป่วยใช้สำหรับเรียกผู้ดูแล โดยแบ่งเป็น 3 กรณี คือ หิว, ต้องการเข้าห้องน้ำ และต้องการความช่วยเหลือเร่งด่วน
- บริเวณรอบเตียงของผู้ป่วยแต่ละคน จะมีการติดเซ็นเซอร์วัดระยะทาง (Ultrasonic Sensor) ใช้สำหรับตรวจจับการตกเตียงของผู้ป่วยแต่ละคน
- มี Micropiano ให้สำหรับผู้ป่วยเล่น เพื่อคลายเครียด

### **ส่วนของผู้ดูแล (1 คน)**

- มีไฟ LED แสดงผลการเรียกจากผู้ป่วยทั้ง 2 คน
- มี Buzzer สำหรับเตือนในกรณีเกิดเหตุการณ์ผู้ป่วยตกเตียง
- มีไฟ LED แสดงสถานะการเล่น Micropiano ของผู้ป่วยทั้ง 2 คน
- มี Web Page สำหรับแสดงผลลัพธ์ทุกอย่าง เช่น สถานะการเรียก สถานะการเล่น Micropiano เป็นต้น

> ## **TECHNIQUES**

### **ส่วนของผู้ป่วย (2 บอร์ด)**

- ใช้ Flex Sensor 2 ชิ้นต่อ 1 บอร์ด โดย Flex Sensor 1 ชิ้นต่อ 1 นิ้วมือ ใช้ติดกับถุงมือนิ้วกลางและนิ้วนาง Flex Sensor จะให้ค่า Analog เมื่อเกิดการงอนิ้ว ค่าที่ได้จะเปลี่ยนแปลง จากนั้นนำค่าของ Flex Sensor ที่ได้ ไปใช้ในการตั้งเงื่อนไขการติดดับของไฟ LED โดยแบ่งเป็น 3 กรณี
  - กรณีที่ 1 หิว > ให้งอนิ้วนางลง แล้วไฟ LED สีเขียวจะติด
  - กรณีที่ 2 ต้องการเข้าห้องน้ำ > ให้งอนิ้วกลางลง แล้วไฟ LED สีเหลืองจะติด
  - กรณีที่ 3 ต้องการความช่วยเหลือเร่งด่วน > ให้งอนิ้วกลางและนิ้วนางลงพร้อมกัน แล้วไฟ LED สีม่วงจะติด
- ใช้ Ultrasonic sensor 2 ชิ้นต่อ 1 บอร์ด โดย Ultrasonic Sensor จะให้ค่าระยะทางจากวัตถุถึง Sensor จากนั้นนำค่าที่ได้ไปใช้ในการตั้งเงื่อนไขการติดดับของไฟ LED และ Buzzer โดยเมื่อระยะทางที่วัดได้มีค่าอยู่ในช่วงที่กำหนดจะทำให้ไฟ LED สีแดงติดและ Buzzer ส่งเสียงเตือน
- ส่งข้อมูลสถานะของไฟ LED ทั้งหมดและสถานะของ Buzzer ไปยังบอร์ดของผู้ดูแล โดยใช้ Library `esp_now.h`

### **Micropiano (2 บอร์ด)**

- สำหรับการแสดงผลทาง Buzzer เราใช้ฟังก์ชัน `ledcWriteTone` และ `ledcWriteNote` ในการแสดงผล
- Micropiano 1 บอร์ด จะมีไฟ LED สีม่วงและปุ่มกดอย่างละ 8 อันสำหรับเล่นโน้ตดนตรี โดยเรียงโน้ตจาก C3 ไปจนถึง C4 เรียงจากซ้ายไปขวา ตามลำดับ และมีปุ่มกด 3 อันสำหรับเลือกเพลง 3 เพลง โดยมีวิธีการเล่น 2 วิธี คือ
  - วิธีที่ 1 กดที่ปุ่มกดสำหรับเล่นโน้ตดนตรีได้เลย แล้วจะเกิดเสียงโน้ตนั้นๆ ขึ้น ลักษณะเหมือนเปียโนทั่วไป
  - วิธีที่ 2 กดที่ปุ่มกดสำหรับเลือกเพลง หลังจากกดเลือกเพลงแล้ว จะมีไฟ LED ติดตามโน้ตของเพลงนั้นๆ ผู้เล่นสามารถกดที่ปุ่มกดสำหรับเล่นโน้ตดนตรีตามแสงไฟ LED ที่ขึ้น และเมื่อกดแล้วจะเกิดเสียงโน้ตนั้นๆ ขึ้น (ประยุกต์ใช้หลักการ Multitasking)
- ส่งข้อมูลสถานะการเล่นไปยังบอร์ดของผู้ดูแล โดยใช้ Library `esp_now.h`

### **ส่วนของผู้ดูแล (1 บอร์ด)**

- รับข้อมูลจากส่วนของผู้ป่วย (2 บอร์ด) และ Micropiano (2 บอร์ด) โดยใช้ Library `esp_now.h` จากนั้นนำค่าสถานะที่ได้ มาแสดงผลที่บอร์ดส่วนของผู้ดูแลด้วย โดยผลลัพธ์ที่แสดง มีดังนี้
  - ผู้ป่วยกำลังเล่น Micropiano > ไฟ LED สีน้ำเงินติด
  - ผู้ป่วยหิว > ไฟ LED สีเขียวติด
  - ผู้ป่วยต้องการเข้าห้องน้ำ > ไฟ LED สีเหลืองติด
  - ผู้ป่วยต้องการความช่วยเหลือเร่งด่วน > ไฟ LED สีม่วงติด
  - ผู้ป่วยตกเตียง > ไฟ LED สีแดงติดและ Buzzer ส่งเสียงเตือน

### **การเชื่อมข้อมูลกับ Backend และ Frontend (1 บอร์ด)**

- รับข้อมูลสถานะทั้งหมดจากบอร์ดของผู้ดูแลโดยใช้ Library `esp_now.h` จากนั้นใช้ Library `HTTPClient.h` และ `ArduinoJson.h` ในการส่งข้อมูลสถานะทั้งหมดไปยัง Server
- หน้า Web Page แสดงวันที่, ชื่อผู้ป่วย และสถานะตามไฟ LED ข้างต้น

> ## **HARDWARE**

- NodeMCU ESP-WROOM-32S [6 ชิ้น]
- เซ็นเซอร์ตรวจจับการโค้งงอ Flex Sensor RFP 2.2 inch [4 ชิ้น]
- เซ็นเซอร์วัดระยะทาง Ultrasonic Module HC-SR04P [4 ชิ้น]
- Active Buzzer Module [4 ชิ้น]
- Active Buzzer 12V [2 ชิ้น]
- Micro Switch Button + Tact Cap 12x12x7.3 mm [22 ชิ้น]
- LED สีม่วง 5mm [20 ชิ้น]
- LED สีน้ำเงิน 5mm [2 ชิ้น]
- LED สีเขียว 5mm [4 ชิ้น]
- LED สีแดง 5mm [4 ชิ้น]
- LED สีเหลือง 5mm [4 ชิ้น]
- ตัวต้านทาน 220 Ohm [34 ชิ้น]
- ตัวต้านทาน 10k Ohm [8 ชิ้น]
- Breadboard [8 ชิ้น]

> ## **DEVELOPMENT TOOLS**

- **Hardware**
  - Language : C, C++
  - Software : Arduino IDE
  - Library : `Wire.h`, `WiFi.h`, `esp_now.h`, `DebouncedSwitch.h`,`HTTPClient.h`, `ArduinoJson.h`
- **Backend**
  - Language : Go
  - Framework : Gin
  - Server : Heroku
- **Frontend**
  - Language : JavaScript, HTML, CSS
  - Framework : React, Bootstrap
  - Design tool : Figma (สามารถดูได้ที่ [UX/UI Design](https://kasets.art/8bziKR))

> ## **PROPERTIES**

|     ฝ่าย     | ชื่อไฟล์          | รายละเอียด                                                                            |
| :----------: | ----------------- | ------------------------------------------------------------------------------------- |
| **Hardware** | `MiniPiano_1.ino` | ไฟล์เกมเปียโนสำหรับผู้ป่วยคนที่ 1                                                     |
|              | `MiniPiano_2.ino` | ไฟล์เกมเปียโนสำหรับผู้ป่วยคนที่ 2                                                     |
|              | `Patient_1.ino`   | แสดงค่าสถานะต่างๆ ของผู้ป่วยคนที่ 1                                                   |
|              | `Patient_2.ino`   | แสดงค่าสถานะต่างๆ ของผู้ป่วยคนที่ 2                                                   |
|              | `Server.ino`      | ส่งข้อมูลจากบอร์ดของผู้ดูแลไปยัง Backend เพื่อนำขึ้นหน้า Web ต่อไป                    |
|              | `pitches.h`       | แสดงค่าความถี่ของตัวโน้ตดนตรีต่างๆที่จะใช้แสดงผลโดย Buzzer                            |
|              | <br>              |                                                                                       |
| **Backend**  | `configs`         | จัดการเชื่อมต่อกับ Database                                                           |
|              | `controllers`     | ควบคุมจัดการข้อมูลใน Database                                                         |
|              | `models`          | เป็น Data structure ที่ใช้จัดเก็บใน Database                                          |
|              | `responses`       | เป็น Data response ที่ใช้ตอบกลับ Client                                               |
|              | `routes`          | กำหนด route ของ API                                                                   |
|              | `main.go`         | กำหนดการทำงานของโปรแกรมทั้งหมด                                                        |
|              | <br>              |                                                                                       |
| **Frontend** | `app.jsx`         | ดึงข้อมูลผู้ป่วยจาก Backend และ render ไฟล์ component ของหน้าเว็ปต่างๆ มารวมกัน       |
|              | `App.css`         | ไฟล์โครงสร้างการตกแต่งหน้า Web ทั้งหมด                                                |
|              | `acivity.jsx`     | แสดงผลสถานะการเล่นเปียโนของผู้ป่วย                                                    |
|              | `alert.jsx`       | แสดงสถานะความต้องการในการ เข้าห้องน้ำ หิว เรียกผู้ดูแล และ แสดงสถานะหากผู้ป่วยตกเตียง |
|              | `header.jsx`      | แสดงวันที่และเวลา                                                                     |
|              | `patients.jsx`    | แสดง ชื่อ เพศ และ อายุ ของผู้ป่วย                                                     |

> ## **Video Presentation สามารถดูได้ที่ → [youtu.be/Lt0JppcsTvc](https://youtu.be/Lt0JppcsTvc)**
