# To Do List Calendar + LINE OA Notification (Google Apps Script + Bootstrap 5)

ระบบบริหารจัดการงานและปฏิทินส่วนตัว พร้อมระบบแจ้งเตือนผ่าน LINE Official Account (Flex Message) อัตโนมัติ

## 🚀 ขั้นตอนการติดตั้งบน Google Apps Script
1. สร้าง **Google Sheet** ใหม่ขึ้นมา
2. ไปที่เมนู **ส่วนขยาย (Extensions)** > **Google Apps Script**
3. คัดลอกโค้ดจากไฟล์ `Code.gs`, `Index.html`, `Javascript.html` และ `Stylesheet.html` ไปวางในโปรเจกต์ GAS โดยตั้งชื่อไฟล์ให้ตรงกัน
4. รันฟังก์ชัน `setupDatabase()` หนึ่งครั้ง เพื่อสร้าง Sheets และข้อมูลเริ่มต้นอัตโนมัติ
5. รันฟังก์ชัน `setupNotificationTrigger()` เพื่อเปิดใช้งานระบบแจ้งเตือนอัตโนมัติทุกๆ 5 นาที
6. กด **เผยแพร่ (Deploy)** > **การปรับใช้ครั้งใหม่ (New deployment)** เลือกประเภทเป็น **แอปเว็บ (Web app)**
   - Execute as: `Me (อีเมลของคุณ)`
   - Who has access: `Anyone (ทุกคน)`
7. นำ URL ที่ได้ไปใช้งานผ่าน Web Browser

## 💬 วิธีการตั้งค่า LINE OA
1. สมัครใช้งาน LINE Official Account และเปิดใช้งาน **Messaging API** บน LINE Developers Console
2. คัดลอก **Channel Access Token** มาใส่ในตัวแปร `LINE_CHANNEL_ACCESS_TOKEN` ในไฟล์ `Code.gs`
3. นำ **LINE User ID** ของผู้ใช้มาบันทึกลงในคอลัมน์ `LineUserId` ใน Sheet `Users` เพื่อรับข้อความแจ้งเตือน Flex Message
