# บทที่ 2
# กระบวนการพัฒนาซอฟต์แวร์แบบ Agile (สัปดาห์ที่ 2)

> *\"Agile is not a noun; Agile is how you do things.\"*
> — Andrew Hunt & David Thomas, *The Pragmatic Programmer* (Tip 83)

---

## 2.0 บทนำ — เมื่อต้องส่งของในสองสัปดาห์ แผนสามเดือนจึงไร้ค่า

> *\"It is not the strongest of the species that survives, nor the most intelligent, but the one most responsive to change.\"*
> — Leon C. Megginson (paraphrasing Darwin)

บทที่ 1 สอนให้คิดว่า "ทำไม" — บทนี้สอนให้ทำ "อย่างไร" เมื่อต้องการคำตอบจากผู้ใช้ก่อนทุ่มงบ เมื่อต้องส่งงานทุกสองสัปดาห์ เมื่อทีมต้องรู้ว่า "ใครทำอะไร เสร็จเมื่อไหร่" — Agile ตอบคำถามเหล่านี้

แต่ Agile ก็มีราคา บางองค์กรใช้แล้วล้ม บางทีมทำตามชื่อพิธีกรรมแต่ขาดแก่น บางบริษัทเลือกเพราะเทรนด์แทนที่จะดูว่าเหมาะกับบริบทไหม

### เรื่องจริงที่สอนเรื่อง "วิธีทำงาน"

**1) Waterfall ล้มเหลวครั้งใหญ่ (FBI Virtual Case File, 2005) — $170 ล้านทิ้ง**

FBI ว่าจ้าง SAIC สร้างระบบจัดการคดี (Virtual Case File, VCF) ด้วย Waterfall — ใช้เวลา 4 ปี งบ **$170 ล้าน** แล้วล้มเหลว FBI ยกเลิกสัญญาและเริ่มใหม่ทั้งหมดด้วย Agile ต้นเหตุหลัก: requirements เปลี่ยนระหว่างทาง (911 เกิดขึ้น) แต่ Waterfall ไม่ยืดหยุ่น

บทเรียน: ถ้า requirements เปลี่ยน Waterfall = แพ้ Waterfall เหมาะกับงานที่ "เข้าใจครบ" ตั้งแต่ต้น — งานที่ "ต้องเรียนรู้ระหว่างทาง" ไม่เหมาะ (ดู 2.2)

**2) Scrum ที่ Toyota (ใช้มาตั้งแต่ 1950s) — เก่ากว่าที่คิด**

Toyota เริ่มใช้ Sprint แบบ weekly planning ตั้งแต่ปี 1950 โดย Taiichi Ohno ที่เรียกว่า "Ohno Circle" — เกิดขึ้นก่อน Ken Schwaber จะชูคำว่า "Scrum" เสียอีก Scrum ไม่ใช่นวัตกรรมของ Silicon Valley — เป็นหลักการที่โรงงานใช้มานาน เพียงแต่ Silicon Valley หยิบมาเขียนใหม่เป็น framework

บทเรียน: Agile ไม่ใช่ของใหม่ เป็นการตั้งชื่อใหม่ให้หลักการเก่า (ดู 2.2, 2.4)

**3) Spotify Model Cargo Cult (2012–2018) — ทำตาม Spotify แล้วพัง**

Spotify เผยแพร่ "Spotify Model" (Squads, Tribes, Chapters, Guilds) ปี 2012 — บริษัททั่วโลกคัดลอกไปใช้ แต่ปี 2018 Henrik Kniberg (ผู้เขียนเอง) ออกมาบอก *"Don't copy the Spotify Model. The whole point is that we are not even using it anymore"* — คัดลอกโครงสร้างโดยไม่เข้าใจหลักการเบื้องหลัง = Cargo Cult

บทเรียน: "ชื่อ" ไม่ใช่ "หลักการ" ทีมควรถาม "หลักการเบื้องหลังคืออะไร" แทน "ต้องทำตาม Spotify ไหม" (ดู 2.6)

**4) Spotify 2012 — ทำไม Agile ที่ Spotify ถึง work**

Spotify ส่ง **40+ ทีม** ทำงานขนานกันบน product เดียว ทุกสัปดาห์ทุกทีม ship feature เล็ก ๆ เข้า production วัฒนธรรม "trust over control" — ผู้จัดการไม่บอกทีมว่าทำอะไร ทีมตัดสินใจเอง เพราะ Spotify เชื่อว่า **คนที่อยู่ใกล้ปัญหารู้ดีที่สุด**

