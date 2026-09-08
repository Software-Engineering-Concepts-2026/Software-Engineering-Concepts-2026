# Quiz 3 — Requirements Engineering (Week 3) · 10 ข้อ

> **Post-quiz Pattern** (ท้ายคาบ 15 นาที) · **10 MCQ × 0.15 = 1.5%** · Close-book
> ครอบคลุม: Personas, Scenarios, User Stories, Acceptance Criteria, INVEST, FR vs NFR, Requirements Pit
> **อ่านก่อนสอบ:** [ESP] Ch.3 · [SE] Ch.4 · [PP] Tips 45, 78, 79 · สไลด์ Week3 + เคส Knight Capital / Therac-25 / Spotify / NHS / Fed

---

## Section A: เลือกคำตอบที่ถูกต้องที่สุด (10 ข้อ × 0.15 = 1.5 คะแนน)

**คำชี้แจง:** เลือกข้อที่ถูกต้องที่สุดเพียงข้อเดียว · Bloom 1–2 · เวลา 15 นาที

### A1. PP Tip 45 ("Requirements Pit") เน้นปัญหาสำคัญข้อใด?
- A) ลูกค้าไม่รู้ว่าต้องการอะไรแน่ชัด — programmer ต้อง discover ไม่ใช่ gather
- B) Requirements document ต้องยาวกว่า 100 หน้า
- C) ต้องเก็บ requirements ทั้งหมดใน database
- D) ต้องใช้ UML diagrams เสมอ

### A2. Persona ที่สมบูรณ์ควรมีกี่องค์ประกอบ (ตาม Sommerville 2019)?
- A) 2
- B) 3
- C) 5
- D) 7

### A3. User Story ที่ดีควรมีโครงสร้างแบบใด?
- A) "ระบบต้องทำ X" (เขียนเชิง technical)
- B) "As a [persona], I want [goal], so that [benefit]" + Acceptance Criteria
- C) รายการ checkbox ของ feature
- D) "User ต้องการ X" (vague)

### A4. INVEST criteria (Bill Wake 2003) สำหรับ User Story ประกอบด้วย:
- A) Internal, Normal, Valid, Easy, Small, Testable
- B) Independent, Negotiable, Valuable, Estimable, Small, Testable
- C) Important, Necessary, Vague, Easy, Significant, Tangible
- D) Inclusive, Notable, Versatile, Essential, Straightforward, Timely

### A5. Non-functional Requirement (NFR) ที่ดีต้องมีลักษณะอย่างไร?
- A) เขียนให้สั้น เช่น "fast" หรือ "secure"
- B) วัดผลได้ เช่น "response time < 2s ที่ p95"
- C) ใช้ภาษาทั่วไป ไม่ต้องมีตัวเลข
- D) เขียนเป็น adjective เท่านั้น

### A6. Scenario ตาม §3.3.2 ต่างจาก User Story อย่างไร และควรประกอบด้วยอะไร?
- A) Scenario = ประโยคสั้นแบบ As a / I want / So that — ไม่ต้องมีรายละเอียด
- B) Scenario = เรื่องเล่า narrative ที่ระบุ Persona + Objective + Action sequence + ปัญหาที่อาจเจอ + ผลลัพธ์ที่หวัง
- C) Scenario = Technical spec สำหรับ developer เท่านั้น
- D) Scenario = รายการ NFR ที่วัดได้

### A7. Acceptance Criteria แบบ Given-When-Then ข้อใดเขียนถูกต้อง (Campus Eats)?
- A) Given ผู้ใช้อยู่ที่ ม. — When กรองร้าน ≤ 1 กม. — Then แสดงเฉพาะร้านในรัศมี 1 กม. เรียงจากใกล้ไปไกล
- B) Given ระบบต้องเร็ว — When ผู้ใช้เปิดแอป — Then รู้สึกเร็ว
- C) Given อยากได้โปรโมชัน — When กดปุ่ม — Then ได้ของถูก
- D) Given เป็นนิสิต — When หิว — Then เปิดแอป

### A8. Requirements Engineering 4 ขั้นตาม Sommerville (2016) เรียงลำดับอย่างไร?
- A) Documentation → Elicitation → Validation → Analysis
- B) Elicitation → Analysis & Negotiation → Documentation → Validation
- C) Validation → Elicitation → Documentation → Analysis
- D) Analysis → Elicitation → Validation → Documentation

### A9. User Story ใหญ่เกิน 1 Sprint (เช่น "As a buyer I want to place an order") วิธี split ที่ถูกต้องตาม §3.4.4 คือข้อใด?
- A) แยกตาม workflow step — "Add to cart" / "Checkout" / "Pay" (หรือ By role / By data / By business rule / By interface)
- B) แยกตาม technical layer — "Frontend part" / "Backend part" / "Database part"
- C) แยกตามจำนวนคำใน story — ยาวเกิน 20 คำให้ตัดครึ่ง
- D) ไม่ต้องแยก — ยืด Sprint ออกไปจนกว่าจะเสร็จ

