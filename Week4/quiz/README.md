# Quiz 4 — Prototyping & AI-Assisted Development (Week 4) · 10 ข้อ

> **Post-quiz Pattern** (ท้ายคาบ 15 นาที) · **10 MCQ × 0.15 = 1.5%** · Close-book
> ครอบคลุม: Tracer Bullets vs Prototype, Two-stage Prototyping, Paper/Interactive Prototypes, GenAI in SDLC, Co-pilot vs Ghost Writer, Five S's Prompting, Chain-of-Thought/Few-shot/Role, จริยธรรม & ความเสี่ยง AI

**อ่านก่อนสอบ:** [ESP] §1.3 · [PP] Topics 12–13, 61 (Tips 20, 21) · [SCG] Ch.1, 4–5 · สไลด์ Week 4 + เคส Zappos/Dropbox/Samsung/Air Canada/Wongnai

---

## Section A: เลือกคำตอบที่ถูกต้องที่สุด (10 ข้อ × 0.15 = 1.5 คะแนน)

**คำชี้แจง:** เลือกข้อที่ถูกต้องที่สุดเพียงข้อเดียว · Bloom 1–2 (Recall + Comprehension) · เวลา 15 นาที

### A1. Tracer Bullets (PP Tip 20) แตกต่างจาก Prototype (PP Tip 21) อย่างไร?
- A) Tracer ใช้เวลา 1 วัน Prototype ใช้หลายสัปดาห์
- B) Tracer คือโครง end-to-end ที่บางแต่ทำงานจริง ต่อยอดได้; Prototype คือของที่เขียนเพื่อเรียนรู้ ทิ้งได้
- C) Tracer ต้องเขียน test ส่วน Prototype ไม่ต้อง
- D) ทั้งสองเหมือนกัน แค่ชื่อต่าง

### A2. หลัก Five S's ของ Prompting (SCG Ch.4) ประกอบด้วย:
- A) Simple, Short, Sweet, Smart, Structured
- B) Structured, Surrounding, Single task, Specific, Short
- C) Step-by-step, Specific, Sensible, Short, Secure
- D) System, Service, Storage, Speed, Scale

### A3. "AI เป็น co-pilot ไม่ใช่ ghost writer" หมายความว่าอย่างไร?
- A) AI เขียน code ให้ทั้งหมด นิสิตแค่ review
- B) AI ช่วยคิด ช่วยร่าง ช่วยตรวจ — นิสิตเป็นเจ้าของผลงาน อธิบายได้ทุกบรรทัด
- C) AI ห้ามใช้ในงานเขียน code
- D) ใช้ AI ได้เฉพาะงาน documentation

### A4. Two-stage Prototyping (Sommerville) แนะนำให้ทำอย่างไรกับ prototype ที่ใช้กับลูกค้า?
- A) เก็บไว้ต่อยอดเป็น production
- B) ใช้แทน production code
- C) Throw away แล้วเริ่มสร้าง production version ใหม่
- D) ส่งให้ลูกค้า deploy เอง

### A5. ความเสี่ยงสำคัญที่สุดของ AI-assisted development ที่นิสิตควรระวังคือ?
- A) AI ใช้เวลาโหลดนาน
- B) Hallucination — AI generate code ที่ดูดีแต่ทำงานผิด หรือ API ที่ไม่มีอยู่จริง
- C) AI ไม่สามารถเขียนภาษา Python ได้
- D) AI มีค่าใช้จ่ายสูง

### A6. Paper prototype กับ Interactive prototype (HTML/CSS/JS) ต่างกันอย่างไร และควรใช้เมื่อใด?
- A) เหมือนกันทุกประการ แค่เครื่องมือต่าง
- B) Paper prototype — ต้นทุนต่ำสุด ใช้ทดสอบ flow/ไอเดียเร็วกับผู้ใช้; Interactive prototype — คลิกได้ ทดสอบ interaction จริง ก่อนลง backend (Lab 4 ใช้แบบหลัง)
- C) Paper prototype ใช้ได้เฉพาะงานดีไซน์โลโก้; Interactive prototype ใช้ได้เฉพาะระบบใหญ่
- D) Paper prototype ต้องเขียนโค้ด production เสมอ; Interactive prototype ไม่ต้องทดสอบกับผู้ใช้