บทเรียน: Agile work ที่ Spotify เพราะ **วัฒนธรรม** ไม่ใช่ "ชื่อพิธีกรรม" — ถ้าองค์กรไม่มี "trust" ก็จะเกิด Agile ไม่ได้ (ดู 2.6)

**5) Microsoft Windows Vista (2006) — กระบวนการไม่เหมาะกับบริบท**

Vista ใช้ waterfall 5 ปี ใช้พนักงาน 9,000 คน งบประมาณหลายพันล้าน — ออกมาทั้งช้า ทั้งไม่ตรงใจผู้ใช้ Microsoft เปลี่ยนเป็น Agile หลังจากนั้น — แต่บางทีมยังคง waterfall สำหรับระบบปฏิบัติการ (Windows มี release cycle 3-5 ปี) ทั้งสองกระบวนการอยู่ร่วมกันได้

บทเรียน: ไม่มีกระบวนการเดียวที่ดีที่สุด Agile กับ Waterfall อยู่ร่วมกันได้ถ้าเลือกให้เหมาะกับงาน (ดู 2.2, 2.6)

> **Pattern**: ทั้งห้าเคสสอนเรื่องเดียวกัน — **บริบทต่างกัน ต้องเลือกวิธีต่างกัน** Waterfall ล้มเหลวไม่ใช่เพราะ Waterfall ไม่ดี แต่เพราะใช้ผิดที่ Agile ทำงานได้ไม่ใช่เพราะ Agile วิเศษ แต่เพราะเลือกให้เหมาะ

