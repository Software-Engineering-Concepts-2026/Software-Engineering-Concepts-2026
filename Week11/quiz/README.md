# Quiz 11 — Security + Privacy (Week 11) · 10 ข้อ

> **Post-quiz Pattern** (ท้ายคาบ 15 นาที) · **10 MCQ × 0.15 = 1.5%** · Close-book
> ครอบคลุม: Secure by Design (CIA Triad + 5 Principles), OWASP Top 10 + STRIDE, Input Validation, PDPA พ.ศ. 2562, Secrets & Hashing (.env)

**อ่านก่อนสอบ:** [ESP] Ch.7 (Security) · Ch.8 (Reliable Programming) · [SE] Ch.13–14 · [PP] T72–T73 · [OWASP] Top 10 (2021) · สไลด์ Week11 + เคส Equifax/Cambridge Analytica/Capital One/SolarWinds/WannaCry

---

## Section A: เลือกคำตอบที่ถูกต้องที่สุด (10 ข้อ × 0.15 = 1.5 คะแนน)

**คำชี้แจง:** เลือกข้อที่ถูกต้องที่สุดเพียงข้อเดียว · Bloom 1–2 (Recall + Comprehension) · เวลา 15 นาที

### A1. [Secure by Design] CIA Triad ประกอบด้วยอะไร — กรณี Equifax 2017 (ข้อมูล 147M หลุด) ละเมิดมิติใด?
- A) Confidentiality, Integrity, Authentication — ละเมิด Availability
- B) **Confidentiality, Integrity, Availability — ละเมิด Confidentiality** (ข้อมูลถูกเข้าถึงโดยไม่ได้รับอนุญาต)
- C) Control, Integrity, Access — ละเมิด Integrity
- D) Confidentiality, Internet, Availability — ละเมิด Integrity

### A2. [Secure by Design] หลักการใดอธิบายได้ดีที่สุดว่า “Capital One — server มีสิทธิ์อ่าน S3 ทุก bucket จน SSRF จุดเดียวรั่ว 106M บัญชี”?
- A) Defense in Depth — ต้องมีหลายชั้น
- B) **Least Privilege — ให้สิทธิ์เท่าที่จำเป็นต่อการทำงาน ไม่มากกว่า** (app account ไม่ควรอ่านทุก bucket)
- C) Minimize Attack Surface — ลดจุด input
- D) Security by Obscurity — ซ่อน URL ไว้

### A3. [OWASP] OWASP Top 10 (2021) อันดับ 1 ที่พบบ่อยที่สุดคือข้อใด?
- A) Injection (A03)
- B) Cryptographic Failures (A02)
- C) **Broken Access Control (A01) — ผู้ใช้ทำในสิ่งที่ตนไม่มีสิทธิ์**
- D) Security Misconfiguration (A05)

### A4. [OWASP] STRIDE ตัวอักษร **T** และ **E** หมายถึงภัยคุกคามใด? — ตัวอย่าง: แก้ `recipient` ใน request body ให้เงินโอนผิดบัญชี, และ user ธรรมดาได้สิทธิ์ admin
- A) Tracking / Exposure
- B) Threat / Error
- C) **Tampering (แก้ไขข้อมูล) / Elevation of Privilege (ยกระดับสิทธิ์)**
- D) Transmission / Encryption

### A5. [Input Validation] การป้องกัน SQL Injection ที่ถูกต้องที่สุดคือ?
- A) ลบช่องเว้นวรรคออกจาก input
- B) ใช้ `f"SELECT * FROM users WHERE name = '{name}'"` แล้ว escape เครื่องหมาย `'` เอง
- C) **ใช้ Parameterized Query — driver แยก “โค้ด query” ออกจาก “ข้อมูล”** (`db.execute("SELECT ... WHERE name = :name", {"name": name})`)
- D) เชื่อ client-side validation ก็พอเพราะใช้ HTTPS แล้ว

### A6. [Input Validation] ตามหลัก “Never Trust User Input” + Defense in Depth 3 ชั้น — ข้อใดเรียงลำดับการ validate ได้ถูกต้อง?
- A) Semantic → Format → Constraint
- B) **Format (type/email/UUID ที่ API boundary) → Constraint (length/range/whitelist) → Semantic (start < end, จำนวนพอ)**
- C) Constraint → Semantic → Format
- D) ไม่ต้อง validate ถ้าใช้ framework มาตรฐาน

### A7. [PDPA] PDPA พ.ศ. 2562 กำหนดหลักการใด **ครบถ้วน**ที่สุด?
- A) เก็บข้อมูลได้ไม่จำกัด ไม่ต้องขอ consent
- B) **ต้องขอ Consent ก่อนเก็บ + ใช้ตาม Purpose Limitation + เก็บเท่าที่จำเป็น (Data Minimization) + มี Right to be Forgotten + แจ้งเหตุ Breach**
- C) Consent ขอครั้งเดียวใช้ได้ทุกวัตถุประสงค์ตลอดไป
- D) ไม่ต้องแจ้งเมื่อข้อมูลหลุดถ้าเป็นแอปเล็ก

### A8. [PDPA] เมื่อเกิด data breach ตาม PDPA ต้องแจ้งหน่วยงานภายในกี่ชั่วโมง — และโทษปรับสูงสุดเท่าใด?
- A) 24 ชั่วโมง / 1 ล้านบาท
- B) 48 ชั่วโมง / 3 ล้านบาท
- C) **72 ชั่วโมง / 5 ล้านบาท + ความรับผิดทางแพ่ง** (บทเรียน Cambridge Analytica — ใช้ข้อมูลเกิน scope ของ consent)
- D) 7 วัน / ไม่มีโทษปรับ

