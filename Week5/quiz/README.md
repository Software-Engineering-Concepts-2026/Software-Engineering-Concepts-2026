# Quiz 5 — Software Architecture (Week 5) · 10 ข้อ

> **Post-quiz Pattern** (ท้ายคาบ 15 นาที) · **10 MCQ × 0.15 = 1.5%** · Close-book
> ครอบคลุม: Architecture fundamentals, Trade-offs (5 คำถาม), Non-functional characteristics, Decomposition (Layered/MVC/Repository), ADR, C4 Model

**อ่านก่อนสอบ:** [ESP] Ch.4 · [SE] Ch.6 · [Bass et al. 2021] · [Nygard 2011] ADR · [Brown 2011] C4 Model · สไลด์ Week5 + เคส Denver/Healthcare.gov/BTS/Knight/Prime Video

---

## Section A: เลือกคำตอบที่ถูกต้องที่สุด (10 ข้อ × 0.15 = 1.5 คะแนน)

**คำชี้แจง:** เลือกข้อที่ถูกต้องที่สุดเพียงข้อเดียว · Bloom 1–2 · เวลา 15 นาที

### A1. [Architecture fundamentals] ตาม Bass, Clements & Kazman (2021) ในบทที่ 5 "Software Architecture" คืออะไร?

- A) แผนผังสวย ๆ ที่วาดก่อนเขียนโค้ด
- B) ชุดของการตัดสินใจที่ยากจะเปลี่ยน (hard-to-change decisions) — เช่น เลือก Monolith/Microservices, SQL/NoSQL, REST/gRPC
- C) Framework ที่ทีมเลือกใช้ (เช่น React, Express)
- D) Diagram ที่วาดครั้งเดียวแล้วจบ

### A2. [Architecture vs Design] ข้อใดอธิบายความต่างได้ถูกต้องที่สุด?

- A) Architecture = รายละเอียดการ implement (class, function) · Design = โครงสร้างระดับสูง
- B) Architecture = โครงสร้างระดับสูงที่เปลี่ยนยาก กระทบทั้งระบบ · Design = รายละเอียด implement ที่เปลี่ยนบ่อยได้ กระทบเฉพาะส่วน
- C) ทั้งสองเหมือนกัน แค่เรียกต่างกันในแต่ละทีม
- D) Architecture = การเขียนโค้ด · Design = การวาด diagram

### A3. [Trade-offs — 5 คำถาม] ก่อนตัดสินใจเชิงสถาปัตยกรรม Sommerville (2019) ให้ตอบ 5 คำถาม — ข้อใด **ไม่ใช่** 1 ใน 5 คำถามนั้น?

- A) Non-functional characteristics
- B) Product lifetime
- C) Framework ที่ dev ชอบเป็นการส่วนตัว
- D) Number of users

### A4. [Trade-offs — Quality Attributes] ข้อใดจับคู่ quality attributes ที่ขัดแย้งกันได้ถูกต้องตามบทที่ 5?

- A) Maintainability vs Performance — optimize ให้เร็วมากมักอ่าน/แก้ยากขึ้น
- B) Security vs Usability — ยิ่งปลอดภัย (2FA, password ซับซ้อน) ยิ่งใช้ยาก · Availability vs Time-to-Market — uptime สูงต้องลงทุน infra มาก
- C) Scalability vs Cost — scale มากย่อมแพงขึ้น
- D) ถูกทุกข้อ (ทุกคู่ข้างต้นเป็น trade-off ที่ต้องเลือกตามบริบท)

### A5. [Non-functional] สำหรับ **Campus Eats** (5,000 นิสิต × 10 ม. = 50,000 users) ข้อใดระบุ non-functional characteristic ได้ครบถ้วนที่สุดตามตาราง 5.2.3?

- A) เฉพาะ functional requirement (สั่งอาหาร, จ่ายเงิน)
- B) response < 2s, GPS real-time, privacy ของตำแหน่ง — และต้องชั่งกับกรณี BTS 2561 ที่ NFR ด้านทนคลื่นรบกวน 2,400 MHz กลายเป็นปัญหาหลักเมื่อเจอสภาพจริง
- C) ใช้ภาษาใดเขียนโค้ด
- D) จำนวนบรรทัดโค้ด