> *แหล่งอ้างอิงที่ตรวจสอบได้:*
> - FBI VCF: [Government Accountability Office, GAO-05-1019, 2005](https://www.gao.gov/products/gao-05-1019) · [Wired, "FBI's Virtual Case File: 'Worst IT Project'", 2005](https://www.wired.com/2006/03/fbi-virtual-case/)
> - Toyota Ohno Circle: [Shook, *Managing to Learn*, 2008](https://www.lean.org/books/misc-books/management-to-learn/) · [Ohno, *Toyota Production System*, 1988]
> - Spotify Cargo Cult: [Kniberg, 2018 — "Spotify Engineering Culture"](https://web.archive.org/web/2018*/spotify.com/engineering)
> - Windows Vista: [TechRadar, 2007 — "What went wrong with Windows Vista"](https://www.techradar.com/news/computing/pc/what-went-wrong-with-windows-vista-706015)

### Mindset Shift

| เดิม | ใหม่ |
|---|---|
| ทำงานตามแผนที่วางไว้ตอนต้น 6 เดือน | ทำงานตามข้อมูลที่ได้ตอนสัปดาห์นี้ (2.2) |
| เขียนเอกสารก่อนเขียนโค้ด | ส่งของทำงานได้ ส่งเอกสารที่จำเป็น (2.3) |
| มี "หัวหน้า" ที่สั่งงาน | มี Scrum Master ที่ขจัดอุปสรรคให้ทีม (2.4) |
| "Done" = "โค้ดเขียนเสร็จ" | "Done" = ผ่าน Definition of Done ของทีม (2.4) |
| ใช้ Agile เพราะเทรนด์ | ใช้ Agile เมื่อ requirements ไม่แน่นอน ไม่ใช้เมื่อ requirements ตายตัว (2.6) |

### Roadmap ของคาบนี้

**2.1 แผนบริหารการสอน** — Post-quiz Pattern 90 นาที · **2.2 Waterfall → Agile (20 นาที)** — วิวัฒนาการ และเมื่อไหร่เหมาะ · **2.3 Agile Manifesto (15 นาที)** — 4 ค่านิยม + 12 หลักการ · **2.4 Scrum (25 นาที)** — 3 บทบาท + 5 พิธีกรรม + DoD · **2.5 XP Practices (15 นาที)** — TDD · Pair Programming · Sustainable Pace · **2.6 เมื่อไหร่ใช้ Agile (15 นาที)** — Cargo Cult + บริบทที่เหมาะ · **2.7 Post-quiz (15 นาที)** — 5 MCQ (1.5%)

บทที่ 3 จะต่อยอดด้วย Requirements ใช้ Scrum backlog เพื่อเก็บความต้องการ Lab 2 คือ Sprint Zero — ตั้ง GitHub Projects Board แล้วสร้าง Product Backlog ตัวแรก

**Prerequisites:** แนวคิด Product Mindset จากบท 1 · Git/GitHub · สมาชิกทีม 4–5 คน

**Self-check:** (1) ทีมเคยส่งงานที่ตรงตาม spec แต่ผู้ใช้ไม่ใช้หรือไม่? — นั่นคือสัญญาณที่ Agile พยายามแก้ (2) ถ้าวันนี้ผู้ใช้ขอเปลี่ยน requirement กลาง Sprint ทีมตอบ "ได้" หรือ "ไม่ได้"? — คำตอบควรเป็น "ทำได้ ถ้า adjust Sprint Goal" (3) สมาชิกในทีมรู้ไหมว่าใครกำลังทำอะไร? — ถ้าไม่รู้ = Daily Scrum ช่วยได้

> **คำเตือนจากน้องวิจัย**: Agile ไม่ใช่กล่องสำเร็จรูป — เหมือนบ้านแมวที่ทุกบ้านต่างกัน ขึ้นกับจำนวนแมวและนิสัยของแมวในบ้าน 🐾

---

## 2.1 แผนบริหารการสอนประจำบท

**ระยะเวลา**: 2 ชั่วโมง (บรรยาย) + 2 ชั่วโมง (ปฏิบัติการ) · **สัปดาห์ที่ 2**

### วัตถุประสงค์เชิงพฤติกรรม

เมื่อจบบทนี้ นิสิตสามารถ

1. อธิบายวิวัฒนาการจาก Waterfall สู่ Agile
2. ระบุค่านิยม 4 ข้อของ Agile Manifesto
3. ประยุกต์ Scrum — บทบาท พิธีกรรม ผลงาน
4. เลือก XP practices ที่เหมาะกับทีม
5. วิเคราะห์ทำไม Agile ไม่ใช่ "กล่องสำเร็จรูป"

### โครงสร้างการสอน (Post-quiz Pattern)

| เวลา | กิจกรรม | สื่อ |
|---|---|---|
| 0:15–0:35 | **2.2** Waterfall → Agile (20 นาที) | กรณีศึกษา |
| 0:35–0:50 | **2.3** Agile Manifesto (15 นาที) | ยกตัวอย่าง |
| 0:50–1:15 | **2.4** Scrum (25 นาที) | Sprint simulation |
| 1:15–1:30 | **2.5** XP Practices (15 นาที) | Trade-off Debate |
| 1:30–1:45 | **2.6** เมื่อไหร่ใช้ Agile (15 นาที) | กรณีศึกษา |
| 1:45–2:00 | **Post-quiz** (5 MCQ + 3 reflection, 1.5%) | commit `reflect.md` |

### สื่อ

- ตำรา: [ESP] Ch.2, [SE] Ch.3, [PP] Tip 83
- สไลด์
- Sprint simulation

### การวัดผล

| ส่วน | คะแนน |
|---|:---:|
| Post-quiz | 1.5% |
| Lab 2 | 3.5% |
| รวม | 5% |

---

## 2.2 จาก Waterfall สู่ Agile

ช่วงทศวรรษ 1970–1990 อุตสาหกรรมซอฟต์แวร์ส่วนใหญ่ใช้ **Waterfall** (Royce, 1970) — แบ่งงานเป็น Requirements → Design → Implementation → Verification → Maintenance ทำต่อเนื่อง แทบไม่มีการย้อนกลับ

Waterfall ยืมมาจากอุตสาหกรรมก่อสร้าง — สร้างบ้านต้องออกแบบให้เสร็จก่อนลงเสาเข็ม ลำดับนี้สมเหตุสมผลสำหรับสิ่งก่อสร้างที่ "แก้ยาก" แต่ซอฟต์แวร์ **ต่างจากสิ่งก่อสร้าง** — ซอฟต์แวร์แก้ได้ตลอด (soft-ware = เปลี่ยนรูปได้)

ข้อจำกัดของ Waterfall ที่ค้นพบในทางปฏิบัติ:

- ลูกค้าไม่รู้ว่าต้องการอะไรจนเห็นซอฟต์แวร์ — Requirements ที่เขียนไว้ตอนต้นมักผิด
- การเปลี่ยน requirement ปลายทางมีต้นทุนสูงมาก — ต้องย้อนทุกขั้น
- ลูกค้าเห็นซอฟต์แวร์ครั้งแรกเมื่อส่งมอบ — ถ้าไม่ตรงใจ ต้องเริ่มใหม่
- ความเสี่ยงถูกซ่อนไว้จนถึงตอนส่งมอบ

**FBI Virtual Case File (2005)** คือตัวอย่าง Waterfall ที่ล้มเหลว — ใช้เวลา 4 ปี งบ $170 ล้าน ไม่ส่งมอบ เพราะ requirements เปลี่ยนหลังเหตุการณ์ 9/11 แต่ Waterfall ไม่ยืดหยุ่น

ในปี 2001 ผู้เชี่ยวชาญ 17 คน (Kent Beck, Martin Fowler, Robert C. Martin, Ken Schwaber, Jeff Sutherland) ร่าง **Agile Manifesto** — เน้นว่ากระบวนการต้องตอบสนองการเปลี่ยนแปลง ไม่ใช่ทำตามแผนเคร่งครัด

| มิติ | Waterfall | Agile |
|---|---|---|
| แนวคิดหลัก | ทำตามแผนที่วางไว้ | ตอบสนองการเปลี่ยนแปลง |
| ขั้นตอน | เป็นลำดับ ย้อนกลับยาก | Iterative + Incremental |
| Requirements | ระบุครบก่อนเริ่ม | Evolve ระหว่างทาง |
| เอกสาร | เขียนครบก่อน implement | Working software over comprehensive documentation |
| การส่งมอบ | ส่งครั้งเดียวท้ายสุด | ส่งทุก 2–4 สัปดาห์ |
| ความเหมาะ | Requirements ชัด ไม่เปลี่ยน | Requirements ไม่แน่ชัด |

**ในรายวิชานี้**: เราใช้ Agile เพราะ product ของนิสิตมี requirements ที่ยังไม่ชัด — ต้องทดลอง ปรับ เรียนรู้ ตรงกับจุดแข็งของ Agile

---

## 2.3 Agile Manifesto

### 2.3.1 ค่านิยม 4 ข้อ

Agile Manifesto เนื้อหาสั้น 68 คำ ผู้ลงนาม 17 คนมาจาก background ต่างกัน แต่เห็นพ้องว่า "heavyweight processes" ไม่ตอบโจทย์อีกต่อไป

> **Individuals and interactions** over processes and tools  
> **Working software** over comprehensive documentation  
> **Customer collaboration** over contract negotiation  
> **Responding to change** over following a plan

"over" ไม่ได้แปลว่าสิ่งที่อยู่ทางขวา "ไม่ดี" แต่แปลว่าสิ่งที่อยู่ทางซ้ายมีคุณค่ามากกว่า

- **Individuals and interactions over processes and tools** — เครื่องมือดีมีประโยชน์ แต่การคุยกับเพื่อน 1 ชั่วโมงแก้ปัญหาได้มากกว่าการติดตั้งเครื่องมือใหม่ 3 วัน
- **Working software over comprehensive documentation** — ซอฟต์แวร์ที่ใช้งานได้จริงมีคุณค่ามากกว่าเอกสาร 100 หน้าที่ไม่มีใครอ่าน
- **Customer collaboration over contract negotiation** — สัญญามีความจำเป็นทางกฎหมาย แต่การร่วมมือกับลูกค้าตลอดโปรเจกต์ให้ผลลัพธ์ที่ดีกว่า
- **Responding to change over following a plan** — แผนที่ดีมีประโยชน์ แต่ความสามารถปรับตัวตามสถานการณ์จริงมีคุณค่ามากกว่า

### 2.3.2 ค่านิยมที่สำคัญที่สุดสำหรับนิสิต

**Sustainable Development** (หลักการข้อ 8) — รักษาจังหวะการทำงานที่ยั่งยืน นิสิตหลายคนชอบ "ปั่น" โปรเจกต์ก่อน deadline อดนอน 3 คืน แล้วส่งงาน — นี่คือ anti-pattern ที่ Agile ต่อสู้ เพราะคุณภาพงานจะต่ำ ทีมจะ burnout และไม่สามารถ sustain ได้ตลอด 15 สัปดาห์

**Regular Reflection** (หลักการข้อ 12) — ทีมสะท้อนวิธีการทำงานเป็นประจำและปรับพฤติกรรม Retrospective ทุก Sprint คือ "โอกาส" ที่ทีมจะปรับปรุง ไม่ใช่ "พิธีกรรม"

### 2.3.3 Essence of Agility (PP Tip 83)

> *\"Agile is not a noun. Agile is an adjective. We don't do Agile, we behave agilely.\"*

หลักคิดนี้ท้าทายวัฒนธรรม "Scrum-in-a-Box" — ทำตามชื่อพิธีกรรมแต่ขาดเนื้อหา ตัวอย่าง: ทีมหนึ่งอ้างว่าใช้ Scrum แต่ Daily Standup ทำอาทิตย์ละครั้ง, Iteration ยาว 6–8 สัปดาห์, ไม่มี Demo ให้ผู้ใช้ — นี่คือ **Cargo Cult** ไม่ใช่ Agile

**คำถามทดสอบ**: "ถ้าเราหยุดทำ [พิธีกรรมนี้] 1 Sprint จะเกิดอะไรขึ้น?" — ถ้าคำตอบคือ "ไม่มีอะไรเปลี่ยน" แสดงว่าพิธีกรรมนั้นเป็น Cargo Cult

---

## 2.4 Scrum

### 2.4.1 ที่มา

Scrum พัฒนาโดย Ken Schwaber และ Jeff Sutherland ต้นทศวรรษ 1990 แรงบันดาลใจจากบทความ Takeuchi & Nonaka (1986) — เปรียบการพัฒนาผลิตภัณฑ์กับ Rugby ที่ทีมทั้งทีมทำงานร่วมกัน ("scrum") ต่างจาก "relay race" (Waterfall) ที่ส่งไม้ต่อทีละขั้น

Toyota ใช้ Sprint แบบ weekly planning มาตั้งแต่ปี 1950 (Ohno Circle) — Scrum จึงไม่ใช่นวัตกรรมใหม่ เป็นการหยิบหลักการเดิมมาเขียนเป็น framework

### 2.4.2 บทบาท 3 ตัว

**Product Owner (PO)** — รับผิดชอบคุณค่าทางธุรกิจ
- จัดทำและจัดลำดับ Product Backlog
- ตัดสินใจว่าจะส่งมอบอะไร
- PO บอก "อะไร" (what) แต่ทีมตัดสินใจ "อย่างไร" (how) — ถ้า PO บอกว่า "เขียนโค้ดแบบนี้ ใช้ database ตัวนี้" แสดงว่า PO กำลังล้ำเส้น

**Scrum Master (SM)** — ผู้ดูแลกระบวนการ — เป็น Servant Leader ไม่ใช่หัวหน้าทีม
- อำนวยความสะดวกกิจกรรม
- ขจัดอุปสรรค
- สอน Scrum

**Developers** — คนทำงานส่งมอบ Increment — Self-organizing

### 2.4.3 พิธีกรรม 5 อย่าง

| พิธีกรรม | ระยะเวลา | วัตถุประสงค์ |
|---|---|---|
| Sprint Planning | ≤ 8 ชม. (Sprint 4 สัปดาห์) | วางแผน Sprint ถัดไป |
| Daily Scrum | 15 นาที | ซิงค์งาน + ระบุอุปสรรค |
| Sprint Review | ≤ 4 ชม. | Demo Increment ให้ stakeholder |
| Sprint Retrospective | ≤ 3 ชม. | สะท้อนกระบวนการทำงาน |
| Backlog Refinement | ≤ 10% ของ Sprint | เตรียม Backlog |

Daily Scrum ตอบ 3 คำถาม: เมื่อวานทำอะไร, วันนี้จะทำอะไร, ติดอะไร — ถ้าเกิน 15 นาที = มีบางอย่างผิดปกติ

**Retrospective** คือพิธีกรรมที่ทรงพลังที่สุด แต่ทีมมักละเลย — ถ้าทีมไม่เคยทำ Retrospective ทีมจะ stagnate ทำผิดซ้ำ ๆ ทุก Sprint

### 2.4.4 Definition of Done

DoD คือเกณฑ์ที่ทีมตกลงร่วมกันว่า "เสร็จ" หมายถึงอะไร Sommerville แนะนำ DoD 5 ข้อ: Reviewed · Unit tested · Integrated · Integration tested · Accepted

ถ้าไม่มี DoD แต่ละคนตีความ "เสร็จ" ต่างกัน — Dev บอก "โค้ดเขียนจบ", QA บอก "test ผ่าน", PO บอก "deploy ได้" DoD ทำให้ทุกคนนิยามเดียวกัน

### 2.4.5 Velocity และ Burnup/Burndown

**Velocity** = story points ที่ทีมทำเสร็จต่อ Sprint ใช้วางแผน Sprint ถัดไป ไม่ใช่ตัวเปรียบเทียบระหว่างทีม

**Burndown Chart** แสดงงานที่เหลือใน Sprint ตามเวลา · **Burnup Chart** แสดงงานที่เสร็จเทียบขอบเขตรวม — Burndown ที่ "สวย" ไม่ได้แปลว่าทีมทำงานดี อาจแปลว่า estimate เกินจริง สิ่งที่สำคัญคือ "เส้นจริง" ที่สะท้อนสถานการณ์จริง

---

## 2.5 Extreme Programming

XP พัฒนาโดย Kent Beck ทศวรรษ 1990 ขณะทำงานที่ Chrysler C3 XP เน้น **แนวปฏิบัติทางเทคนิค** — เอาสิ่งที่ "ดี" มาทำให้สุด ๆ Review ที่ดี → Pair Programming · Testing ที่ดี → TDD · Integration ที่ดี → Continuous Integration

### แนวปฏิบัติหลัก

| หมวด | แนวปฏิบัติ |
|---|---|
| การวางแผน | Planning Game · Small Releases |
| การจัดการ | Sustainable Pace · Whole Team |
| การออกแบบ | Simple Design · Refactoring |
| การเขียนโค้ด | Pair Programming · Collective Code Ownership · Coding Standards |
| การทดสอบ | Test-Driven Development · Continuous Integration |

XP practices ไม่ใช่ "กฎ" ที่ต้องทำทั้งหมด — ทีมเลือกได้ (Pick-and-Mix) แต่ต้องมีเหตุผล

**ในรายวิชานี้** แนะนำ:

- **Sustainable Pace** — ไม่อดนอนทำโปรเจกต์
- **Coding Standards** — ตกลงกันเรื่อง naming convention, folder structure ตั้งแต่ Sprint 0
- **Small Releases** — commit ทุกวัน ไม่ใช่ "หายไปแล้ว push ครั้งใหญ่"

### Pair Programming ในรายวิยว

Pair Programming คือเขียนโค้ด 2 คน 1 เครื่อง **Driver** (พิมพ์ คิดเรื่อง syntax) และ **Navigator** (ดู คิดเรื่อง scope, design, edge cases) สลับหน้าที่ทุก 20–30 นาที

ข้อจำกัด: ใช้เวลา 1.5–2 เท่า · อาจไม่ work กับ developer บางคู่ · ไม่เหมาะกับงาน routine

---

## 2.6 เมื่อไหร่ใช้ Agile

### 2.6.1 Cargo Cult Agile

> *\"Cargo cult programming\" — Fred Brooks, *The Mythical Man-Month* (1975) — เลียนแบบรูปแบบแต่ไม่มีเนื้อหา*

Cargo Cult หมายถึงทีมที่:
- ทำ Daily Standup ทุกเช้า (เพราะ "ต้องทำ") แต่ไม่ได้ซิงค์งานจริง ๆ
- มี Sprint Backlog (เพราะ "ต้องมี") แต่ไม่ได้ตกลงร่วมกัน
- ใช้ Scrum (เพราะ "เทรนด์") แต่ iteration ยาว 6–8 สัปดาห์

Spotify Model (2012) คือตัวอย่าง — บริษัททั่วโลกคัดลอก Squads/Tribes/Chapters/Guilds แต่ปี 2018 Henrik Kniberg (ผู้เขียนเอง) บอก *"Don't copy the Spotify Model. The whole point is that we are not even using it anymore"* คัดลอกโครงสร้างโดยไม่เข้าใจหลักการเบื้องหลัง = Cargo Cult

**วิธีตรวจ**: "ถ้าเราหยุดทำ [พิธีกรรมนี้] 1 Sprint จะเกิดอะไรขึ้น?" — ถ้าคำตอบคือ "ไม่มีอะไรเปลี่ยน" = Cargo Cult

### 2.6.2 เมื่อไหร่เหมาะ

Agile เหมาะกับ:

- Requirements ไม่แน่นอน — ลูกค้ายังไม่รู้ว่าต้องการอะไร
- ตลาดเปลี่ยนเร็ว — ต้อง feedback เร็ว ปรับตัวเร็ว
- ทีม 3–12 คน — สื่อสารได้ง่าย
- ลูกค้าพร้อมมีส่วนร่วม
- วัฒนธรรม trust-based

ในรายวิชานี้: product ของนิสิตตรงกับทุกข้อ — requirements ยังไม่ชัด, ทีม 4–5 คน, ลูกค้า (เพื่อนร่วมชั้น) พร้อมให้ feedback

### 2.6.3 เมื่อไหร่ไม่เหมาะ

Agile **ไม่** เหมาะกับ:

- Requirements ตายตัว — ระบบ regulatory เคร่ง
- Distributed teams 50+ คน — ประสานงานยาก
- Hardware-software co-design — ต้องทดสอบ hardware ก่อน
- Critical safety systems — เครื่องบิน อุปกรณ์การแพทย์ ต้องผ่าน certification

Microsoft Windows Vista (2006) เป็นตัวอย่าง Waterfall ที่ล้มเหลว — ใช้ 5 ปี พนักงาน 9,000 คน ออกมาทั้งช้าทั้งไม่ตรงใจ Microsoft เปลี่ยนเป็น Agile หลังจากนั้น — แต่บางทีมยังคง waterfall สำหรับ OS ทั้งสองอยู่ร่วมกันได้

**ข้อสรุป**: ไม่มีกระบวนการที่ดีที่สุด มีแต่กระบวนการที่เหมาะกับบริบท หน้าที่ของวิศวกรคือ **เลือกเครื่องมือให้เหมาะกับงาน** ไม่ใช่ทำตามกระแส

---

## 2.7 Post-quiz (ท้ายคาบ 1:45–2:00, 1.5%)

### Section A: เลือกคำตอบที่ถูกต้องที่สุด (5 ข้อ × 0.3 = 1.5 คะแนน)

**A1.** Agile Manifesto (2001) มีค่านิยมกี่ข้อ
- A) 2
- B) 4
- C) 7
- D) 12

