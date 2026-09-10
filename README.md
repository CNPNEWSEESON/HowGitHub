# คู่มือ Git เบื้องต้น — Clone, Commit, Push

## 📋 ขั้นตอนที่ถูกต้อง

### 1. Clone โปรเจกต์ลงเครื่อง
```bash
git clone https://github.com/Akarawin-hub/Mini-Monopoly.git
```
คำสั่งนี้จะดาวน์โหลดโปรเจกต์ทั้งหมด **พร้อม `.git` มาให้แล้ว** (เชื่อมกับ origin ให้อัตโนมัติ)

> ⚠️ **ข้อสังเกต**: ถ้า `git clone` แล้ว **ไม่ต้อง** `git init` และ `git remote add origin` ซ้ำอีก — สองคำสั่งนี้ใช้ตอนที่คุณ**สร้างโฟลเดอร์เปล่าเอง** แล้วอยากเชื่อมกับ repo บน GitHub เท่านั้น

เข้าไปในโฟลเดอร์ที่ clone มา:
```bash
cd Mini-Monopoly
```

---

## 🌱 กรณีที่ 1: Clone มาแล้ว (ส่วนใหญ่ใช้แบบนี้)

```bash
# 1. แก้ไขไฟล์ตามต้องการ เช่น game/Player.ts

# 2. เพิ่มไฟล์ที่แก้เข้า staging area
git add game/Player.ts

# 3. บันทึกการเปลี่ยนแปลงพร้อมข้อความอธิบาย
git commit -m "แก้ไข logic ผู้เล่นใน Player.ts"

# 4. อัพขึ้น GitHub
git push
```

---

## 🌱 กรณีที่ 2: สร้างโปรเจกต์ใหม่เอง (ยังไม่มี .git)

```bash
# 1. เริ่มต้น git ในโฟลเดอร์
git init

# 2. เชื่อมกับ repo บน GitHub
git remote add origin https://github.com/Akarawin-hub/Mini-Monopoly.git

# 3. เพิ่มไฟล์
git add game/Player.ts

# 4. คอมมิท
git commit -m "ข้อความที่จะคอมเม้น"

# 5. เปลี่ยนชื่อ branch เป็น main
git branch -M main

# 6. อัพขึ้น GitHub ครั้งแรก
git push -u origin main
```

`-u` คือการตั้งค่าให้ branch ปัจจุบันผูกกับ `origin/main` — ครั้งต่อไปพิมพ์แค่ `git push` เฉยๆ ได้เลย

---

## 💡 เทคนิคที่มีประโยชน์

| คำสั่ง | ใช้ทำอะไร |
|---|---|
| `git status` | เช็คว่าไฟล์ไหนเปลี่ยน/ยังไม่ add |
| `git add .` | เพิ่มไฟล์ที่เปลี่ยนทั้งหมดในโฟลเดอร์ปัจจุบัน |
| `git pull` | ดึงโค้ดล่าสุดจาก GitHub มาก่อนแก้ไข (กันชนกับเพื่อนร่วมทีม) |
| `git log --oneline` | ดูประวัติ commit แบบสั้นๆ |

**ลำดับที่แนะนำทุกครั้งก่อนเริ่มงาน**: `git pull` → แก้โค้ด → `git add` → `git commit` → `git push`
