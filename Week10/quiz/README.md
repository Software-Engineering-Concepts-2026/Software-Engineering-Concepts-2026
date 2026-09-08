# Quiz 10 — DevOps & Continuous Delivery (Week 10) · 10 ข้อ

> **Post-quiz Pattern** (ท้ายคาบ 15 นาที) · **10 MCQ × 0.15 = 1.5%** · Close-book
> ครอบคลุม: DevOps (CALMS, DORA), CI/CD, IaC, Branching (Trunk-Based), Pipeline

**อ่านก่อนสอบ:** [ESP] Ch.10 — DevOps, CI/CD, IaC, DevOps scorecard · [SE] Ch.25 — Configuration management, DevOps · [PP] T34 "Automate Everything" · สไลด์ Week10 + เคส Knight Capital / GitLab / AWS S3

---

## Section A: เลือกคำตอบที่ถูกต้องที่สุด (10 ข้อ × 0.15 = 1.5 คะแนน)

**คำชี้แจง:** เลือกข้อที่ถูกต้องที่สุดเพียงข้อเดียว · Bloom 1–2 · เวลา 15 นาที ท้ายคาบ (หลังเรียนทฤษฎี)

### A1. DevOps — "CALMS" Framework — "L" ย่อมาจากคำใด? [DevOps]
- A) Learning
- B) Lean
- C) Lifecycle
- D) Logging

### A2. DORA Metrics — 4 metrics ใด *ไม่รวม* อยู่ในชุดวัด DevOps maturity? [DevOps]
- A) Deployment Frequency
- B) Lead Time for Changes
- C) Code Coverage
- D) Mean Time To Recovery (MTTR)

### A3. CI / CD — Continuous Delivery vs Continuous Deployment ต่างกันที่จุดใด? [CI/CD]
- A) Delivery = build artifact พร้อม deploy แต่ต้องกดปุ่มอนุมัติ; Deployment = deploy ถึง production อัตโนมัติเมื่อ test ผ่าน
- B) Delivery = ใช้ Docker; Deployment = ใช้ Kubernetes
- C) Delivery = manual test; Deployment = auto test
- D) ทั้งคู่เหมือนกันทุกประการ

### A4. CI Pipeline — ข้อใด *ไม่ใช่* แนวปฏิบัติที่ดี (Best Practice)? [Pipeline]
- A) Fail fast — ใส่ lint ก่อน test
- B) Cache dependencies เพื่อไม่ต้อง download ทุกครั้ง
- C) Pipeline ควรใช้เวลาเกิน 30 นาที เพื่อให้ build "ละเอียดถี่ถ้วน"
- D) Coverage threshold — fail ถ้า coverage ลด

### A5. Branching — Trunk-Based Development หลักการสำคัญที่สุดคือ? [Branching]
- A) ใช้ long-lived branch แยกทุก feature เพื่อกันงานชนกัน
- B) ทุกคน commit ลง trunk/main บ่อยๆ ด้วย branch อายุสั้น (< 1 วัน) + ทุก commit ผ่าน build/test อัตโนมัติ
- C) ต้องใช้ GitHub กับ Docker เท่านั้น
- D) ห้ามมี branch ใดๆ เลยแม้แต่ branch ชั่วคราว

### A6. CI/CD Pipeline — ลำดับ stage ที่ถูกต้องตาม Best Practice คือ? [Pipeline]
- A) Deploy → Build → Test
- B) Lint → Test (parallel) → Build artifact → Deploy (gated)
- C) Test → Lint → Deploy → Build
- D) Build → Deploy → Test บน production

### A7. Deployment Strategies — Blue-Green Deployment ทำงานอย่างไร? [CI/CD]
- A) มี 2 environment (Blue = ปัจจุบัน, Green = ใหม่) — deploy ไป Green → ทดสอบ → switch traffic → ถ้าผิด switch กลับ Blue (instant rollback)
- B) แบ่งผู้ใช้ออกเป็น 2 กลุ่มเท่าๆ กันถาวร
- C) ทาสี UI เป็น 2 สีเพื่อเทียบ conversion
- D) Deploy ทีละเครื่องจนครบทุกเครื่อง (rolling ธรรมดา)

### A8. Deployment Strategies — ข้อดีที่โดดเด่นของ Canary เมื่อเทียบกับ Blue-Green คือ? [CI/CD]
- A) เห็นผลกับ 100% ของผู้ใช้ทันที ตรวจผลได้รวดเร็ว
- B) ปล่อยให้กลุ่มผู้ใช้เล็กๆ (เช่น 5%) ทดลองก่อน → ดู error rate/latency → ค่อยเพิ่มเป็น 25% → 100% (blast radius เล็ก)
- C) ไม่ต้องมี monitoring เลย เพราะระบบปลอดภัยอยู่แล้ว
- D) เหมาะกับระบบที่กู้ rollback ไม่ได้

