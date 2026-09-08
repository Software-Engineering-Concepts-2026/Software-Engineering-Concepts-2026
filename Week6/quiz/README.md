# Quiz 6 — Cloud-Native, Containers & Microservices (Week 6) · 10 ข้อ

> **Post-quiz Pattern** (ท้ายคาบ 15 นาที) · **10 MCQ × 0.15 = 1.5%** · Close-book
> ครอบคลุม: Virtualization, Containers, Docker, Microservices, Cloud-Native (IaaS/PaaS/FaaS, REST, Resilience)
> ตามบทที่ 6: สถาปัตยกรรมบนคลาวด์และไมโครเซอร์วิส — *Cloud is not a place. It's an operating model.* (Werner Vogels)

**อ่านก่อนสอบ:** [ESP] Ch.5 (Cloud-Based Software) · [ESP] Ch.6 (Microservices, REST, Orchestration vs Choreography) · [SE] Ch.17–18 · สไลด์ Week6 + บทที่ 6 (§6.2–6.5) · เคส Netflix / AWS S3 / Prime Video / เป๋าตัง / Canva

---

## Section A: เลือกคำตอบที่ถูกต้องที่สุด (10 ข้อ × 0.15 = 1.5 คะแนน)

**คำชี้แจง:** เลือกข้อที่ถูกต้องที่สุดเพียงข้อเดียว · Bloom 1–2 (Recall + Comprehension) · เวลา 15 นาที ท้ายคาบ (หลังเรียนทฤษฎี)

### A1. [Cloud-Native — Service Models] Cloud Service Model ใดที่ผู้ใช้จัดการ "เฉพาะ application + data" และ provider จัดการ runtime / middleware / OS / infrastructure ทั้งหมด?
- A) IaaS
- B) PaaS
- C) SaaS
- D) FaaS

### A2. [Containers vs VM — Core Difference] ข้อใดคือข้อแตกต่างที่ถูกต้องระหว่าง Container กับ Virtual Machine?
- A) Container แชร์ host kernel; VM มี Guest OS แยก
- B) Container ใหญ่กว่า VM เพราะรวม OS มาด้วย
- C) VM boot เร็วกว่า Container (วินาที vs นาที)
- D) Container ไม่สามารถ standardize image ได้

### A3. [Virtualization — Hypervisor & Isolation] ข้อใดอธิบาย Virtualization ด้วย Hypervisor ได้ถูกต้องที่สุด?
- A) Container ใช้ Hypervisor เพื่อจำลอง hardware — แยกในระดับ process
- B) VM ใช้ Hypervisor จำลองเครื่องทั้งเครื่อง — แต่ละ VM มี Guest OS + kernel แยก — isolation ระดับ hardware, เหมาะกับ shared DB หรือ workload ที่ต้องใช้ OS ต่างกัน; ข้อเสียคือ image ขนาด GB และ boot 2–5 นาที
- C) VM แชร์ host kernel จึงเบากว่า Container
- D) Hypervisor ทำให้ Container กับ VM มีขนาดและ boot time เท่ากัน

### A4. [Docker — Multi-stage Build] ทำไม Dockerfile ในบทที่ 6 (§6.3.3) จึงแนะนำ Multi-stage Build?
- A) เพื่อให้ image มีขนาดใหญ่ขึ้นและรวม build tools ไว้ debug ใน production
- B) เพื่อแยก stage ติดตั้ง dependencies/build ออกจาก stage production — ไม่ให้ gcc/build-base ติดไปใน image ทำให้ image เหลือ ~100 MB แทน ~800 MB และปลอดภัยขึ้น
- C) เพื่อให้ต้องใช้ `USER root` เสมอ
- D) เพื่อให้ไม่ต้องใช้ `.dockerignore`

