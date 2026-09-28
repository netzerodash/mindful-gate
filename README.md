# site/

หน้า Privacy Policy และ Support สำหรับ App Store Connect เป็น HTML/CSS ล้วน ไม่มี build step

- `support/` และ `en/support/` คือหน้าช่วยเหลือภาษาไทยและอังกฤษ
- `privacy/` และ `en/privacy/` คือนโยบายความเป็นส่วนตัวภาษาไทยและอังกฤษ
- `index.html` และ `privacy.html` เป็นทางผ่านสำหรับ URL เดิม จึงห้ามลบ
- `docs/app-store/privacy-policy.md` ต้องตรงกับข้อความหลักในหน้า Privacy

## ตรวจและเผยแพร่

```sh
python3 scripts/validate_site.py
```

`social-detox` เป็น source of truth เมื่อการแก้ไขขึ้น `main` workflow `Website` จะตรวจทุกหน้าแล้ว sync เฉพาะโฟลเดอร์นี้ไปยัง public repository `netzerodash/mindful-gate` ซึ่ง GitHub Pages เผยแพร่จาก branch `main`

workflow ใช้ deploy key แบบเขียนได้เฉพาะ public repository ผ่าน secret `SITE_DEPLOY_KEY` ไม่ต้องคัดลอกไฟล์ด้วยมือ