**A2.** Scrum Master เป็นอะไร
- A) Project Manager
- B) Servant Leader (ผู้นำเชิงบริการ)
- C) Product Owner
- D) Tech Lead

**A3.** Sprint มีระยะเวลา timeboxed กี่สัปดาห์
- A) 1 สัปดาห์
- B) 2–4 สัปดาห์
- C) 1 เดือน
- D) ตามที่ทีมต้องการ

**A4.** Definition of Done ประกอบด้วยกี่ข้อ
- A) 3
- B) 5
- C) 7
- D) 10

**A5.** ข้อใดเป็น XP Practice ทั้งหมด
- A) Pair Programming
- B) Sustainable Pace
- C) Continuous Integration
- D) ถูกทุกข้อ

### เฉลย

- **A1. B** — 4 ค่านิยม (Beck et al. 2001)
- **A2. B** — Servant Leader ไม่ใช่หัวหน้าทีม (Schwaber & Sutherland 2020)
- **A3. B** — 2–4 สัปดาห์ timebox
- **A4. B** — DoD 5 ข้อ: Reviewed, Unit tested, Integrated, Integration tested, Accepted
- **A5. D** — ทั้ง 3 ข้อเป็น XP practices

### Section B: Reflection (ไม่นับคะแนน) — ส่งเป็น `reflect.md`