### A5. [Docker — Image / Container / Registry & Best Practices] ข้อใดถูกต้องเกี่ยวกับ Docker?
- A) Dockerfile คือ running instance, Container คือ recipe, Image เก็บใน Registry
- B) Image คือ read-only ผลลัพธ์จาก `docker build`, Container คือ running instance ของ image, Registry (เช่น Docker Hub / ghcr.io) คือที่เก็บ image; Best practice คือใช้ base เล็ก (`alpine/slim`), ใส่ `USER node/nobody` ไม่ใช้ root, ระบุ `EXPOSE` ตรง port และมี `.dockerignore`
- C) `docker build` ไม่จำเป็นต้องมี Dockerfile
- D) ควรใช้ `python:latest` และรันเป็น root เพื่อให้สิทธิ์ครบ

### A6. [Cloud-Native — FaaS / Serverless & Trade-offs] ข้อใดถูกต้องเกี่ยวกับ FaaS / Serverless?
- A) FaaS เหมาะกับทุก workload — Prime Video ย้ายไป Lambda/Step Functions แล้วต้นทุนลด 90%
- B) FaaS (เช่น AWS Lambda) คือเขียน function เล็กๆ ที่ trigger ด้วย event — เหมาะกับ workload ไม่ต่อเนื่อง/ event-driven และจ่ายเมื่อมี traffic; แต่ workload ที่รันหนักต่อเนื่องอาจเจอ cold start / state passing ยาก จนแพงขึ้น — Prime Video (2023) ย้ายกลับ monolith เพราะต้นทุนพุ่ง ~90%
- C) FaaS คือผู้ใช้ต้องจัดการ OS เองทั้งหมดเหมือน IaaS
- D) Serverless ถูกกว่าเสมอ ไม่ต้องคำนวณต้นทุน

### A7. [Microservices — Rule of Twos] ข้อใดเป็น 1 ใน Microservices Rule of Twos (Sommerville 2019)?
- A) ทุก service ต้อง share database เดียวกัน
- B) Dev/test/deploy cycle ต้อง ≤ 2 สัปดาห์
- C) Service ต้อง stateful เพื่อ performance
- D) ทีมต้องมีอย่างน้อย 50 คน

### A8. [Microservices — When NOT to Use] กรณีใด "ไม่ควร" แยกเป็น microservices ตามคำแนะนำใน §6.4.4?
- A) ทีม 5 คน, domain ยังไม่ชัด, ไม่มี DevOps capability และระบบเป็น banking core ที่ต้องการ ACID ข้าม entity — ควรเริ่มจาก Modular Monolith ก่อน แยกเมื่อ scale จริง (Prime Video เป็นตัวอย่างที่แยกแล้วต้นทุนพุ่งจนต้องย้ายกลับ)
- B) ทีม 8 คน แต่ละ service มี single responsibility และ stateless ชัดเจน, deploy ได้ใน 1 สัปดาห์ — ควรแยกทันที
- C) Service ที่ผ่าน Rule of Twos ครบ 4 ข้อ — ไม่ควรแยก
- D) ระบบที่ traffic พุ่ง 15 เท่าในคืนเดียว — ต้องแยกเป็น microservices ทันทีโดยไม่ต้องประเมิน

### A9. [Cloud-Native — REST] ในการออกแบบ REST API สำหรับ "อัปเดตชื่อ to-do item บางส่วน" ควรใช้ HTTP verb ใด และเมื่อสร้าง resource สำเร็จควรตอบ status ใด?
- A) GET → 200 OK
- B) PUT (แทนทั้ง resource) → 200 OK
- C) PATCH (update partial) → 200 OK; ส่วน POST สร้างใหม่ → 201 Created — และควร versioning ด้วย URI เช่น `/api/v1/todos` เพื่อไม่ให้ break client เก่า
- D) DELETE → 204 No Content