### A10. ข้อใดแยก FR vs NFR ได้ถูกต้องสำหรับ Campus Eats?
- A) FR: "response time < 2s ที่ p95" — NFR: "ระบบต้องแสดงรายการร้านอาหารพร้อมโปรโมชัน"
- B) FR: "ระบบต้องแสดงรายการร้านอาหารพร้อมโปรโมชัน" — NFR: "response time < 2s ที่ p95" (FR = สิ่งที่ระบบต้องทำ, NFR = คุณลักษณะที่วัดได้)
- C) FR และ NFR เหมือนกัน แยกไม่ได้
- D) FR: "secure" — NFR: "ระบบต้องค้นหาร้านตามระยะทาง"

---

## Section B: Reflection (ไม่นับคะแนน — ส่งเป็น reflect.md)

**B1. Apply — Magic Shipping Question (2–3 ประโยค)** ลูกค้าบอก "อยากให้แอปส่ง notification โปรโมชันใหม่" — ถามคำถามอย่างน้อย 3 ข้อเพิ่มเพื่อให้ requirement ชัดเจน (ใคร? เมื่อไหร่? บ่อยแค่ไหน? ยกเลิกได้ไหม? ฯลฯ) และสรุปว่า 3 ข้อนี้ช่วยลด ambiguity อย่างไร (1 ประโยค)

**B2. Connect — NFR (3–4 ประโยค)** เลือกแอปที่ใช้ทุกวัน: ระบุ NFR 1 ข้อ, วิธีวัด (ต้อง measurable — ตัวเลขชัดเจน), และผลกระทบถ้าไม่มี NFR นี้

**B3. Reflect — User Story (1 ประโยค)** เขียน User Story 1 เรื่องสำหรับ Sprint 1 ของโปรเจกต์ทีม (As a / I want / So that) + เหตุผล 1 ประโยค (จะถูกสร้างเป็น GitHub Issue ใน Lab 3)

> วิธีส่ง: branch `feature/post-quiz-3` → `reflect.md` ที่ root → commit + push + เปิด PR (merge พร้อม Lab 3)

---

## เฉลย (Answer Key) — ห้ามเปิดก่อนสอบ

> **สำหรับอาจารย์เท่านั้น**

| ข้อ | คำตอบ | แหล่งอ้างอิง |
|---|---|---|
| A1 | **A** | PP Tip 45 — "No one knows exactly what they want" (Hunt & Thomas 2019) — ต้อง discover ไม่ใช่ gather |
| A2 | **C** | Sommerville 2019 §3.3 — 5 องค์ประกอบ: Personalization, Job, Education, Relevance, Frequency |
| A3 | **B** | Jeffries 2001 — "As a / I want / So that" + Acceptance Criteria |
| A4 | **B** | Wake 2003 — Independent, Negotiable, Valuable, Estimable, Small, Testable |
| A5 | **B** | Sommerville 2016 — NFR ต้อง measurable ("ถ้าวัดไม่ได้ ทดสอบไม่ได้") |
| A6 | **B** | §3.3.2 — Scenario = narrative: Persona + Objective + Action sequence + ปัญหาที่อาจเจอ + ผลลัพธ์ที่หวัง |
| A7 | **A** | §3.4.3 — Given-When-Then ต้องวัดผลได้ (เช่น กรอง ≤1 กม. → แสดงร้านในรัศมีเรียงใกล้→ไกล); B/C/D คลุมเครือ |
| A8 | **B** | Sommerville 2016 §3.2 — Elicitation → Analysis & Negotiation → Documentation → Validation (ต่อเนื่อง ไม่ใช่ one-shot) |
| A9 | **A** | §3.4.4 — Split by role / data / workflow step / business rule / interface; B = แยกตาม layer ผิด INVEST (ไม่ Valuable/Testable) |
| A10 | **B** | §3.5 — FR = สิ่งที่ระบบต้องทำ (แสดงรายการร้าน), NFR = คุณลักษณะวัดได้ (response time <2s p95, HTTPS, uptime ≥99%) |

**💡 reflect.md:** คะแนนเป็น Completion ไม่ใช่ Content — นิสิตที่เขียนสะท้อนความคิดจะได้คะแนนเต็ม

---

*จัดทำโดย: ธรรมรัตน์ ธรรมา · สาขาวิทยาการคอมพิวเตอร์ คณะเทคโนโลยีสารสนเทศและการสื่อสาร มหาวิทยาลัยพะเยา · ภาคเรียนที่ 1 ปีการศึกษา 2569*