**B1. Apply — Sprint Trade-off (2–3 ประโยค)**

Sprint 2 สัปดาห์ใกล้จบ งานเหลือ 2 stories หัวหน้าทีมเสนอขยาย Sprint ไปอีก 3 วัน
- โต้แย้งด้วยหลักการ Scrum (timebox — Sprint ต้องจบตรงเวลา) อย่างไร
- เสนอทางเลือกอื่นแทนการขยายเวลา 1 ทางเลือก (ลด scope / เพิ่มคนชั่วคราว / ย้าย story ไป Sprint ถัดไป)

**B2. Connect — Cargo Cult (3–4 ประโยค)**

เลือก "Cargo Cult" 1 อย่างจากชีวิตจริง
- pattern (พิธีกรรม) คืออะไร
- ทำไมคิดว่าเป็น Cargo Cult
- จะปรับให้เป็นของจริงได้อย่างไร

**B3. Reflect — Trust Culture (1 ประโยค)**

ถ้าผู้จัดการทีมบอกว่า "ให้รายงานทุกวันว่าทำอะไร" ทีมจะรู้สึก "ถูกตรวจ" หรือ "ได้รับความช่วยเหลือ" — และความรู้สึกนั้นส่งผลต่อ Agile ของทีมอย่างไร

### วิธีส่ง

