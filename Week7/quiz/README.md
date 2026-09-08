# Quiz 7 — Clean Code / DRY / ETC / Orthogonality / Refactoring (Week 7) · 10 ข้อ

> **Post-quiz Pattern** (ท้ายคาบ 15 นาที) · **10 MCQ × 0.15 = 1.5%** · Close-book
> ครอบคลุม: Clean Code (Naming/Comments), DRY, ETC, Orthogonality, Refactoring basics

**อ่านก่อนสอบ:** [PP] Ch.2 — ETC (Tip 14) · DRY (Tip 15, 5 duplication types) · Orthogonality (Tip 17) · Reversibility · [PP] Ch.7 (T65·T74) — Refactoring · Naming · [SE] Ch.7 — Implementation, code quality · [SCG] Ch.7 — Reading Code Bases with GenAI · สไลด์ Week7 + เคส Knight Capital / Apple goto fail / Voyager

---

## Section A: เลือกคำตอบที่ถูกต้องที่สุด (10 ข้อ × 0.15 = 1.5 คะแนน)

**คำชี้แจง:** เลือกคำตอบที่ถูกต้องที่สุดเพียงข้อเดียว · Bloom level 1–2 (Recall + Comprehension) · เวลา 15 นาที ท้ายคาบ (หลังเรียนทฤษฎี)

### A1. "Good Design Is Easier to Change" เป็น Tip ใดของ The Pragmatic Programmer และสื่อหลักการใด?
- A) Tip 6 — Don't Live with Broken Windows
- B) Tip 14 — ETC (Easier To Change): ออกแบบให้เปลี่ยน requirement ได้ง่าย — ถามว่า "แบบไหนแก้ได้ง่ายกว่า"
- C) Tip 18 — Reversibility
- D) Tip 65 — Being Pragmatic

### A2. DRY (Tip 15 — Don't Repeat Yourself) ที่ "ถูกต้อง" หมายความว่าอย่างไร?
- A) ห้าม copy-paste โค้ดเท่านั้น
- B) ทุกชิ้นของ **ความรู้ (knowledge)** ในระบบต้องมี single authoritative representation — ไม่ใช่แค่ห้าม copy โค้ด
- C) ห้ามเขียน comment ซ้ำกัน
- D) ต้องใช้ function แทนการ copy เสมอ แม้จะเป็นความรู้คนละเรื่อง

### A3. สถานการณ์ "Alice กับ Bob ทำสิ่งเดียวกันโดยไม่รู้ตัว — เขียน utility คำนวณส่วนลดแยกกันคนละไฟล์" ตรงกับ duplication ประเภทใด (PP Tip 15 — 5 types)?
- A) Code duplication
- B) Documentation duplication
- C) Data duplication
- D) Interdeveloper duplication

### A4. ตัวอย่าง DRY violation ที่พบบ่อยตาม Ch.7 คือข้อใด?
- A) ตั้งชื่อตัวแปรว่า `data` หรือ `info`
- B) ตรรกะคำนวณส่วนลดเดียวกันปรากฏใน `order.py` / `invoice.py` / `report.py` — แก้ promo rate ต้องแก้ 3 ที่
- C) เขียน comment อธิบาย "what" ซ้ำกับโค้ด
- D) ใช้ `goto fail;` ซ้ำ 2 ครั้ง

### A5. หลัก ETC (Easier To Change) แนะนำให้เลือกระหว่าง hardcode config ในโค้ด vs แยก config file อย่างไร?
- A) Hardcode ดีกว่าเพราะโค้ดสั้น
- B) แยก config file ดีกว่า — เปลี่ยนค่าไม่ต้องแก้โค้ด ไม่ต้อง recompile — ตัดสินด้วยคำถาม "ถ้า requirement เปลี่ยน แบบไหนแก้ได้ง่ายกว่า"
- C) ทั้งสองแบบ ETC เท่ากัน
- D) ETC แนะนำให้ใช้ framework ยอดนิยมเท่านั้น

### A6. "Two or more things are orthogonal if changes in one do not affect any of the others" คือ Tip ใด และหมายความว่าอะไร?
- A) Tip 14 (ETC) — โค้ดสั้นที่สุด
- B) Tip 17 (Orthogonality) — แต่ละ component เป็นอิสระต่อกัน เปลี่ยนส่วนหนึ่งไม่กระทบส่วนอื่น
- C) Tip 18 (Reversibility) — ตัดสินใจแบบ reversible
- D) Tip 45 (Tell, Don't Ask) — ส่ง message แทนการถาม state

### A7. ตัวอย่างใด "ไม่ orthogonal" และวิธีแก้ที่ถูกต้องคืออะไร?
- A) UI เรียก database โดยตรง → เปลี่ยน MySQL เป็น PostgreSQL ต้องแก้ UI ทุกหน้า — แก้โดยให้ UI เรียกผ่าน API/Service layer
- B) UI เรียกผ่าน API layer → เปลี่ยน DB แก้ที่ API ที่เดียว — นี่คือไม่ orthogonal
- C) ใช้หลาย framework พร้อมกันคือ orthogonal
- D) โค้ดทำงานแบบ multi-threaded คือ orthogonal

