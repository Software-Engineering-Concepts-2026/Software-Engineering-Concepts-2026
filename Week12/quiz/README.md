# Quiz 12 — Advanced Refactoring & Technical Debt (Week 12) · 10 ข้อ

> **Post-quiz Pattern** (ท้ายคาบ 15 นาที) · **10 MCQ × 0.15 = 1.5%** · Close-book
> ครอบคลุม: Refactoring (นิยาม + 8 เทคนิค Fowler), Technical Debt (Cunningham + Fowler Quadrant + การติดตาม), Code Smells 9 ประเภท, AI-Assisted Refactoring (SCG Ch.10)

**อ่านก่อนสอบ:** [Fowler 2018] *Refactoring* Ch.2–3 · [PP] T40, T65 · [SE] Ch.9 · [SCG] Ch.10 · สไลด์ Week12 + เคส Knight Capital / Netscape / Mars Climate Orbiter

---

## Section A: เลือกคำตอบที่ถูกต้องที่สุด (10 ข้อ × 0.15 = 1.5 คะแนน)

**คำชี้แจง:** เลือกข้อที่ถูกต้องที่สุดเพียงข้อเดียว · Bloom 1–2 (Recall + Comprehension) · เวลา 15 นาที ท้ายคาบ (หลังเรียนทฤษฎี)

### A1. [Code Smells] Method ใดเข้าข่าย **Feature Envy** มากที่สุด — และแก้ด้วยเทคนิคใด? [§12.2.1]
- A) Method ที่มี parameter 5+ ตัว — แก้ด้วย Introduce Parameter Object
- B) **`OrderProcessor.apply_discount(order)` ที่ใช้ `order.total`, `order.customer.is_vip()` มากกว่า `self.*` — แก้ด้วย Move Method ย้าย logic ไป `Order`**
- C) `user.team.project.company.get_manager().get_profile().name` — แก้ด้วย Hide Delegate
- D) Class ที่มี `if-elif` 8 ชั้น — แก้ด้วย Replace Conditional with Polymorphism

### A2. [Code Smells] ข้อใดอธิบายความต่างระหว่าง **Divergent Change** กับ **Shotgun Surgery** ได้ถูกต้อง? [§12.2.4]
- A) เหมือนกัน — แก้ด้วย Extract Class เหมือนกัน
- B) Divergent = แก้ 1 เรื่องต้องไปหลาย class / Shotgun = class เดียวถูกแก้หลายเหตุผล
- C) **Divergent = class เดียวถูกแก้หลายเหตุผล → แก้ด้วย Extract Class (split) / Shotgun = แก้ 1 เรื่องต้องไปหลาย class → แก้ด้วย Move Field + Move Method (merge)**
- D) Divergent แก้ด้วย Hide Delegate / Shotgun แก้ด้วย Replace Inheritance with Delegation

### A3. [Refactoring] ตามนิยาม Fowler (2018) — "Refactoring" คืออะไร? [§12.3]
- A) เขียนระบบใหม่ทั้งหมดด้วย framework ใหม่
- B) เพิ่ม feature ใหม่โดยเปลี่ยน external behavior
- C) **ปรับโครงสร้างภายใน (internal structure) โดยไม่เปลี่ยนพฤติกรรมภายนอก (external behavior) — ต้องมี test เป็น safety net**
- D) แก้ bug ใน production โดยเปลี่ยน behavior ให้ถูกต้อง

### A4. [Refactoring] Safety Net 5 ขั้นตาม PP Tip 65 — ข้อใดเรียงลำดับได้ถูกต้อง? [§12.4.1]
- A) Refactor → เขียน test → commit → deploy
- B) ใช้ AI refactor → merge ทันที → รัน test ทีหลัง
- C) **มี test ก่อน (ถ้าไม่มีให้เขียน characterization test) → refactor ขั้นเล็กทีละเทคนิค → รัน test ทุกขั้น → commit atomic (1 refactoring = 1 commit) → ถ้า fail revert แค่ขั้นนั้น**
- D) Refactor + เพิ่ม feature พร้อมกันใน commit เดียวเพื่อประหยัดเวลา

