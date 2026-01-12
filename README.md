# Library Management System - Layered Architecture

## 📋 Project Information
- **Student Name:** [นางสาวดาวประกาย เสาร์สิงห์]
- **Student ID:** [67543210027-8]
- **Course:** ENGSE207 Software Architecture

## 🏗️ Architecture Style
Layered Architecture (3-tier)

## 📂 Project Structure
src/
├── presentation/
│ ├── routes/ # จัดการเส้นทาง API
│ ├── controllers/ # จัดการ HTTP Request/Response
│ └── middlewares/ # Error Handling และ Middleware
├── business/
│ ├── services/ # Business Logic ของระบบ
│ └── validators/ # ตรวจสอบความถูกต้องของข้อมูล
└── data/
├── repositories/ # การเข้าถึงฐานข้อมูล
└── database/ # การเชื่อมต่อ SQLite

## 🎯 Refactoring Summary

### ปัญหาของ Monolithic (เดิม):
-โค้ดทั้งหมดอยู่ในไฟล์เดียว ทำให้ไฟล์มีขนาดใหญ่และอ่านยาก
-Business Logic ปะปนกับ HTTP และ Database Logic
-การแก้ไขโค้ดส่วนหนึ่งอาจกระทบทั้งระบบ
-ยากต่อการบำรุงรักษาและขยายระบบ
-การทดสอบแต่ละส่วนทำได้ยาก

### วิธีแก้ไขด้วย Layered Architecture:
-แยกความรับผิดชอบของโค้ดออกเป็น Layer 
-Controller ทำหน้าที่รับ–ส่งข้อมูลผ่าน HTTP เท่านั้น
-Service จัดการ Business Logic และกฎของระบบ
-Repository จัดการการเข้าถึงฐานข้อมูล
-ลดการพึ่งพาซึ่งกันและกันระหว่างส่วนต่าง ๆ

### ประโยชน์ที่ได้รับ:
-โค้ดอ่านง่าย เป็นระเบียบ และดูเป็นมืออาชีพ
-แก้ไขหรือเพิ่มฟีเจอร์ได้ง่าย
-ลดผลกระทบเมื่อมีการเปลี่ยนแปลงโค้ด
-รองรับการขยายระบบในอนาคต
-สอดคล้องกับหลักการออกแบบซอฟต์แวร์ที่ดี

## 🚀 How to Run

```
# 1. Clone repository
git clone [your-repo-url]

# 2. Install dependencies
npm install

# 3. Run server
npm start

# 4. Test API
# Open browser: http://localhost:3000
```

## 📝 API Endpoints
Method	Endpoint	Description
GET	/api/books	ดึงข้อมูลหนังสือทั้งหมด
GET	/api/books/:id	ดึงข้อมูลหนังสือตาม ID
POST	/api/books	เพิ่มหนังสือใหม่
PUT	/api/books/:id	แก้ไขข้อมูลหนังสือ
PATCH	/api/books/:id/borrow	ยืมหนังสือ
PATCH	/api/books/:id/return	คืนหนังสือ
DELETE	/api/books/:id	ลบหนังสือ