### A8. หลักตั้งชื่อที่ดี (Ch.7.2.2 — Naming) ข้อใด "ผิด"?
- A) ชื่อต้องสื่อเจตนา (intent) — บอกว่าทำอะไร ไม่ใช่ตัวเองเป็นอะไร
- B) หลีกเลี่ยงคำกลาง ๆ เช่น `data`, `info`, `temp`, `flag` ที่บอกอะไรไม่ได้
- C) ควรใช้ `a`, `b`, `c` หรือ `d` เสมอเพื่อให้โค้ดสั้น อ่านเร็ว
- D) ใช้ภาษาเดียวกันทั้ง codebase และให้ความยาวเหมาะสมกับ scope

### A9. Comment ที่ดีควรอธิบายสิ่งใด (Ch.7.2.3)?
- A) "what" ที่โค้ดทำ — เขียนซ้ำกับโค้ดทุกบรรทัด (เช่น `i = i + 1 # increment i`)
- B) "why" ที่โค้ดทำ — เหตุผลที่โค้ดไม่สามารถบอกเอง (เช่น `MAX_RETRIES = 5 # จาก requirement เก่า ห้ามแก้`)
- C) ประวัติการแก้ไขและชื่อผู้เขียนเท่านั้น
- D) ไม่ควรเขียน comment เลย

### A10. ข้อใดถูกต้องเกี่ยวกับ Refactoring (Ch.7.5 — Fowler 2018 + Boy Scout Rule)?
- A) Refactor คือการสะสมไว้แล้วทำทีเดียวตอนท้ายโปรเจกต์ — ไม่ต้องมี test ก็ทำได้ปลอดภัย
- B) Refactor ต้องทำเป็นนิสัย (habit, ไม่ใช่ event) + ต้องมี test ก่อน — ขั้น Fowler: Identify smell → Pick refactoring → Apply safely (run test ทุกขั้น); Boy Scout Rule: แตะโค้ดให้ดีขึ้นกว่าที่เจอ
- C) Refactor คือการเปลี่ยนพฤติกรรม (behavior) ของระบบให้ทำงานใหม่
- D) ถ้าไม่มี test ก็ refactor ได้เลยเพราะไม่เปลี่ยน behavior อยู่แล้ว

---

## Section B: Reflection (ส่งเป็น reflect.md — ไม่นับคะแนน แต่ต้องผ่าน)

> ทำหลัง Lab07 ทั้ง 5 ขั้นเสร็จ — `reflect.md` ที่ root → branch `feature/post-quiz-7` → PR (merge พร้อม Lab 7 = Milestone 1)
> ดูตัวอย่างที่ `labs/guides/Post-quiz-7-Example.md` และ `labs/examples/lab07-sample-solution/reflect.md`

**B1. Apply — Naming (2–3 ประโยค — เขียนหลัง Lab ขั้น 3)**
เลือก **1 ตัวแปร/ฟังก์ชันจริง** ที่เพิ่ง rename ใน Lab ขั้น 3:
- **ชื่อเก่า → ชื่อใหม่:** เช่น `d` → `order`, `calc` → `calculate_discount`, `tmp` → `subtotal`
- **อยู่ที่ไหน:** ไฟล์ + บรรทัด (เช่น `order.py:process_order(d, promo)` → `process_order(order, promo_code)`)
- **ทำไมดีขึ้น:** อ่านแล้วรู้ทันทีว่าคืออะไร — คนอื่นเข้าใจได้ใน 5 วินาที

**B2. Connect — DRY (3–4 ประโยค — เขียนหลัง Lab ขั้น 3)**
เลือก **1 DRY violation จริง** ที่เพิ่งแก้ใน Lab ขั้น 3:
- **อยู่ที่ไหน + ซ้ำกี่ที่:** เช่น `order.py` / `invoice.py` / `report.py` — 12 บรรทัดเหมือนกัน (discount logic)
- **ประเภท duplication:** code / documentation / data / representational / interdeveloper (PP Tip 15)
- **แก้อย่างไร:** เช่น extract เป็น `calculate_discount()` ใน `src/pricing.py` ที่เดียว แล้วให้ทั้ง 3 ไฟล์ import
- **ETC ดีขึ้นอย่างไร:** แก้ promo rate จาก 3 ที่ → 1 ที่ (`PROMO_RATE`) — ลืมไม่ได้

**B3. Reflect — Refactor + Orthogonality (1–2 ประโยค — เขียนหลัง Lab ทั้งหมดเสร็จ)**
หลังทำ Lab07 ทั้ง 5 ขั้นแล้ว ทีมจะทำอะไรต่อใน Sprint หน้า:
- **จะ refactor อะไรต่อ:** 1 จุดชัดที่ยังไม่ได้ทำ (เช่น `process_order` 40 บรรทัด → แยกเป็น `calculate_subtotal` + `apply_tax`)
- **Orthogonality:** จะแยกส่วนไหนให้เป็นอิสระ (เช่น handler → `OrderService` → DB — เปลี่ยน DB แก้ที่เดียว)
- **Tests:** มี test อยู่ไหม ถ้าไม่มีต้องเขียนก่อน refactor