### A9. [Secrets] ทำไมการเก็บ password ด้วย SHA-1 (แม้เติม salt) จึงไม่ปลอดภัย — ควรใช้อะไรแทน?
- A) SHA-1 ถอดรหัสกลับได้
- B) salt ทำให้ hash สั้นเกินไป
- C) **SHA-1 เป็น fast hash — GPU brute-force ได้เร็วมาก ต้องใช้ slow hash + auto salt เช่น bcrypt / argon2**
- D) SHA-1 ถูกกฎหมายห้ามใช้

### A10. [Secrets] วิธีจัดการ Secrets (.env) ที่ถูกต้องที่สุดสำหรับทีม — ข้อใด **ปลอดภัยที่สุด**?
- A) เขียน `DB_PASSWORD="supersecret"` ในโค้ดและ commit ลง git เพื่อให้ทีมเห็นง่าย
- B) เขียน secret ลง Dockerfile เพื่อให้ build ผ่านเสมอ
- C) เก็บใน Git history เผื่อลืมแล้วค่อย revert
- D) **ใช้ `.env` ที่ถูก `.gitignore` + GitHub Secrets สำหรับ CI + Vault/AWS Secrets Manager ใน production + rotate ทันทีถ้าหลุด + สแกนด้วย gitleaks/TruffleHog ใน CI**

---

## Section B: Reflection (ไม่นับคะแนน — ส่งเป็น reflect.md หลัง Lab11)

**B1. Apply — STRIDE Threat Model (2–3 ประโยค)** เลือก 1 endpoint ของทีม (เช่น `POST /users/{id}/profile`) ระบุว่าเสี่ยงต่อ STRIDE ≥ 2 ข้อ พร้อมเหตุผลสั้น ๆ — เช่น S (Spoofing: ขโมย JWT) / T (Tampering: แก้ body) / E (Elevation: user → admin)

> Starter สำหรับ Lab 11 Exercise 11.1

**B2. Connect — Input Validation Plan (2–3 ประโยค)** เลือก 1 endpoint ที่รับ input แล้วออกแบบ validation: Schema (Pydantic/Zod/Joi) + Fields + constraint (length/format/range) + Error response `400 {field: "message"}`

> Starter สำหรับ Lab 11 Exercise 11.2

**B3. Reflect — Secrets Management Plan (1–2 ประโยค)** ระบุ 3 ข้อปฏิบัติที่ทีมจะใช้ Sprint หน้า: Storage (`.env` + GitHub Secrets / Vault) + Rotation (หลุด → rotate + ลบ history) + Scanning (gitleaks/TruffleHog ใน CI)

> Starter สำหรับ Lab 11 Exercise 11.3

> วิธีส่ง: branch `feature/post-quiz-11` (หรือ `feature/lab11-security`) → สร้าง `reflect.md` ที่ root → commit + push + เปิด PR (merge พร้อม Lab 11) · เกณฑ์: B1 ระบุ endpoint+STRIDE 2 ข้อ / B2 ครบ schema+field+400 / B3 ครบ 3 ข้อปฏิบัติ

---

## เฉลย (Answer Key) — ห้ามเปิดก่อนสอบ

| ข้อ | คำตอบ | อ้างอิง |
|-----|--------|---------|
| A1 | **B** — CIA = Confidentiality, Integrity, Availability · Equifax ละเมิด Confidentiality | ESP §7.1, SE §14.1, Ch11 §11.2.2 |
| A2 | **B** — Least Privilege: ให้สิทธิ์เท่าที่จำเป็น | ESP §7.2, Ch11 §11.2.3 (Capital One) |
| A3 | **C** — A01 Broken Access Control ขึ้นอันดับ 1 ปี 2021 | OWASP Top 10 (2021), Ch11 §11.3.1 |
| A4 | **C** — T=Tampering, E=Elevation of Privilege | STRIDE Model, Ch11 §11.3.2 |
| A5 | **C** — Parameterized Query แยกโค้ดออกจากข้อมูล | OWASP A03, ESP Ch.8, Ch11 §11.4.3 |
| A6 | **B** — Format → Constraint → Semantic (Defense in Depth 3 ชั้น) | Ch11 §11.4.3 |
| A7 | **B** — Consent + Purpose Limitation + Data Minimization + Right to be Forgotten + Breach Notification | PDPA พ.ศ. 2562, Ch11 §11.6.2 |
| A8 | **C** — 72 ชั่วโมง / ปรับสูงสุด 5 ล้านบาท + แพ่ง | PDPA พ.ศ. 2562, Ch11 §11.6.2 |
| A9 | **C** — SHA-1 เร็วเกิน → GPU crack ได้ ต้องใช้ bcrypt/argon2 (slow hash + salt) | ESP §7.6, Ch11 §11.5.1 |
| A10 | **D** — `.env` (gitignored) + CI Secrets + Secret Manager + rotate + scan | OWASP A08, PP T72, Ch11 §11.5.2 |

*อ้างอิงหลัก: Sommerville ESP Ch.7–8 · NIST SP 800-63B · OWASP Top 10 (2021) · PDPA พ.ศ. 2562 · Hunt & Thomas PP Tips 72–73*