### A6. [Decomposition — Layered] Layered Architecture แบบ 5-layer generic model (Sommerville) มีกฎเรื่อง dependency อย่างไร?

- A) Dependency ชี้ลงล่างเท่านั้น (UI → Auth & UI Mgmt → Application → Shared Services → Database) · security/logging เป็น cross-cutting concern กระจายข้ามทุกชั้น
- B) Layer ไหนก็เรียก layer ไหนก็ได้ตามสะดวก
- C) UI Layer ต้องเรียก Database โดยตรงเพื่อความเร็ว
- D) Dependency ชี้ขึ้นบนเท่านั้น

### A7. [Decomposition — MVC + Repository] ข้อใดอธิบาย MVC และ Repository Pattern ได้ถูกต้องที่สุด?

- A) Model = presentation, View = business logic, Controller = data — Repository ไม่จำเป็น
- B) Model = business logic + data · View = presentation · Controller = รับ input → อัปเดต Model → เลือก View · Repository แยก data access เพื่อให้ business logic ไม่ผูก ORM, mock ใน test ง่าย, เปลี่ยน DB โดยไม่กระทบ business
- C) MVC ใช้ได้เฉพาะแอปเล็ก — แอปใหญ่ต้องไม่แยก concerns
- D) Repository คือฐานข้อมูลประเภทหนึ่ง

### A8. [Decomposition — Multi-tier vs Service-oriented] ข้อใดคือ **เหตุผลหลัก** ที่ควรเลือก Multi-tier แทน Service-oriented และบทเรียนจาก Prime Video (2023)?

- A) เมื่อต้องการ scale แบบ infinite และ resilience สูงสุด — Prime Video พิสูจน์ว่า serverless ดีกว่าเสมอ
- B) เมื่อข้อมูล structured + เปลี่ยนไม่บ่อย + local servers + ทีมเล็ก/ต้องการความเรียบง่าย — Prime Video ย้ายจาก Lambda+Step Functions กลับไป Monolith เพราะค่าใช้จ่ายพุ่ง 90% บทเรียนคือ "บริบทเปลี่ยน สถาปัตยกรรมที่ถูกก็อาจผิดได้"
- C) เมื่อทีมใหญ่และ deploy แต่ละ service อิสระทุกวัน
- D) เมื่อต้องการ polyglot (หลายภาษา) เสมอ

### A9. [ADR] Architecture Decision Record (ADR) ตาม Michael Nygard (2011) ประกอบด้วย 5 ส่วน — ข้อใดคือ 1 ใน 5 ส่วนนั้น และ ADR มีไว้เพื่ออะไร?

- A) Backlog — มีไว้ติดตามงานค้าง
- B) Consequences — บันทึกผลที่ตามมาทั้งบวก/ลบ · ADR มีไว้สร้าง institutional memory, ป้องกันการตัดสินใจซ้ำ, บันทึก trade-off context, และเป็น audit trail (เช่น ถ้า Denver/Healthcare.gov มี ADR อาจจับปัญหา "ไม่มีคนรับผิดชอบภาพรวม" ได้ก่อนลงทุน)
- C) Sprint Plan — มีไว้วางแผน Sprint
- D) Test Coverage — มีไว้วัด coverage

### A10. [C4 Model] C4 Model (Simon Brown, 2011) แบ่งสถาปัตยกรรมเป็น 4 ระดับ — ข้อใดเรียงลำดับได้ถูกต้อง?

- A) Code → Component → Container → Context
- B) Context (ระบบอยู่ที่ไหนในโลก: users + external systems) → Container (web app, API, DB) → Component (controllers, services) → Code (ระดับ class ถ้าจำเป็น)
- C) Context → Code → Container → Component
- D) มีเพียง 2 ระดับคือ Context และ Code

---

## Section B: Reflection (ไม่นับคะแนน — ส่งเป็น reflect.md)

ทำ **หลัง Lab05 ทั้ง 5 ขั้นเสร็จ** — เขียนสะท้อนสิ่งที่เพิ่งทำ (ดูตัวอย่างที่ `labs/guides/Post-quiz-5-Example.md` และ `labs/examples/lab05-sample-solution/reflect.md`)