1. สร้าง branch `feature/post-quiz-2` ใน team repo
2. สร้าง `reflect.md` ที่ root ของ repo
3. Commit + push + เปิด PR (merge พร้อม Lab 2)

---

## 2.8 สรุปสาระสำคัญ

บทที่ 2 ครอบคลุม Agile ตั้งแต่ประวัติจนถึงการใช้งานจริง

- **วิวัฒนาการ** — จาก Waterfall (FBI VCF ล้มเหลว $170M) สู่ Agile Manifesto 2001
- **Manifesto** — 4 ค่านิยม ที่ข้อความ "over" ไม่ได้แปลว่า "ไม่ดี" แต่แปลว่า "มีคุณค่ามากกว่า"
- **Scrum** — 3 บทบาท · 5 พิธีกรรม · DoD · Velocity
- **XP** — Sustainable Pace · Coding Standards · Small Releases (แนะนำสำหรับนิสิต)
- **Cargo Cult** — ทำพิธีกรรมโดยไม่มีเนื้อหา = อันตรายกว่าทำ Waterfall อย่างตั้งใจ
- **บริบท** — ไม่มีกระบวนการเดียวที่ดีที่สุด มีแต่กระบวนการที่เหมาะกับบริบท

FBI ใช้ Waterfall กับงานที่ requirements เปลี่ยน = แพ้ Spotify ก็อบโมเดลที่ไม่เข้าใจ = ล้ม คนที่ทำงานจริงต้อง **เลือกวิธีให้เหมาะกับบริบท** ไม่ใช่เลือกตามแฟชั่น