### A9. Infrastructure as Code (IaC) — คุณสมบัติที่ *สำคัญที่สุด* คือ? [IaC]
- A) เขียนด้วย HCL เท่านั้น
- B) Versioned + reproducible — infra อยู่ใน git, review ได้, สร้างซ้ำได้เหมือนกันทุกครั้ง
- C) ต้องใช้ Terraform เท่านั้น
- D) ใช้ได้กับ cloud เท่านั้น

### A10. IaC / Secrets — วิธีจัดการ Secrets ที่ถูกต้องที่สุดคือ? [IaC]
- A) เก็บ `DB_PASSWORD = "supersecret123"` ไว้ในโค้ด เพื่อให้ทีมเห็นง่าย
- B) ฝาก secret ไว้ใน Git history เผื่อลืม
- C) ใช้ `os.environ["DB_PASSWORD"]` + เก็บค่าจริงใน CI/CD Secrets (GitHub Secrets / Vault / AWS Secrets Manager) — ไม่ commit ลง git
- D) เขียน secret ลงใน Dockerfile เพื่อให้ build ผ่านเสมอ

---

## Section B: Reflection (ไม่นับคะแนน — ส่งเป็น reflect.md)

**B1. Apply — CI Workflow Plan (2–3 ประโยค)** ออกแบบ `.github/workflows/ci.yml` สำหรับโปรเจกต์ของทีม:
- **Jobs**: lint → test → build (parallel/sequential + `needs`)
- **Fail-fast**: ใส่ lint ก่อน, cache dependencies, coverage threshold
- **Target**: pipeline < 10 นาที

*Starter สำหรับ Lab 10 exercise 10.1 (CI Workflow)*

**B2. Connect — CD Pipeline Plan (2–3 ประโยค)** เลือก deployment strategy สำหรับทีม + อธิบายเหตุผล:
- **Strategy**: Blue-Green / Canary / Feature Flags (เลือก 1 แบบ)
- **Rollback**: จะทำอย่างไรถ้า deploy ล้มเหลว
- **Monitoring**: metric อะไรที่จะดูหลัง deploy (error rate, latency)

*Starter สำหรับ Lab 10 exercise 10.3 (CD Pipeline)*

**B3. Reflect — IaC Plan (1–2 ประโยค)** ระบุ **1 level** ของ IaC ที่ทีมจะใช้ใน Sprint หน้า + เหตุผล:
- **Level**: Dockerfile (L1) / Compose (L2) / Terraform (L3)
- **Why**: ทำไม level นี้ถึงเหมาะกับโปรเจกต์ตอนนี้

*Starter สำหรับ Lab 10 exercise 10.4 (IaC Practice)*

> วิธีส่ง: สร้าง branch `feature/post-quiz-10` → สร้าง `reflect.md` ที่ root → commit + push + เปิด PR (จะ merge พร้อม Lab 10)

---

## เฉลย (Answer Key) — ห้ามเปิดดูก่อนสอบ

| ข้อ | ตอบ | อธิบายสั้น + อ้างอิง |
|-----|-----|----------------------|
| A1 | **B** | CALMS = Culture, Automation, **Lean**, Measurement, Sharing (Edwards & Willis; ESP §10.2.2) |
| A2 | **C** | DORA 4 metrics: Deployment Frequency, Lead Time, Change Failure Rate, MTTR — **ไม่รวม Code Coverage** (Forsgren et al., *Accelerate*, 2018; ESP §10.2.3) |
| A3 | **A** | Delivery ต้อง manual approval; Deployment = อัตโนมัติ (Humble & Farley, *Continuous Delivery*, 2010; ESP §10.4.1) |
| A4 | **C** | CI ต้อง fast feedback < 10 นาที — 30 นาทีไม่ใช่ best practice (ESP §10.3.3) |
| A5 | **B** | Trunk-based: commit บ่อยลง trunk/main ด้วย short-lived branches + ทุก commit ผ่าน CI (Fowler, 2006; ESP §10.3.2) |
| A6 | **B** | Lint → Test → Build → Deploy คือลำดับ fail-fast + gated (ESP §10.3.3; GitHub Actions docs) |
| A7 | **A** | Blue-Green: 2 env + switch traffic + instant rollback (Humble & Farley, 2010; ESP §10.4.2) |
| A8 | **B** | Canary: ปล่อย % เล็กๆ ก่อน ดู metrics แล้วค่อยเพิ่ม — blast radius เล็กกว่า Blue-Green (ESP §10.4.2) |
| A9 | **B** | IaC ต้อง versioned + reproducible (Kief Morris; ESP §10.5.1) |
| A10 | **C** | Secret ต้องไม่อยู่ใน git/โค้ด — ใช้ env var + Secrets Manager (12-Factor App; ESP §10.5.4) |

> หมายเหตุ: A1–A10 ครอบคลุมครบ 5 หมวดตามโจทย์ — DevOps (A1,A2) · CI/CD (A3,A7,A8) · IaC (A9,A10) · Branching (A5) · Pipeline (A4,A6)