### A5. [Technical Debt] Ward Cunningham (1992) + Fowler Quadrant — ช่องใด **อันตรายที่สุด**? [§12.5.2]
- A) Prudent + Deliberate — "ต้องส่งของก่อน แล้วค่อยกลับมาแก้" (ยอมรับได้)
- B) Prudent + Inadvertent — "ตอนนี้รู้แล้วว่าควรทำยังไง" (เรียนรู้)
- C) **Reckless + Deliberate — "ไม่มีเวลา design" / "รู้ว่าผิดแต่ไม่สน" — ทีมไม่มี future**
- D) Reckless + Inadvertent — "อะไรคือ layering?" (ขาดความรู้ แต่ไม่ตั้งใจ)

### A6. [Technical Debt] การจัดการหนี้ — ข้อใดปฏิบัติตาม **PP Tip 21** และ §12.5.3 ได้ถูกต้องที่สุด? [§12.5.3]
- A) "หลังส่งงานค่อย refactor" — ไม่ต้องจัดสรรเวลา Sprint
- B) บันทึก debt ไว้ในใจ ไม่ต้องทำ backlog
- C) **Track ทุก debt ลง Tech Debt Backlog → Prioritize ตาม severity (🔴→🟡→🟢) → Allocate 10–20% ของ Sprint ให้ debt repayment → Pay off ตัวที่ interest สูงสุดก่อน**
- D) จ่ายหนี้ทั้งหมดพร้อมกันใน Sprint เดียวก่อน Demo Day

### A7. [Code Smells] โค้ด `user.team.project.company.get_manager().get_profile().name` และ `email` ที่เป็น `str` กระจาย validation 8 ที่ — จัดเป็น smell ใดตามลำดับ? [§12.2.3, §12.2.7]
- A) Long Parameter List / Data Clumps
- B) Feature Envy / Divergent Change
- C) **Message Chains (Train Wreck) → แก้ด้วย Hide Delegate / Primitive Obsession → แก้ด้วย Replace with Value Object (`Email` class รวมศูนย์ validation)**
- D) Inappropriate Intimacy / Shotgun Surgery

### A8. [Refactoring] โค้ดไม่มี test จะ refactor — ขั้นตอนแรกที่ถูกต้องที่สุดคือ? [§12.4.2]
- A) Refactor ทันที แล้วค่อยเขียน test ทีหลัง
- B) Rewrite ทั้งไฟล์แล้วรัน manual test
- C) **เขียน characterization test ที่บันทึก behavior ปัจจุบัน (แม้เป็น bug) ก่อน — `assert apply_discount(order) == 850` → refactor → test ยัง pass = behavior ไม่เปลี่ยน**
- D) ใช้ AI refactor แล้ว merge โดยไม่ต้อง test เพราะ AI ถูกต้องเสมอ

### A9. [Technical Debt] บทเรียน **Knight Capital (2012)** — ขาดทุน $440M ใน 45 นาที — สาเหตุหลักตาม §12.0 คือ? [§12.0]
- A) ไม่มี firewall ทำให้ถูกโจมตี
- B) ทีมใช้ Waterfall ทั้งที่ requirements เปลี่ยน
- C) **dead code (Power Peg flag) ที่ไม่มีใครเข้าใจหลงเหลือ 8 ปี ถูก deploy กลับมาทำงาน — เทียบเท่า Tech Debt ที่ไม่มีใครกล้าแตะ**
- D) ใช้ pound-force กับ newton ปนกันเหมือน Mars Orbiter

### A10. [AI Assistant] Workflow `explain → propose → apply → test` (SCG Ch.10, §12.7) — ข้อใดถูกต้องที่สุด? [§12.7]
- A) ให้ AI แก้ไฟล์ตรง ๆ แล้ว merge ทันทีโดยไม่ต้องตรวจ — AI ไม่เคยผิด
- B) ขั้น Propose มีไว้เพื่อให้ AI สร้างโค้ดได้เร็วขึ้น
- C) **Explain ให้ AI อธิบาย smell → Propose ให้ AI เสนอทางเลือกก่อน apply เพื่อให้ทีมตรวจ 4 คำถาม (ทำไม/edge case/test ต้องเปลี่ยนไหม/side effect) → Apply เอง → Test ทุกขั้น — และห้ามใช้ AI กับ security-sensitive / ไม่มี test / performance-critical / architecture decisions**
- D) AI refactor ได้ทุกกรณีโดยไม่ต้องมี test

---

## Section B: Reflection (ไม่นับคะแนน — ส่งเป็น reflect.md)