แนวคิดเหล่านี้จะถูกนำไปใช้ในบทที่ 3 (Requirements — ใช้ Scrum backlog เก็บความต้องการ) Lab 2 คือ Sprint Zero — ตั้ง GitHub Projects Board แล้วสร้าง Product Backlog ตัวแรก

---

## 2.9 คำถามทบทวน

1. เปรียบเทียบ Waterfall กับ Agile ใน 5 มิติ — เมื่อไหร่ควรใช้แบบใด
2. อธิบาย Agile Manifesto 4 ค่านิยม พร้อมยกตัวอย่างจริงในรายวิชา
3. Scrum Master ต่างจาก Project Manager อย่างไร — ทำไมถึงไม่ใช่ "หัวหน้าทีม"
4. Definition of Done สำคัญอย่างไร — ถ้าไม่มีจะเกิดอะไร
5. XP Practice 3 อย่างที่ควรเริ่มใน Sprint แรก — เหตุผล
6. Cargo Cult Agile คืออะไร — วิธีตรวจว่าทีมตกเป็น Cargo Cult
7. Velocity ใช้วัดอะไร — ใช้เปรียบเทียบระหว่างทีมได้ไหม
8. ทำไม Spotify Model ถึงเป็น Cargo Cult เมื่อคัดลอก — Kniberg บอกอะไร