### A10. [Cloud-Native — Resilience: Circuit Breaker & API Gateway] ข้อใดอธิบาย Resilience Patterns ได้ถูกต้องที่สุด?
- A) แก้ failure ด้วยการรอ timeout 10 วินาทีทุก request ก็พอ — ไม่ต้องมี Circuit Breaker
- B) Choreography มี central orchestrator สั่งงาน — ส่วน Orchestration ใช้ events
- C) Circuit Breaker มี 3 สถานะ Closed (ปล่อยผ่าน + นับ failure) → Open (ตัดวงจรทันที return fallback ไม่รอ timeout) → Half-Open (probe ว่าฟื้นหรือยัง); ส่วน API Gateway เป็น single entry point ทำ routing/aggregation/auth/rate limiting/logging — ต้องทำ HA เพราะเป็น single point of failure (§6.5.5)
- D) API Gateway อยู่ระหว่าง service → service ส่วน Circuit Breaker อยู่ที่ edge ระหว่าง client กับระบบ

---

## เฉลย (Answer Key) — ห้ามเปิดดูก่อนสอบ

| ข้อ | คำตอบ | เหตุผลย่อ + อ้างอิง |
|:---:|:---:|---|
| A1 | **B** | PaaS — ผู้ใช้จัดการเฉพาะ application + data; IaaS จัดการ OS ขึ้นไป, SaaS ใช้สำเร็จรูป, FaaS = event-driven function (ESP §5.2 / §6.2.1) |
| A2 | **A** | Container แชร์ host kernel (OS-level virtualization via namespaces/cgroups) — เบา MB boot <1s; VM มี Guest OS แยก boot 2–5 นาที overhead สูง (ตาราง 6.1) |
| A3 | **B** | VM = Hypervisor จำลองเครื่องทั้งเครื่อง hardware-level isolation เหมาะ shared DB / OS ต่างกัน แลกกับขนาด GB + boot ช้า; Container = process-level ( §6.3.1–6.3.2) |
| A4 | **B** | Multi-stage แยก deps/build ออก — image production เล็กลง ~100 MB จาก ~800 MB ปลอดภัยขึ้น (§6.3.3 ตัวอย่าง Dockerfile node:20-alpine) |
| A5 | **B** | Dockerfile(recipe) → Image(read-only) → Container(running) → Registry(Docker Hub/ghcr.io); Best practice: alpine/slim + USER non-root + EXPOSE + .dockerignore (§6.3.3) |
| A6 | **B** | FaaS เหมาะ event-driven ไม่ต่อเนื่อง จ่ายตามใช้งาน แต่ workload หนักต่อเนื่องเจอ cold start / state passing → แพง — Prime Video กลับ monolith ต้นทุนพุ่ง 90% (§6.2.1, 6.4.4) |
| A7 | **B** | Rule of Twos: Single responsibility · Stateless · ≤2 weeks dev/test/deploy · ≤2 pizzas team (≤8–10 คน) (ESP §6.3 / ตาราง 6.2) |
| A8 | **A** | ไม่ควรแยกเมื่อ: banking ACID ข้าม entity, ทีมเล็ก <5, domain ไม่ชัด, ไม่มี DevOps — เริ่ม Modular Monolith ก่อน (§6.4.4) |
| A9 | **C** | PATCH = partial update, PUT = replace ทั้ง resource; POST สร้าง → 201 Created; versioning นิยม URI `/api/v1/...` (§6.5.1–6.5.3) |
| A10 | **C** | Circuit Breaker Closed→Open→Half-Open = fail fast กัน cascading failure; API Gateway = edge single entry (routing/auth/rate limiting) ต้อง HA (§6.5.5) — ตัวเลือก D สลับที่กัน |

> **การกระจายตามหัวข้อ:** Virtualization (A2, A3) · Containers (A2, A3) · Docker (A4, A5) · Microservices (A7, A8) · Cloud-Native (A1, A6, A9, A10) — 5 กลุ่มครบตามโจทย์ โดย A2 คร่อม Virtualization/Containers

---

## Section B: Reflection (ไม่นับคะแนน — เขียนหลังทำ Lab06 เสร็จ → ส่งเป็น reflect.md)

