# Way To Shine Fans.com — prototype

ต้นแบบเว็บแอปธีมดำ/น้ำเงิน พร้อม SHOP, PRE-ORDER countdown, token wallet 3 ประเภท, login/register, chat UI และ Admin Studio

## เปิดใช้งานบน Vercel
1. แตกไฟล์ ZIP แล้วอัปโหลดโฟลเดอร์โปรเจกต์ขึ้น GitHub
2. เข้า Vercel → Add New → Project → Import Git Repository
3. กด Deploy ได้เลย (เป็น static site ไม่ต้อง build command)
4. URL จะได้จาก Vercel หลัง deploy สำเร็จ

## บัญชีแอดมินสำหรับเดโมเท่านั้น
- Email: `admin@waytoshinefans.com`
- Password: `WTSadmin2026!`

**สำคัญ:** นี่เป็น prototype ที่เก็บข้อมูลใน `localStorage` ของเบราว์เซอร์ ไม่ใช่ระบบ production จริง ข้อมูลไม่ได้ sync ระหว่างอุปกรณ์ ผู้ใช้สามารถแก้ข้อมูลฝั่งเครื่องได้ และรหัสผ่านเดโมไม่ปลอดภัย ห้ามใช้กับข้อมูลจริงหรือรับชำระเงินจริง

ก่อนเปิดใช้จริง ควรเชื่อม Supabase (Auth + Postgres + Row Level Security) หรือ backend ที่ปลอดภัย เพื่อให้:
- ตรวจสิทธิ์ Admin ฝั่ง server ไม่ใช่ใน browser
- จัดเก็บ password ด้วยระบบ auth ที่ปลอดภัย
- sync สินค้า/ออเดอร์/ข้อความ/ยอด token ข้ามอุปกรณ์
- ป้องกันการซื้อซ้ำและการแก้ token โดยผู้ใช้
- ส่งข้อความแชตถึงแอดมินได้จริง
- ตั้งเวลาสิ้นสุดพรีออร์เดอร์จากเวลา server

## หมายเหตุ
สิทธิ์ “ฟรีครั้งแรก” ในเดโมนี้นับต่อสมาชิกต่อสินค้า โดยหลังจากนั้นจะใช้ token ชนิดที่สินค้านั้นระบุไว้ โทเค่นเริ่มต้นเป็นยอดทดลอง ไม่มีมูลค่าเงินจริง