---

## 2.10 แบบฝึกหัด

### 2.1 — Scrum Role Play

แบ่งทีม 4–5 คนเป็น 3 roles (PO, SM, Developers) แล้วเล่น Sprint จำลอง 1 สัปดาห์:
- Sprint Planning 30 นาที — เลือก user stories จาก Product Backlog
- Daily Scrum 5 ครั้ง — คนละ 1 นาทีตอบ 3 คำถาม
- Sprint Review 15 นาที — demo สิ่งที่ทำเสร็จ
- Retrospective 15 นาที — "เราทำอะไรได้ดี / อะไรควรปรับ"

### 2.2 — Cargo Cult Audit

ตรวจทีมของคุณเอง (หรือทีมที่เคยร่วมงาน):
- มีพิธีกรรมใดที่ "ทำแต่ไม่มีคุณค่า"
- ถ้าหยุดพิธีกรรมนั้น 1 Sprint จะเกิดอะไร
- มีทางไหนที่จะปรับให้เป็น "ของจริง"

---

## บรรณานุกรมเพิ่มเติมประจำบท

- Beck, K., et al. (2001). *Manifesto for Agile Software Development*. [agilemanifesto.org](https://agilemanifesto.org/).
- Schwaber, K., & Sutherland, J. (2020). *The Scrum Guide*. [scrumguides.org](https://scrumguides.org/).
- Sommerville, I. (2019). *Engineering Software Products*. Pearson. Chapter 2.
- Sommerville, I. (2016). *Software Engineering* (10th ed.). Pearson. Chapter 3.
- Beck, K. (1999). *Extreme Programming Explained*. Addison-Wesley.
- Brooks, F. (1975). *The Mythical Man-Month*. Addison-Wesley.
- Kniberg, H. (2012). *Spotify Engineering Culture*. Spotify R&D.
- Takeuchi, H., & Nonaka, I. (1986). The New New Product Development Game. *Harvard Business Review*.

---

*จัดทำโดย: ธรรมรัตน์ ธรรมา · สาขาวิทยาการคอมพิวเตอร์ คณะเทคโนโลยีสารสนเทศและการสื่อสาร มหาวิทยาลัยพะเยา · ภาคเรียนที่ 1 ปีการศึกษา 2569*