> **เมื่อไหร่ทำ:** หลังทำ Lab06 ทั้ง 5 ขั้นเสร็จแล้ว — เปิด `reflect.md` แล้วเขียนสะท้อนสิ่งที่เพิ่งทำ (ดูตัวอย่างที่ `labs/guides/Post-quiz-6-Example.md` และ `labs/examples/lab06-sample-solution/reflect.md`)

**B1. Apply — Dockerfile draft (3–5 บรรทัด — เขียนหลังทำ Lab ขั้น 2 เสร็จ)**

ทำอย่างไร (หลัง Lab ขั้น 2 เสร็จ):
1. เปิด `Dockerfile` ที่เพิ่งเขียนใน Lab — copy 3–5 บรรทัดสำคัญมา (FROM + WORKDIR + COPY + EXPOSE + USER)
2. เทียบกับ draft ที่ร่างก่อน Lab — อะไรเปลี่ยน (เช่น ก่อน Lab ใช้ `python:latest` หลัง Lab เปลี่ยนเป็น `python:3.12-slim` + เพิ่ม multi-stage)

เขียนตอบ 3 อย่าง (สะท้อนหลังทำ Lab):
- **Draft ก่อน Lab:** ใช้ base อะไร + มี USER/EXPOSE ไหม (เช่น `python:3.12-slim` + `USER nobody` + `EXPOSE 8000`)
- **หลังทำ Lab refine อะไร:** เช่น เพิ่ม Stage 2 ทำให้ image เหลือ ~145 MB จาก 800 MB, pin version `3.12-slim` ไม่ใช้ `:latest`
- **ทำไมเลือก base นี้:** เช่น slim เล็ก 120 MB + ปลอดภัย (USER nobody) — อ้าง ESP §7

ตัวอย่างที่ดี / ไม่ดี: ดู `labs/guides/Post-quiz-6-Example.md` หัวข้อ B1

**B2. Connect — Microservices Decision (2–3 ประโยค — เขียนหลังทำ Lab ขั้น 1 เสร็จ)**

เลือก **1 service จริง** ที่เพิ่ง containerize ใน Lab ขั้น 1:

เขียนตอบ 3 อย่าง (สะท้อนหลังทำ):
- **เลือก service ไหน:** ชื่อ + หน้าที่ (เช่น Campus Eats API สั่งอาหาร)
- **Rule of Twos 4 ข้อ — ผ่าน/ไม่ผ่านแต่ละข้อ:** Single responsibility (ทำอย่างเดียวไหม) / Stateless (state ไป DB ไหม) / ≤2 weeks (deploy ได้ใน 2 สัปดาห์ไหม) / ≤2 pizzas (ทีม ≤10 คนไหม) — บอกผ่าน/ไม่ผ่านแต่ละข้อ
- **สรุป:** 4 ข้อผ่านหมด → แยกเป็น microservice ได้ / ถ้าข้อใดตก → ควรเป็น Modular Monolith ก่อน (§6.4.4)

ตัวอย่างที่ดี / ไม่ดี: ดู `labs/guides/Post-quiz-6-Example.md` หัวข้อ B2

**B3. Reflect — Circuit Breaker Scenario (1–2 ประโยค — เขียนหลังทำ Lab ทั้งหมดเสร็จ)**

หลังทำ Lab06 ทั้ง 5 ขั้นแล้ว ถ้า service หนึ่งในโปรเจกต์ล่ม:

เขียนตอบ 2 อย่าง:
- **เลือก service จริง + fail fast หรือ fail slow:** เช่น Payment service ล่ม → เลือก **fail fast** (Circuit Breaker Open → return fallback "ชำระเงินไม่สำเร็จ กรุณาลองใหม่" ทันที) ไม่ใช่ fail slow (รอ timeout 10s ทุก request)
- **เหตุผล + fallback:** cascading delay ทำให้ผู้ใช้หนีและ Order service ล่มตาม — ใช้ Half-Open probe ว่าฟื้นหรือยัง (§6.5.5)