**B1. Apply — ADR ฉบับแรก (2–3 ประโยค + บริบท)** — หลัง Lab ขั้น 4 เสร็จ: เปิด `docs/architecture/adr/0001-*.md` แล้วย่อเหลือ 2–3 ประโยค — Context (ทีม/เวลา/scale) + Decision (เลือกอะไร) + Consequences (ดี 1 + เสีย 1)

**B2. Connect — C4 Context + Container (3–4 ประโยค)** — หลัง Lab ขั้น 3 เสร็จ: เปิด `docs/architecture/c4-context.md` + `c4-container.md` แล้วย่อ — บอก Person ใคร + System/Container อะไร + Rel อะไร + technology อะไร (ทุก Rel ต้องมี label, Mermaid render ถูก)

**B3. Reflect — Tech Stack Decision (1–2 ประโยค)** — หลังทำ Lab05 ทั้ง 5 ขั้นแล้ว: เลือก stack หลัก (Frontend / Backend / Database) พร้อมเหตุผลเชิงบริบท 1 ประโยคต่อตัว (ไม่ใช่แค่ "เพราะถนัด" — ระบุ scale, deployment target, NFR)

> วิธีส่ง: branch `feature/post-quiz-5` → `reflect.md` ที่ root → commit + push + เปิด PR (merge พร้อม Lab 5)

---

## เฉลย (Answer Key) — ห้ามเปิดก่อนสอบ

- **A1. B** — Architecture = ชุดของการตัดสินใจที่ยากจะเปลี่ยน (Bass et al. 2021) — เลือก Monolith/Microservices, SQL/NoSQL, REST/gRPC ผิดต้องรื้อทั้งระบบ (เช่น Denver $560M, Healthcare.gov $1.7B) (Ch.5 §5.2.1)
- **A2. B** — Architecture = โครงสร้างระดับสูง เปลี่ยนยาก กระทบทั้งระบบ · Design = รายละเอียด implement เปลี่ยนบ่อยได้ กระทบเฉพาะส่วน (Ch.5 §5.2.2)
- **A3. C** — 5 คำถามจริง: NFR, lifetime, reuse, number of users, compatibility (กับ requirement ไม่ใช่ preference ของ dev) (Sommerville 2019, Ch.5 §5.2.3)
- **A4. D** — ถูกทุกข้อ — ทุกคู่เป็น trade-off ที่ต้องเลือกตามบริบท ไม่มีคำตอบถูกเสมอ (Ch.5 §5.2.4)
- **A5. B** — Campus Eats: response <2s + GPS real-time + privacy; BTS case แสดงว่า NFR ที่ไม่เจอในห้องทดลองอาจเป็นปัญหาหลักเมื่อใช้งานจริง (Ch.5 §5.2.3, §5.0)
- **A6. A** — Dependency ชี้ลงล่างเท่านั้น; security/logging เป็น cross-cutting concern (แก้ด้วย AOP/middleware) (Ch.5 §5.3.1)
- **A7. B** — MVC: Model(business+data)/View(presentation)/Controller(input→Model→View) · Repository: encapsulate data access, ไม่ผูก ORM, mock ง่าย (Ch.5 §5.3.2–5.3.3)
- **A8. B** — Multi-tier เหมาะกับ structured + เปลี่ยนไม่บ่อย + local + ทีมเล็ก; Prime Video 2023 ย้ายกลับ Monolith เพราะ cost +90% บทเรียนคือบริบทเปลี่ยนคำตอบก็เปลี่ยน (Ch.5 §5.4.4–5.4.5)
- **A9. B** — ADR 5 ส่วน: Status · Context · Decision · Consequences · Alternatives Considered (Nygard 2011); ประโยชน์ 4 ข้อ: institutional memory, ป้องกันตัดสินใจซ้ำ, trade-off context, audit trail (Ch.5 §5.5.1–5.5.2)
- **A10. B** — C4: Level 1 Context → Level 2 Container → Level 3 Component → Level 4 Code (Brown 2011) (Ch.5 §5.5.4)