### A7. Generative AI ช่วยได้ใน 7 จุดของ SDLC (Herszfang & Henstock 2025) — ข้อใด **ไม่ใช่** จุดที่ระบุในบทเรียน?
- A) Ideation — ระดมฟีเจอร์ / Requirements — ร่าง User Story
- B) Implementation — ร่างโค้ด / Testing — ร่างชุดทดสอบ
- C) Deployment — AI ตัดสินใจปล่อย production แทนทีมโดยอัตโนมัติโดยไม่ต้อง review
- D) Documentation — ร่าง README / Code Review — ชี้จุดเสี่ยง

### A8. เมื่อ prompt ซับซ้อน เทคนิคใดตรงกับคำอธิบาย "ให้ตัวอย่าง 1–2 ชิ้น แล้วให้ AI ทำข้อถัดไปตามแพทเทิร์นเดียวกัน"?
- A) Chain of Thought — สั่งให้คิดเป็นขั้น (วิเคราะห์ → ระบุขอบ → เขียนเทสต์ → ลงมือ → ตรวจ)
- B) Few-shot — ให้ตัวอย่างแล้วให้ทำต่อ
- C) Role prompting — กำหนดบทบาทเช่น "คุณเป็น senior Python..."
- D) Structured prompting — แบ่ง Context/Task/Constraints/Format

### A9. ตามกติการายวิชา (4.6) และ ACM Code of Ethics ข้อใดคือวิธีใช้ AI ที่ **ถูกต้อง**?
- A) ส่งรหัสนิสิต ข้อมูลสุขภาพ หรือข้อมูลส่วนบุคคลจริงให้ AI เพื่อให้คำตอบแม่นขึ้น
- B) ใช้ AI เขียนทั้งโปรเจกต์แล้วส่งเลย ไม่ต้องระบุใน AI_USAGE.md เพราะ AI เป็นผู้ช่วย
- C) ระบุเครื่องมือ prompt และส่วนที่รับจาก AI ใน `AI_USAGE.md` · ไม่ส่งข้อมูลส่วนบุคคลจริง (PDPA) · ทดสอบโค้ดก่อนส่ง
- D) ใช้ AI ทำข้อสอบ Quiz ได้ เพราะเป็นงานเดี่ยว

### A10. กรณี Samsung (2023) และ Air Canada (2022–2024) สอนบทเรียนใดเกี่ยวกับความรับผิดชอบเมื่อใช้ AI?
- A) Samsung ห้ามใช้ GenAI เพราะโมเดลฉลาดไม่พอ; Air Canada ไม่ต้องรับผิดชอบเพราะแชตบอทตอบเอง
- B) ทุก prompt คือข้อมูลที่ส่งออก — ต้องมีกติกา (Samsung พบ 3 เคสส่ง source code หลุด) และองค์กรต้องรับผิดชอบทุกคำตอบที่ AI ปล่อยถึงลูกค้า (ศาล BCCRT 2024 สั่ง Air Canada จ่าย 812.02 CAD)
- C) ส่ง source code ให้ ChatGPT ปลอดภัยเสมอ เพราะข้อมูลเรียกคืนได้
- D) แชตบอทตอบผิดเป็นความผิดของผู้ใช้ที่ถามไม่ดี

---

## Section B: Reflection (ไม่นับคะแนน — ส่งเป็น reflect.md)

**B1. Apply — Prompt Critique (2–3 ประโยค)**

Prompt เดิม: *"ช่วยเขียน code Python ที่ดีๆ หน่อย"*

ไม่มีบริบท ไม่มีงาน ไม่มีรูปแบบผลลัพธ์ — เขียน prompt ใหม่ตาม Five S's (Structured / Surrounding / Single task / Specific / Short) สำหรับฟังก์ชัน `calculate_discount(price, member_level)` แล้วบอกว่าทำไมของใหม่ดีกว่า

**B2. Connect — AI ในงานที่ใช้ (3–4 ประโยค)**

เลือกงานที่คุณทำเป็นประจำ (เรียน / ทำงาน / โปรเจกต์ส่วนตัว) — ระบุ 1 task ที่ AI ช่วยได้จริง (เช่น ร่าง boilerplate, อธิบาย error) และ 1 task ที่ AI ใช้ไม่ได้หรือไม่ควรใช้ (เช่น ตัดสินใจสถาปัตยกรรมทั้งระบบโดยไม่ review) พร้อมเหตุผล