ตัวอย่างที่ดี: `ถ้า Payment service ล่ม — fail fast (Open → fallback ทันที) ไม่ใช่ fail slow (รอ 10s) — เพราะ cascading delay ทำให้ Order service ล่มตาม — ใช้ Half-Open probe`
ตัวอย่างที่ไม่ดี: `ควรใช้ Circuit Breaker` (ไม่บอก service ไหน ไม่บอก fallback)

> **เกณฑ์ที่อาจารย์ดู (Section B ไม่นับคะแนน แต่ต้องผ่าน — เขียนหลัง Lab):** B1 ต้องมี Dockerfile 3–5 บรรทัด + base pin version + USER + EXPOSE + เหตุผล / B2 ต้องตอบครบ 4 ข้อ + ผ่าน/ไม่ผ่าน + สรุป / B3 ต้องระบุ service จริง + fail fast/slow + เหตุผล + fallback — ถ้าไม่ครบจะให้แก้ก่อน merge PR

**ตัวอย่าง `reflect.md` ที่ส่งจริง (เขียนหลัง Lab):**

```markdown
# Post-quiz 6 — Reflection (เขียนหลังทำ Lab06)
**ชื่อ:** สมชาย ใจดี — **ทีม:** Campus Eats — **Sprint:** 6

## B1. Apply — Dockerfile draft (หลังทำ Lab)
ร่าง Dockerfile จาก Post-quiz ใช้ python:3.12-slim + EXPOSE 8000 + USER nobody — หลังทำ Lab refine เป็น multi-stage จริง: Stage 1 ติดตั้ง dependencies ด้วย pip install --no-cache-dir แล้ว Stage 2 copy เฉพาะ site-packages + main.py ทำให้ image เหลือ ~145 MB (จาก 800 MB ถ้าไม่แยก stage) — Pin version 3.12-slim ไม่ใช้ :latest เพื่อให้ build วันนี้กับพรุ่งนี้ได้ผลเดียวกัน

## B2. Connect — Microservices Decision (หลังทำ Lab)
API สั่งอาหารของทีม: Single responsibility — ทำเรื่องสั่งอาหารอย่างเดียว (ผ่าน), Stateless — state อยู่ใน Postgres ไม่เก็บใน memory (ผ่าน), ≤2 weeks — มี Dockerfile + CI พร้อม deploy ได้ในวันเดียว (ผ่าน), ≤2 pizzas — ทีม 5 คน (ผ่าน) → 4 ข้อผ่านหมดจึงแยกเป็น microservice ได้ ถ้าข้อใดตกจะเริ่มจาก Modular Monolith ก่อนตามคำแนะนำ §6.4.4

## B3. Reflect — Circuit Breaker Scenario (หลังทำ Lab)
ถ้า Payment service ล่ม — ทีมเลือก fail fast (Circuit Breaker Open → return fallback "ชำระเงินไม่สำเร็จ กรุณาลองใหม่" ทันที) ไม่ใช่ fail slow (รอ timeout 10 วินาทีทุก request) — เพราะ cascading delay ทำให้ผู้ใช้หนีและ Order service ก็ล่มตามไปด้วย — ใช้ fallback + Half-Open probe ว่าฟื้นหรือยัง
```

### วิธีส่ง

1. ทำ Lab06 ทั้ง 5 ขั้นให้เสร็จก่อน
2. สร้าง branch `feature/post-quiz-6` (หรือใช้ branch เดียวกับ Lab `feature/lab6-dockerfile`)
3. สร้าง `reflect.md` ที่ root (copy โครงข้างบนแล้วเติมคำตอบหลังทำ Lab)
4. Commit + push + เปิด PR (merge พร้อม Lab 6)

> **ดูตัวอย่างเต็ม:** `labs/guides/Post-quiz-6-Example.md` — มีตัวอย่างที่ดี/ไม่ดี + เกณฑ์ตรวจ
