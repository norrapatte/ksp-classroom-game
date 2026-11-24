# KSP Classroom Simulation — บทที่ 2 ทักษะการคิดขั้นสูง

เกมจำลองห้องเรียน 3D (EP1–EP3 + Ending) เป็นเว็บไฟล์เดียว ไม่ต้อง build

```
index.html          ตัวเกม (ฝังโมเดล 3D รูป เสียง และฟอนต์ไว้ในไฟล์)
VDO/opening.mp4     วิดีโอ Opening
sound/              เพลงประกอบ (BGM) และเสียงพากย์ — ต้องอัปขึ้นไปด้วย ไม่งั้นเกมไม่มีเสียง
.nojekyll           ให้ GitHub Pages ส่งไฟล์ตรง ๆ ไม่ผ่าน Jekyll
```

## Deploy ขึ้น GitHub Pages

1. สร้าง repository ใหม่บน GitHub (Public)
2. กด **Add file → Upload files** แล้วลากไฟล์ทั้งหมดในโฟลเดอร์นี้ขึ้นไป
   (index.html, README.md, .nojekyll และโฟลเดอร์ VDO กับ sound) → **Commit changes**
   - ถ้าลาก .nojekyll ไม่ขึ้น (ไฟล์ซ่อน) ข้ามได้ เกมยังทำงานปกติ
3. ไปที่ **Settings → Pages** → Source: **Deploy from a branch** → Branch: **main** / **(root)** → Save
4. รอ 1–2 นาที จะได้ลิงก์ `https://<username>.github.io/<repo-name>/`

ใช้ git แทนได้:

```bash
git init
git add .
git commit -m "Deploy KSP classroom simulation"
git branch -M main
git remote add origin https://github.com/<username>/<repo-name>.git
git push -u origin main
```

## เปลี่ยนวิดีโอ Opening

Export เป็น .mp4 (H.264 + AAC) ตั้งชื่อ `opening.mp4` แล้วอัปโหลดทับ `VDO/opening.mp4`
แนะนำ 1280px ไม่เกิน ~10 MB เพื่อให้โหลดเร็ว (GitHub อัปผ่านเว็บได้ไม่เกิน 25 MB ต่อไฟล์)
ถ้าวิดีโอโหลดไม่ได้ เกมจะข้ามไปหน้า "รับภารกิจ" อัตโนมัติ

## หมายเหตุ

- index.html ขนาดประมาณ 21 MB ครั้งแรกจะโหลดนานสักหน่อย ครั้งต่อไปเบราว์เซอร์จะ cache ไว้
- แนะนำเปิดบน Chrome / Edge บนคอมพิวเตอร์