**B1. Apply — เลือก 1 Code Smell (2–3 ประโยค)** เลือก 1 smell จากโปรเจกต์ทีม (Feature Envy / Inappropriate Intimacy / Primitive Obsession / Divergent Change / Shotgun Surgery / Data Clumps / Message Chains ฯลฯ) ระบุ: **Smell**: ชื่อ + file/line — **เหตุผล**: ทำไมถึงเป็น smell (หลักฐานจากโค้ด) — **Refactoring ที่จะใช้**: 1 เทคนิค + สิ่งที่ต้องระวัง (consequence)

> นี่คือ starter สำหรับ Lab 12 (Refactor 1 smell → 1 PR)

**B2. Connect — Fowler Quadrant ของทีม (2–3 ประโยค)** ประเมิน technical debt ของโปรเจกต์ทีม: **เลือก 1 debt** ที่มีอยู่ตอนนี้ — **จัดช่อง**ใน Fowler Quadrant (Reckless/Prudent × Deliberate/Inadvertent) + เหตุผล — **แผนจ่ายคืน** จะปิด debt นี้เมื่อไหร่ (Sprint ไหน / ก่อน Demo Day W14?)

**B3. Reflect — AI Workflow (1–2 ประโยค)** สะท้อนการใช้ AI ในการ Refactor: **Explain** — ให้ AI อธิบาย smell ครั้งไหนที่ AI ตอบผิดหรืออธิบายไม่ครบ? — **ตรวจสอบ** — ตอบ 4 คำถาม (ทำไม/edge case/test ต้องเปลี่ยนไหม/side effect) กับ proposal ที่ AI เสนอ

> นี่คือ starter สำหรับ Lab 12 (AI-assisted refactor + `docs/refactoring-log.md`)

> วิธีส่ง: สร้าง branch `feature/post-quiz-12` → สร้าง `reflect.md` ที่ root → commit + push + เปิด PR (จะ merge พร้อม Lab 12)

---

## เฉลย (Answer Key) — ห้ามเปิดก่อนสอบ

- **A1. B** — Feature Envy: method ใช้ data class อื่นมากกว่า `self` → Move Method ไป class ที่ใช้บ่อยสุด (Fowler 2018, §12.2.1)
- **A2. C** — Divergent = class เดียวหลายเหตุผล → split (Extract Class) / Shotgun = 1 เรื่องหลาย class → merge (Move Field/Method) — หลักจำ: Divergent = ย้ายออก, Shotgun = ย้ายเข้าหากัน (§12.2.4)
- **A3. C** — Refactoring = เปลี่ยน internal structure ไม่เปลี่ยน external behavior + ต้องมี test (§12.3, Fowler 2018)
- **A4. C** — Safety Net: test ก่อน → ขั้นเล็ก → รัน test ทุกขั้น → commit atomic → revert ถ้า fail — ห้าม refactor + feature พร้อมกัน, ห้าม refactor ไม่มี test (PP Tip 65, §12.4.1)
- **A5. C** — Reckless + Deliberate อันตรายสุด: รู้ว่าผิดแต่ไม่สน = หนี้ที่ไม่มีวันจ่าย (§12.5.2)
- **A6. C** — Track → Prioritize (🔴🟡🟢) → Allocate 10–20% Sprint (PP Tip 21) → Pay off ตัว interest สูงสุดก่อน — "หลังส่งงานค่อย refactor" ไม่เคยเกิดขึ้นจริง (§12.5.3)
- **A7. C** — `a.b().c().d().e()` = Message Chains → Hide Delegate (Law of Demeter) / `str` แทน object = Primitive Obsession → Value Object รวมศูนย์ validation (§12.2.3, §12.2.7)
- **A8. C** — Characterization test (Feathers 2004): บันทึก behavior ปัจจุบันก่อน refactor — refactor โดยไม่มี test = เดินบนเชือกไม่มีตาข่าย (§12.4.2)
- **A9. C** — Knight Capital: dead code 8 ปีถูก activate ซ้ำ → ขาดทุน $440M ใน 45 นาที → บทเรียน: โค้ดที่ "ยังมีอยู่แต่ไม่มีใครเข้าใจ" = Tech Debt แพงสุด (§12.0, Bloomberg 2012)
- **A10. C** — Workflow 4 ขั้น: explain → propose (ตรวจ 4 คำถามก่อน apply) → apply เอง → test ทุกขั้น — ห้ามใช้ AI กับ security / ไม่มี test / performance-critical / architecture (§12.7, SCG Ch.10)