> **เกณฑ์ที่อาจารย์ดู (Section B):** B1 ต้องระบุตัวแปรจริง + ชื่อใหม่ + เหตุผล / B2 ต้องระบุไฟล์ที่ซ้ำ + กี่ที่ + ประเภท + แผน refactor / B3 ต้องระบุ 1 จุด + จะแยกเป็นอะไร + เหตุผล — ไม่ครบให้แก้ก่อน merge PR

**ตัวอย่าง `reflect.md` ที่ส่งจริง:**

```markdown
# Post-quiz 7 — Reflection (เขียนหลังทำ Lab07)
**ชื่อ:** สมชาย ใจดี — **ทีม:** Campus Eats — **Sprint:** 7

## B1. Apply — Naming (หลังทำขั้น 3)
ตัวแปร `d` ใน `order.py:process_order(d, promo)` ย่อมาจาก data — ไม่สื่อความหมาย
เขียนใหม่เป็น `order` และ `promo_code` — อ่านแล้วรู้ทันทีว่าคือคำสั่งซื้อและรหัสโปรโมชัน

## B2. Connect — DRY (หลังทำขั้น 3)
เจอ DRY violation: logic คำนวณส่วนลดซ้ำใน `order.py` / `invoice.py` / `report.py` (3 ที่, 12 บรรทัดเหมือนกัน) — ประเภท code duplication
ถ้า refactor จะ extract เป็น `calculate_discount()` ใน `src/pricing.py` ที่เดียว แล้วให้ทั้ง 3 ไฟล์ import — แก้ promo rate ครั้งเดียวจบ (ETC)

## B3. Reflect — Refactor (หลังทำ Lab)
Sprint หน้า จะ refactor `process_order` ที่ยาว 40 บรรทัด — แยกเป็น `calculate_subtotal` + `calculate_discount` + `apply_tax`
เหตุผล: แต่ละส่วน test แยกได้ง่าย และ reuse ใน invoice/report ได้ — จะแยก handler ออกจาก DB ผ่าน OrderService ด้วย (Orthogonality)
```

---

## เฉลย (Answer Key) — ห้ามเปิดก่อนสอบ

- **A1. B** — Tip 14 ETC — Good Design Is Easier to Change (PP Ch.2; Ch.7 Roadmap)
- **A2. B** — DRY = ความรู้ทุกชิ้นมีที่เดียว ไม่ใช่แค่ห้าม copy-paste (PP Tip 15; Ch.7.3.1)
- **A3. D** — Interdeveloper duplication = คนสองคนทำสิ่งเดียวกันโดยไม่รู้ตัว (PP Tip 15)
- **A4. B** — DRY violation: ตรรกะเดียวกันในหลายไฟล์ — แก้ 3 ที่ พลาดง่าย (Ch.7.3.1 ตัวอย่าง discount)
- **A5. B** — ETC: แยก config file — เปลี่ยนค่าไม่ต้องแก้โค้ด/recompile — ตัดสินด้วย "แบบไหนแก้ได้ง่ายกว่า" (Ch.7.3.2)
- **A6. B** — Tip 17 Orthogonality — เปลี่ยนส่วนหนึ่งไม่กระทบส่วนอื่น (PP Ch.2; Ch.7.4)
- **A7. A** — ไม่ orthogonal: UI→DB ตรง — เปลี่ยน DB ต้องแก้ UI ทุกหน้า — แก้โดยผ่าน API layer (Ch.7.4 ตัวอย่าง)
- **A8. C** — ผิด: ใช้ `a,b,c,d` ทำให้อ่านไม่ออก — ชื่อต้องสื่อเจตนา หลีกเลี่ยงคำกลาง ๆ (Ch.7.2.2)
- **A9. B** — Comment ที่ดีอธิบาย "why" ที่โค้ดบอกเองไม่ได้ — ไม่ใช่ "what" ซ้ำกับโค้ด (Ch.7.2.3; Abelson)
- **A10. B** — Refactor เป็นนิสัย + ต้องมี test ก่อน — Fowler 3 ขั้น + Boy Scout Rule (Ch.7.5; Fowler 2018; PP T65·T74)

**อ้างอิง:** Hunt & Thomas (2019) *The Pragmatic Programmer* 2nd ed. Tips 14,15,17,65,74 · Fowler (2018) *Refactoring* 2nd ed. · Martin (2008) *Clean Code* · Abelson & Sussman (1996) *SICP*

> วิธีส่ง: branch `feature/post-quiz-7` (หรือ `feature/lab7-refactor-<smell>`) → `reflect.md` ที่ root → commit + push + PR (merge พร้อม Lab 7 = Milestone 1)
