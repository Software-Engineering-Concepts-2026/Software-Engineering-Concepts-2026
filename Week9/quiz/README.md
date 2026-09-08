# Quiz 9 — Software Testing (Week 9) · 10 ข้อ

> **Post-quiz Pattern** (ท้ายคาบ 15 นาที) · **10 MCQ × 0.15 = 1.5%** · Close-book
> ครอบคลุม: TDD (Red-Green-Refactor), Testing Pyramid (Unit/Integration/System), Test Doubles, Coverage & Branch Coverage, AI Test Generation

**อ่านก่อนสอบ:** [SE] Ch.8 — Software Testing · [ESP] Ch.8–9 · [PP] Tip 66, 67, 69, 71, 92, 93 · [SCG] Ch.13 — Testing with GenAI · สไลด์ Week9 + เคส Knight Capital / Therac-25 / Mars Climate Orbiter / Apple goto fail · Beck (2003) TDD · Cohn (2009) Test Pyramid · Meszaros (2007) Test Doubles

---

## Section A: เลือกคำตอบที่ถูกต้องที่สุด (10 ข้อ × 0.15 = 1.5 คะแนน)

**คำชี้แจง:** เลือกข้อที่ถูกต้องที่สุดเพียงข้อเดียว · Bloom 1–2 (Recall + Comprehension) · เวลา 15 นาที

### A1. Testing Pyramid (Mike Cohn 2009) แนะนำสัดส่วนใดจึงจะสมดุลระหว่างความเร็ว ต้นทุน และความเชื่อมั่น?

- A) 90% Unit, 5% Integration, 5% E2E
- B) 70% Unit, 20% Integration, 10% E2E
- C) 33% เท่ากันทุกระดับ
- D) 10% Unit, 20% Integration, 70% E2E (Ice Cream Cone)

### A2. ข้อใดจับคู่ **ระดับการทดสอบกับตัวอย่างได้ถูกต้องที่สุด**?

- A) Unit — เปิด browser, login, คลิกจนจบ flow / System — `calculate_discount(100, 0.10) == 90.0`
- B) Unit — `calculate_discount(100, 0.10) == 90.0` / Integration — API → Service → DB → Response / System — เปิด browser, login, คลิก, ตรวจผล
- C) Integration — ทดสอบฟังก์ชันเดียวแยกเดี่ยว / Unit — ทดสอบหลาย component พร้อมกัน
- D) System — ทดสอบเร็ว <1ms ต่อ test / Unit — ทดสอบช้าเป็นนาทีต่อ test

### A3. NASA Mars Climate Orbiter (1999, $327M) และ Therac-25 สอนบทเรียนเดียวกันเรื่องระดับการทดสอบ — ข้อใดถูกต้อง?

- A) Unit test อย่างเดียวพอ — ทั้งสองเคสมี unit test ผ่านหมดแต่พังเพราะไม่มี **Integration test** ที่รันหลาย component/ระบบร่วมกัน
- B) ต้องเพิ่ม E2E ให้เป็น 70% จึงจะป้องกันได้
- C) ควรเลิกเขียน unit test แล้วเขียนแต่ system test
- D) Bug เกิดจาก code coverage ต่ำเพียงอย่างเดียว

### A4. Test Doubles (Meszaros 2007) — ข้อใดนิยาม **Mock** ได้ถูกต้อง?

- A) Object ที่ return ค่าตายตัวเพื่อควบคุม response — ไม่ตรวจสอบการเรียก
- B) Object ที่มี implementation จริงแต่เรียบง่าย เช่น in-memory database (Fake)
- C) Object ที่ **verify ว่าถูกเรียกตามที่คาดหวัง** (verify behavior) — เช่น `mock_email_service.verify_called_with(to="user@test.com")`
- D) Object ที่ส่งผ่านแต่ไม่ถูกใช้ เพียงเติม parameter list (Dummy)

### A5. TDD (Beck 2003) — ลำดับ Red-Green-Refactor ที่ถูกต้องคือข้อใด?

- A) เขียน production code ให้เสร็จ → เขียน test → refactor
- B) Red — เขียน test ที่ fail ก่อน → Green — เขียน code น้อยที่สุดให้ผ่าน → Refactor — ปรับโครงสร้างโดย test ยังเขียว
- C) Green → Red → Refactor
- D) Refactor → Red → Green

### A6. ประโยค “ถ้า test เขียนยาก — design ไม่ดี” ในบท 9.5.3 หมายถึงอะไร?

- A) TDD ทำให้ต้อง mock 5 object แปลว่า function ผูกกับภายนอกมากเกินไป — สัญญาณให้แยก pure logic / ลด coupling
- B) ต้องเลิกเขียน test แล้วเขียน code ให้ง่ายอย่างเดียว
- C) ต้องเพิ่ม E2E แทน unit test
- D) ต้องเพิ่ม coverage ให้ถึง 100% ทันที

### A7. “Code Coverage 100%” หมายความว่าอย่างไร และทำไมจึง **ไม่ได้แปลว่าไม่มี bug** (บท 9.6.1–9.6.3)?

- A) ทุกบรรทัดถูก run ใน test — แต่ไม่รับประกันว่าทุก behavior/branch ถูกต้อง (Apple `goto fail` ผ่านทุกบรรทัดแต่ skip SSL verification)
- B) ไม่มี bug เหลือแล้ว — ปลอดภัย deploy ได้ทันที
- C) Test ผ่านทั้งหมด 100%
- D) Branch coverage = 100% โดยอัตโนมัติ

### A8. Branch Coverage vs Line Coverage — จากตัวอย่าง `if user.is_admin: show_admin_panel() else: show_user_panel()` ข้อใดถูก?