**B3. Reflect — AI Strategy ใน Sprint หน้า (1 ประโยค)**

ใน Lab 4 (Interactive Prototype) คุณจะใช้ AI ในขั้นตอนใดของการทำ Prototype บ้าง? ระบุ 1 step + เหตุผล (เช่น "ใช้ร่าง HTML/CSS แล้วแก้เอง 30% เพราะ...")

> วิธีส่ง: สร้าง branch `feature/post-quiz-4` → สร้าง `reflect.md` ที่ root → commit + push + เปิด PR (จะ merge พร้อม Lab 4) · B1 เป็นจุดตั้งต้นของ Lab 4

---

## เฉลย (Answer Key) — ห้ามเปิดดูก่อนสอบ

### Section A — Post-quiz

- **A1. B** — Tracer = โครง end-to-end บางแต่ทำงานจริง ต่อยอดได้ (PP Tip 20); Prototype = เขียนเพื่อเรียนรู้ ทิ้งได้ (PP Tip 21)
- **A2. B** — Five S's = Structured, Surrounding, Single task, Specific, Short (SCG Ch.4, ตาราง 4.2)
- **A3. B** — Co-pilot = AI ช่วยคิด/ร่าง/ตรวจ คนเป็นเจ้าของ อธิบายได้ทุกบรรทัด (SCG Ch.1; 4.4.2)
- **A4. C** — Prototype ที่เจอผู้ใช้ภายนอกต้อง throw away (Sommerville 2019, p.28) — ป้องกัน technical debt
- **A5. B** — Hallucination = code ดูดีแต่ผิด/เรียก API ไม่มีอยู่ (SCG Ch.5) — ต้อง review + test ทุกครั้ง
- **A6. B** — Paper = ต้นทุนต่ำสุด ทดสอบ flow เร็ว; Interactive (HTML/CSS/JS) = คลิกได้ ทดสอบ interaction จริงก่อนลง backend (4.3 + Lab 4)
- **A7. C** — 7 จุดที่ AI ช่วยได้คือ Ideation/Requirements/Design/Implementation/Testing/Documentation/Code Review — ไม่มี "AI deploy แทนโดยไม่ review"; AI ร่างให้ ไม่ได้รับผิดชอบแทน (4.4.1)
- **A8. B** — Few-shot = ให้ตัวอย่าง 1–2 ชิ้นแล้วให้ทำต่อ; Chain of Thought = คิดเป็นขั้น; Role = กำหนดบทบาท (4.5.4)
- **A9. C** — กติการายวิชา: ระบุใน `AI_USAGE.md` + ห้ามส่งข้อมูลส่วนบุคคลจริง (PDPA) + ทดสอบก่อนส่ง + ห้ามใช้ทำ Quiz (4.6)
- **A10. B** — Samsung: 3 เคสส่ง source code หลุดในเดือนเดียว → ห้ามใช้บนอุปกรณ์บริษัท (TechCrunch 2 พ.ค. 2023); Air Canada: ศาล BCCRT 2024 ตัดสินว่าบริษัทต้องรับผิดชอบคำตอบแชตบอท (4.0, 4.4.2, 4.6)

### Section B — Reflection (แนวคำตอบ)

- **B1.** Prompt ใหม่ต้องมี Context (Python 3.12, ไม่มี framework), Task เดียว (เขียน `calculate_discount`), Constraints (member_level: gold/silver/none → 20%/10%/0%), Format (1 function + docstring + ตัวอย่างเรียก) — ดีกว่าเพราะ Specific + Surrounding + Short ครบ ทำให้ AI ไม่ต้องเดา
- **B2.** ตัวอย่าง: ช่วยได้ = อธิบาย stack trace / ร่าง unit test จาก acceptance criteria; ไม่ควร = ให้ออกแบบสถาปัตยกรรมทั้งระบบแล้วก๊อปเลย เพราะต้อง trade-off บริบททีม/สเกลที่ AI ไม่รู้
- **B3.** ตัวอย่าง: "ใช้ AI ร่างโครง HTML/CSS ของหน้า Campus Eats แล้วแก้ Tailwind เอง เพราะ AI เร็วใน boilerplate แต่ต้องคุม UX เอง"