- A) Test แค่ `is_admin=True` ก็ได้ line 100% และ branch 100% แล้ว
- B) Test แค่ `is_admin=True` ได้ line 100% (ทุกบรรทัดถูก run) แต่ branch เพียง 50% — ต้อง test ทั้งสองทางจึงจะได้ branch 100%
- C) Line coverage ไม่มีประโยชน์ วัดแค่ branch ก็พอ
- D) เป้าหมายที่ดีคือ line coverage 100% เสมอ — ไม่ว่าเสียเวลาเท่าไร

### A9. Saboteur Testing (PP Tip 92) และ Mutation Testing (mutmut) — ถ้าแทรกบั๊กเปลี่ยน `>` เป็น `>=` แล้ว test ยังเขียว หรือ mutation score < 50% แปลว่าอะไร?

- A) Bug ไม่มีจริง — tool คิดไปเอง
- B) Test **exercise code แต่ไม่ verify behavior** — ไม่ได้ test boundary ตรงจุดนั้น ต้องเพิ่ม test ที่จุดแทรกบั๊ก
- C) Test ดีมาก — จับ mutant ได้หมด
- D) Code quality ต่ำ — ต้อง rewrite ทั้งไฟล์

### A10. AI Test Generation (SCG Ch.13 — Writing Unit Tests with GenAI) — ข้อใดคือสิ่งที่ **ไม่ควรทำ**?

- A) ใช้ AI generate test cases จาก Acceptance Criteria แล้วให้คน review
- B) ใช้ AI review test quality / หา blind spot
- C) ปล่อยให้ AI generate **test + implementation พร้อมกันในรอบเดียว** โดยไม่มีการตรวจอิสระ — เสี่ยง test ผ่านเพราะผิดทั้งคู่ (false confidence)
- D) ใช้ AI ช่วยเขียน property-based test จาก invariants

---

## Section B: Reflection (ไม่นับคะแนน — ส่งเป็น reflect.md หลัง Lab09)

> ทำหลัง Lab09 ทั้ง 5 ขั้นเสร็จ — ดูตัวอย่างที่ `labs/guides/Post-quiz-9-Example.md`

**B1. Apply — Coverage Report (2–3 ประโยค + ตัวเลข)** รัน `pytest --cov=src --cov-branch --cov-report=term-missing -v` หลัง Lab ขั้น 4 — รายงานตัวเลข Overall line/branch เทียบกับก่อนทำ, ระบุไฟล์/ฟังก์ชันต่ำสุด + Missing lines, และแผนเพิ่ม test อะไรต่อ

**B2. Connect — TDD (3–4 ประโยค)** เลือก **1 function จริง** ที่ทำ TDD ใน Lab ขั้น 2 (เช่น `calculate_total`, `calculate_discount`) — เล่าการเขียน test ก่อน code แล้ว design เปลี่ยนอย่างไร (เช่น `promo_code: str | None`, แยก constant เพื่อ test boundary) + ดีขึ้น/แย่ลงอย่างไร

**B3. Reflect — Testing Culture (1–2 ประโยค)** หลัง Lab ทั้ง 5 ขั้น ทีมจะปรับ **1 อย่าง** ที่ทำได้จริงใน Sprint หน้า พร้อมวิธีบังคับ (เช่น Branch Protection `main` → Require `test` + `lint` ก่อน merge)

> **เกณฑ์ผ่าน B:** B1 มีตัวเลขหลัง Lab + ระบุไฟล์ต่ำ + แผน / B2 มีชื่อ function + design เปลี่ยน + ดี/แย่ / B3 มี 1 อย่าง + วิธีบังคับ — ไม่ครบให้แก้ก่อน merge PR

> วิธีส่ง: branch `feature/post-quiz-9` (หรือ `feature/lab9-testing`) → สร้าง `reflect.md` ที่ root → commit + push + เปิด PR (merge พร้อม Lab 9)

---

## เฉลย (Answer Key) — ห้ามเปิดก่อนสอบ

- **A1. B** — 70% Unit (เร็ว/ถูก), 20% Integration, 10% E2E (ช้า/แพง/brittle) — Cohn (2009) *Succeeding with Agile*; ช.9.3–9.3.4
- **A2. B** — Unit <1ms แคบ, Integration 100ms–1s หลาย component, System/E2E วินาที–นาทีทั้งระบบ — ช.9.3.1–9.3.3
- **A3. A** — ทั้งสองทีมมี unit pass แต่ไม่มี integration ที่รันรวมกัน — Knight/Mars/Therac-25 เคส 9.1; NASA (1999)
- **A4. C** — Mock = verify behavior; Stub = return ค่าตายตัว; Fake = in-memory impl; Dummy = placeholder — Meszaros (2007); ช.9.4.1–9.4.3
- **A5. B** — Red (failing test) → Green (minimal pass) → Refactor (structure) รอบ 5–10 นาที — Beck (2003); ช.9.5.1–9.5.2
- **A6. A** — test เขียนยาก = coupling สูง สัญญาณ refactor แยก pure logic — ช.9.5.3
- **A7. A** — 100% = ทุกบรรทัดถูก run ไม่ใช่ทุก behavior ถูก — Apple goto fail, Knight flag ตาย 8 ปี — ช.9.6.1; Langley (2014)
- **A8. B** — line 100% ≠ branch 100%; เป้าหมายแนะนำ 70%+ (90%+ สำหรับ critical) ไม่ต้อง 100% เสมอ — ช.9.6.2–9.6.3
- **A9. B** — Saboteur/Mutation จับ test ที่ exercise แต่ไม่ verify — ต้องเพิ่ม test ที่ boundary นั้น — PP Tip 92–93; ช.9.6
- **A10. C** — ห้ามให้ AI gen test+impl พร้อมกันโดยไม่ตรวจอิสระ — SCG Ch.13; PP Tip 71
