# บทที่ 1
# แนะนำรายวิชาและปรัชญาวิศวกรรมซอฟต์แวร์ (สัปดาห์ที่ 1)

> *\"In the rush to add yet another feature, yet another product, yet another layer of abstraction, it's easy to forget that what we're really doing is trying to make our lives easier.\"*
> — Andrew Hunt & David Thomas, *The Pragmatic Programmer* (2019)

---

## 1.0 บทนำ — ทำไม "เขียนโค้ดเป็น" ไม่พอ แต่ต้องคิดให้เป็นด้วย

> *\"It is not the language that makes programs appear simple, but the programmer.\"*
> — Hal Abelson, *Structure and Interpretation of Computer Programs*

โปรเจกต์แรกของหลายคนคือ "ทำให้มันทำงาน" รายวิชานี้เปลี่ยนคำถามเป็น "ทำไมมันต้องทำงาน ทำงานเพื่อใคร และจะอยู่ต่อไปได้อย่างไร" วิศวกรซอฟต์แวร์ที่ดีต้องคิดเรื่อง **ชีวิตของผลิตภัณฑ์** ไม่ใช่แค่ชีวิตของฟีเจอร์

ปี 2026 เราส่งงานได้ในไม่กี่วินาทีด้วย Generative AI แต่โปรเจกต์ใหญ่ ๆ ที่ล้มเหลวไม่ได้ล้มเพราะโค้ดเขียนไม่เป็น ล้มเพราะ **คิดไม่เป็น**

### เรื่องจริงที่สอนเรื่อง "คิดไม่เป็น"

**1) Theranos (2003–2018) — เครื่องตรวจเลือดที่ไม่เคยทำงาน**

Theranos อ้างว่าเครื่อง Edison ตรวจเลือดจากหยดเดียวได้ 240+ รายการ — ผลลัพธ์จริงส่วนใหญ่รันบนเครื่อง Siemens มาตรฐานที่ซื้อมา ทีม engineer รู้แต่ถูกกดดันให้เงียบ Holmes สร้างวัฒนธรรม "ห้ามถาม" พนักงานที่ตั้งคำถามถูกมองว่า "ไม่เชื่อ mission" — ผลลัพธ์: ผู้ป่วยหลายพันคนได้ผลตรวจผิด บริษัทล้มละลาย Holmes ถูกตัดสินจำคุก **11 ปี** (2022)

บทเรียน: คนที่รู้ว่า product เป็นอันตรายแล้วเงียบ = มีส่วนร่วม ต้อง "กล้าพูด" ก่อนที่เรื่องจะใหญ่โต (ดู 1.5)

**2) Knight Capital (2012) — deploy ผิด บริษัทล้มใน 45 นาที**

Knight Capital deploy ระบบซื้อขายหุ้นใหม่โดยไม่ได้ run regression test ในสภาพ production-like โค้ดใหม่ไป **activate flag เก่าที่ dormant มา 8 ปี** อัลกอริทึมซื้อขายผิดต่อเนื่อง ขาดทุน **440 ล้านดอลลาร์ใน 45 นาที** ล้มละลายวันรุ่งขึ้น

บทเรียน: บั๊กที่ "ดูเล็ก" ในสภาพจริงอาจกลายเป็นหายนะได้ใน 1 ชั่วโมง "ดีพอ" ไม่ใช่ "พอทดสอบในห้อง" แต่คือ "พอเมื่อใช้งานจริง" (ดู 1.3)

**3) Healthcare.gov (2013) — สัญญา 60 ฉบับ ไม่มีคนรับผิดชอบ**

เว็บลงทะเบียนประกันสุขภาพของสหรัฐฯ ล่มตั้งแต่เปิดตัว ผู้ใช้กว่า 60% กดสมัครไม่ได้ สืบพบว่ามี **สัญญาย่อย 60 ฉบับ** กับบริษัท แต่ละเจ้าเขียนโค้ดคนละส่วน **ไม่มี lead integrator** — ไม่มีใครรับผิดชอบภาพรวม ใช้เวลา 1 ปีแก้ งบบานปลายจาก $93 ล้านเป็น **$1.7 พันล้าน**

บทเรียน: จำนวน contractor ไม่ได้แก้ปัญหา ถ้าไม่มีคนรับผิดชอบ end-to-end ต่างคนต่างทำ ไม่มีใครเห็นภาพรวม (ดู 1.3)

**4) Boeing 737 MAX (2018–2019) — เขียนโค้ดถูก แต่ออกแบบขั้นตอนผิด**

MCAS ระบบช่วยบินของ Boeing อ่าน sensor เพียงตัวเดียว (แทนที่จะ 2 ตัว) เมื่อ sensor เสีย → ระบบดึงหัวเครื่องลงเอง → เครื่องตก **346 คน** เสียชีวิต (สองเที่ยวบิน) โค้ดทำงานตามที่เขียน ไม่มี bug แต่ **ออกแบบกระบวนการผิด** (single point of failure ที่ sensor)

บทเรียน: โค้ด "ถูก" ในระบบที่ "ผิด" = หายนะ คิดเรื่องขั้นตอน ไม่ใช่แค่เรื่อง logic (ดู 1.5)

**5) Therac-25 (1985–1987) — bug ในเครื่องฉายรังสีฆ่าคน**

Therac-25 เครื่องฉายรังสีรักษามะเร็ง race condition ใน safety interlock ทำให้ผู้ป่วยได้รับรังสี overdose เสียชีวิตอย่างน้อย 6 คน สาเหตุ: ไม่มี automated test บน interlock logic + ไม่มี process ตรวจสอบข้ามทีม

บทเรียน: ระบบที่กระทบความปลอดภัยของคนต้องมี testing ที่ครอบคลุมทุก state ไม่ใช่เฉพาะ happy path

> **Pattern**: ทั้งห้าเคสไม่ได้ขาดคนเขียนโค้ด — ขาด "คนคิด" ขาด "คนตั้งคำถาม" ขาด "คนรับผิดชอบ"

> *แหล่งอ้างอิงที่ตรวจสอบได้:*
> - Theranos: [SEC vs. Theranos — case documents, 2018](https://www.sec.gov/news/press-release/2018-123) · [The Wall Street Journal, 16 ต.ค. 2015](https://www.wsj.com/articles/theranos-has-struggled-with-blood-tests-1444881901) · [Theranos Holmes verdict, 3 ม.ค. 2022](https://www.justice.gov/usao-ndca/pr/former-ceo-and-former-president-theranos-inc-convicted-federal-wire-fraud-charges)
> - Knight Capital: [Bloomberg, 2 ส.ค. 2012](https://www.bloomberg.com/news/articles/2012-08-02/knight-capital-s-trading-fiasco-cost-440-million-in-45-minutes) · [SEC, 16 ต.ค. 2013](https://www.sec.gov/news/press-release/2013-2013-225htm)
> - Healthcare.gov: [GAO, 2014 — GAO-14-174](https://www.gao.gov/products/gao-14-174)
> - Boeing 737 MAX: [NTSB Report, Sept. 2019](https://www.ntsb.gov/investigations/AccidentReports/Reports/AAR1901.pdf) · [Seattle Times, 2019](https://www.seattletimes.com/business/boeing-aerospace/)
> - Therac-25: [Leveson & Turner, 1993](https://cacm.acm.org/research/the-therac-25-incident/) · [Computer History Museum](https://computerhistory.org/blog/therac-25-the-radiation-therapy-machine-that-killed-patients/)

### Mindset Shift

| เดิม | ใหม่ |
|---|---|
| ซอฟต์แวร์ = โปรเจกต์ที่ส่งมอบครั้งเดียวแล้วจบ | ซอฟต์แวร์ = Product ที่ต้องดูแลต่อเนื่องหลายปี (1.2) |
| เน้นเขียนโค้ดให้ผ่าน test | เน้นคิดว่า "ใครได้ประโยชน์" และ "ความเสี่ยงคืออะไร" ก่อน (1.2) |
| ปล่อยให้มี bug เล็กค้างไว้ "ไม่เป็นไร" | ซ่อม broken window ทันที — ทุก bug ที่ปล่อยทิ้งจะกลายเป็น pattern (1.3) |
| ทำงานเสร็จตาม spec แล้วไปต่อ | เรียนรู้จากทุก feature ว่า "ดีพอ" หรือยัง (1.3) |
| เงียบเมื่อเห็นปัญหา | กล้าพูด — "เงียบ" คือมีส่วนร่วมกับปัญหา (1.5) |
| ซอฟต์แวร์เขียนได้ก็พอ | ซอฟต์แวร์มีจรรยาบรรณ — มีคนได้รับผลกระทบจริง (1.5) |

### Roadmap ของคาบนี้

**1.1 แผนบริหารการสอน** — Post-quiz Pattern 90 นาที · **1.2 Project vs Product (20 นาที)** — Product mindset + Vision Statement · **1.3 Pragmatic Philosophy (20 นาที)** — เจ้าของผลงาน, broken windows, ดีพอ · **1.4 Knowledge Portfolio (15 นาที)** — ลงทุนความรู้สม่ำเสมอ · **1.5 จรรยาบรรณ (15 นาที)** — ซื่อสัตย์ เคารพความเป็นส่วนตัว กล้าพูด · **1.6 Post-quiz (15 นาที)** — 5 MCQ (1.5%)

ทุกบทต่อจากนี้ตั้งอยู่บบบที่ 1 — บทที่ 2 สอน Agile, บทที่ 3 สอน Requirements, บทที่ 4 สอนต้นแบบ แต่ละบทจะตอบคำถาม "ทำอย่างไร" ในขณะที่บทนี้ตอบ "ทำไมต้องทำ"

**Prerequisites:** พื้นฐาน programming เคยเขียนโค้ดได้ · สมัคร GitHub account

**Self-check:** (1) เคยถูกถามว่า "ทำไมต้องทำ" ไหม — ตอบได้ไหม (ถ้าตอบไม่ได้ = ขาด Product mindset) (2) เคยเห็น bug ที่ปล่อยค้างไว้จนลุกลามไหม — เกิดอะไรขึ้น (3) ถ้าเพื่อนร่วมทีมเขียนโค้ดผิดจริยธรรม กล้าบอกไหม (ถ้าไม่กล้า = ขาด moral courage)

> **คำเตือนจากน้องวิจัย**: ซอฟต์แวร์ที่เขียนดีแต่คิดไม่ดีก็เหมือนบ้านที่ก่อสร้างสวยแต่แปลนผิด — แมวนอนในบ้านที่คนอยู่ ไม่ใช่แปลนที่ดูดี 🐾

---

## 1.1 แผนบริหารการสอนประจำบท

**ระยะเวลา**: 2 ชั่วโมง (บรรยาย) + 2 ชั่วโมง (ปฏิบัติการ) · **สัปดาห์ที่ 1**

### วัตถุประสงค์เชิงพฤติกรรม

เมื่อจบบทนี้ นิสิตสามารถ

1. อธิบายความแตกต่าง Project-based กับ Product-based
2. ระบุ Pragmatic Programmer 7 ประการ พร้อมยกตัวอย่าง
3. วิเคราะห์ Broken Window ในโครงการซอฟต์แวร์
4. อธิบาย Knowledge Portfolio และจัดแผนพัฒนาตนเอง
5. สะท้อนจรรยาบรรณเบื้องต้น

### โครงสร้างการสอน (Post-quiz Pattern)

| เวลา | กิจกรรม | สื่อ |
|---|---|---|
| 0:15–0:30 | แนะนำรายวิชา + GitHub Organization | สไลด์ + live demo |
| 0:30–0:50 | **1.2** Project vs Product (20 นาที) | กรณีศึกษา |
| 0:50–1:10 | **1.3** Pragmatic Philosophy (20 นาที) | Lame Excuse Bingo |
| 1:10–1:25 | **1.4** Knowledge Portfolio (15 นาที) | Five Whys |
| 1:25–1:45 | **1.5** จรรยาบรรณ (20 นาที) | กรณีศึกษา |
| 1:45–2:00 | **Post-quiz** (5 MCQ + 3 reflection, 1.5%) | เขียน → commit `reflect.md` |

### สื่อ

- ตำรา: [ESP] Ch.1, [PP] Ch.1, [SE] Ch.1–2
- สไลด์ (22 สไลด์)
- GitHub Organization

### การวัดผล

| ส่วน | คะแนน |
|---|:---:|
| Post-quiz | 1.5% |
| Lab 1 | 1.75% |
| รวม | 3.25% |

---

## 1.2 Project vs Product

ซอฟต์แวร์ที่ใช้ทุกวัน — LINE, Spotify, Slack — ล้วนเป็น **Product** ที่อัปเดตต่อเนื่อง ไม่ใช่โปรเจกต์ที่ส่งมอบแล้วจบ Sommerville (2019) ตั้งข้อสังเกตว่าอุตสาหกรรมเปลี่ยนจาก Project-based ไป Product-based ในช่วง 20 ปีที่ผ่านมา เพราะธุรกิจต้องการความเร็วในการปรับตัวมากกว่าการส่งมอบตาม spec

| มิติ | Project-based | Product-based |
|---|---|---|
| เป้าหมาย | ส่งมอบตามสัญญา | สร้างและรักษาฐานผู้ใช้ |
| ระยะเวลา | มีจุดเริ่ม-จบชัดเจน | ดำเนินต่อเนื่องหลายปี |
| ทีม | อาจสลายหลังส่งมอบ | ทีมหลักทำงานต่อเนื่อง |
| ความสำเร็จ | ตรงตามขอบข่าย ตรงเวลา | Engagement, Retention |
| การเปลี่ยนแปลง | ต้องผ่าน change request | ปรับเปลี่ยนได้ตาม feedback |

ในรายวิชานี้ นิสิตจะทำงานเป็นทีมตลอดภาค — ตั้งแต่ Sprint Zero ถึง Demo Day ไม่ใช่ส่งงานปลายเทอมแล้วจบ

**Product Vision Statement (Moore template)** ช่วยให้ทีมตกลงกันว่า product คืออะไร ก่อนเขียนโค้ด

```
For [target customer]
Who [need/opportunity]
The [product name]
Is a [product category]
That [key benefit]
Unlike [primary competitive alternative]
Our Product [primary differentiation]
```

---

## 1.3 ปรัชญา Pragmatic

### 1.3.1 เจ้าของผลงาน เสนอทางเลือกแทนข้อแก้ตัว

Hunt & Thomas เริ่มหนังสือด้วยเรื่อง "Cat Ate My Source Code" — วัฒนธรรมโยนความผิด หลักการสำคัญสองข้อ

> **It's Your Life** (Tip 1) — คุณมี agency อย่านั่งรอให้คนอื่นมาแก้

> **Provide Options, Don't Make Lame Excuses** (Tip 4) — เมื่อเจอปัญหา อย่าเสียเวลาคิดข้อแก้ตัว เอาเวลานั้นไปเสนอทางเลือก

ตัวอย่าง: Sprint ทำไม่ทันเพราะ API ยังไม่พร้อม — แทนที่จะบอก "ทำไม่ได้เพราะ backend" เสนอทางเลือกพร้อมข้อดีข้อเสีย
- A: ใช้ mock API ชั่วคราว (เสี่ยง: ต้องแก้ integration ทีหลัง)
- B: ลด scope เหลือ feature ที่ไม่พึ่ง API (เสี่ยง: velocity ลด)
- C: ขอความช่วยเหลือจากทีมที่ API พร้อม (เสี่ยง: dependency เพิ่ม)

การเสนอทางเลือกแสดงว่า **เป็นเจ้าของปัญหา** ไม่ใช่เหยื่อ

### 1.3.2 Broken Window Theory

ยืมแนวคิดจาก Wilson & Kelling (1982): อาคารที่มีหน้าต่างแตก 1 บาน จะถูกทำลายเพิ่ม เพราะคนตีความว่า "ไม่มีใครสนใจ"

> **Don't Live with Broken Windows** (Tip 5) — อย่าปล่อยให้ bad design, wrong decisions, poor code ค้างไว้ Fix ทันที

ตัวอย่าง: ฟังก์ชัน `calculateTax()` ทำงานผิดเมื่อ amount เป็น 0 ทีมรู้แต่ "ยังไม่มีเวลา" แก้ ผ่านไป 2 สัปดาห์ developer ใหม่เห็นโค้ดเก่าและคัดลอก pattern ผิดไปใช้ที่อื่น อีก 2 สัปดาห์ระบบคำนวณภาษีผิดทั้งหมด ใช้เวลา 3 สัปดาห์แก้ทั้งหมด ทั้งหมดนี้เกิดจาก "หน้าต่างแตกบานเดียว"

**วิธีป้องกัน**: ตั้งกฎทีม — broken window ทุกตัวต้อง fix ใน Sprint เดียวกัน หรืออย่างน้อยสร้าง issue + assign ให้ชัดเจน อย่า "รู้แล้วปล่อย"

### 1.3.3 Stone Soup & Boiled Frogs

สองเรื่องสั้นที่สะท้อนพลวัตทีม

> **Be a Catalyst for Change** (Tip 6) — หินในหม้อน้ำเป็นจุดเริ่มต้องชาวบ้านเติมผักเอง

ตัวอย่าง: ทีมอยากใช้ CI/CD แต่หัวหน้าทีมไม่แน่ใจ เริ่มจาก "หินก้อนเดียว" — ตั้ง GitHub Actions รัน test อัตโนมัติ เมื่อทีมเห็น test ผ่าน/ล้มชัดเจน หัวหน้าจะถามเองว่า "เพิ่ม deploy อัตโนมัติได้ไหม" — ชาวบ้านเติมผักเอง

> **Remember the Big Picture** (Tip 7) — กบในหม้อน้ำร้อนไม่รู้ตัว เราก็เหมือนกัน ถ้าไม่หยุดมองภาพใหญ่

**สัญญาณ Boiled Frog**: Sprint 1 ทำเล็ก ๆ ไม่เป็นไร Sprint 3 เริ่มสะสม Sprint 5 ต้อง demo หน้าโซน เดือดแล้ว

### 1.3.4 Good-Enough Software

> **Make Quality a Requirements Issue** (Tip 8) — ต้องรู้จัก "ดีพอ" เหมือนจิตรกรที่รู้จักหยุดเติมสี

ไม่ใช่ "ทำให้สมบูรณ์แบบ" แต่ "ทำให้ถึงระดับที่ตกลงกับผู้ใช้" การถามผู้ใช้ว่า "ต้องการดีแค่ไหน" ก่อนเริ่มป้องกันทั้ง over-engineering และ under-engineering

**ข้อยกเว้น**: ห้าม "ดีพอ" กับ security/reliability — ผู้ใช้มองไม่เห็นความจำเป็นจนกว่าจะถูกโจมตี ให้ตั้งเกณฑ์ที่สูงพอสำหรับเรื่องที่กระทบความปลอดภัย

### 1.3.5 DRY · ETC · Orthogonality

สามหลักการออกแบบที่เชื่อมโยงกัน

**DRY — Don't Repeat Yourself** (Tip 11): ความรู้ทุกชิ้นมีแหล่งเดียวที่น่าเชื่อถือ ถ้า logic เดียวกันอยู่ใน 3 ไฟล์ แก้ครั้งหนึ่งต้องแก้ 3 ที่ ลืม 1 ที่ได้ผลลัพธ์ไม่ตรงกัน

**ETC — Easier to Change** (Tip 17): เลือกระหว่าง design สองแบบ ให้ถามว่า "ถ้า requirement เปลี่ยน แบบไหนแก้ได้ง่ายกว่า" — heuristic ที่ตัดสินใจโดยไม่ over-engineer

**Orthogonality** (Tip 13): แต่ละ component เป็นอิสระต่อกัน เปลี่ยน database ไม่กระทบ UI เปลี่ยน API ไม่กระทบ frontend

สามหลักการนี้เชื่อมโยงกัน: DRY ลด duplicate → ETC ทำให้แก้ได้ง่าย → Orthogonality จำกัดขอบเขตผลกระทบ

---

## 1.4 Knowledge Portfolio

Hunt & Thomas เปรียบเทียบความรู้ของนักพัฒนากับ **พอร์ตการลงทุน** ที่ต้องบริหารอย่างต่อเนื่อง

> **Invest Regularly in Your Knowledge Portfolio** (Tip 9) — ทำให้การเรียนรู้เป็นนิสัย ไม่ใช่ event ครั้งเดียว

5 หลัก:

1. **ลงทุนสม่ำเสมอ** — 30 นาทีทุกวัน ดีกว่า 5 ชั่วโมงครั้งเดียวต่อเดือน
2. **Diversify** — เรียนหลายเทคโนโลยี ไม่ผูก stack เดียว ถ้าเชี่ยว Python ลอง Go/Rust เพื่อเห็นมุมมองต่าง
3. **สมดุลความเสี่ยง** — 80% safe tech / 20% cutting-edge
4. **Buy low, sell high** — เรียนของใหม่ก่อน mainstream
5. **Rebalance เป็นระยะ** — ทบทวนทุก 6 เดือน

**สำหรับนิสิตปี 1**: อ่าน tech blog สัปดาห์ละ 1 บทความ · ลองภาษาใหม่ทุกเทอม · ทำ side project ทุกปิดเทอม

**Five Whys** (Tip 10) — เทคนิคของ Toyota ถาม "ทำไม?" 5 ครั้งเพื่อหา root cause

> Bug: ฟังก์ชันคำนวณส่วนลดผิด
> ทำไม? ใช้ `>` แทน `>=`
> ทำไม? developer เข้าใจ requirement ผิด
> ทำไม? ไม่มี Acceptance Criteria ชัด
> ทำไม? ไม่มี process ตรวจสอบกับ PO
> ทำไม? — root cause = กระบวนการที่ขาดคุณภาพ

Bug ไม่ได้เกิดจากคนผิด เกิดจากกระบวนการ แก้ที่ root cause (เพิ่ม AC process) มีประสิทธิภาพกว่าแก้ปลายเหตุ (เปลี่ยน `>` เป็น `>=`)

---

## 1.5 จรรยาบรรณและความรับผิดชอบ

### 1.5.1 ACM Code of Ethics (2018)

ACM กำหนดหลักจรรยาบรรณ 7 ข้อ (เรียงตามลำดับสำคัญ):

1. มีส่วนร่วมต่อสังคมและสวัสดิการของมนุษย์
2. หลีกเลี่ยงอันตรายต่อผู้อื่น
3. ซื่อสัตย์และไว้วางใจได้
4. ปฏิบัติอย่างเป็นธรรม
5. เคารพทรัพย์สินทางปัญญา
6. เคารพความเป็นส่วนตัว
7. รักษาความลับ

แปลเป็นแนวปฏิบัติ: ไม่เก็บข้อมูลส่วนบุคคลเกินจำเป็น · ไม่เปิดเผยข้อมูลผู้ใช้ให้บุคคลที่สาม · เปิดเผย conflict of interest · รายงาน bug ที่อาจกระทบความปลอดภัย · ไม่ใช้เทคโนโลยีเพื่อสร้างความเสียหาย

### 1.5.2 Communicate!

ทักษะการสื่อสารสำคัญไม่แพ้ทักษะการเขียนโค้ด นักพัฒนาที่เขียนโค้ดเก่งแต่สื่อสารไม่ได้ จะถูกจำกัดเพดานอาชีพ

> **English is Just Another Programming Language** (Tip 11) — เขียน commit message, PR description, documentation ด้วยความใส่ใจเดียวกับเขียนโค้ด ใช้ template ตรวจ grammar อย่า copy-paste

> **Build Documentation In, Don't Bolt It On** (Tip 13) — README.md ต้องอยู่ใน repo เดียวกับโค้ด API docs สร้างจาก code comments ไม่ใช่เขียนแยกใน Word file ที่จะ outdated

### 1.5.3 Case Study — Theranos

Theranos คือกรณีศึกษาที่ชัดเจนที่สุดของการละเมิดจรรยาบรรณ เครื่อง Edison อ้างว่าตรวจเลือดได้ 240+ รายการ แต่ผลจริงรันบนเครื่อง Siemens

Holmes สร้างวัฒนธรรม "ความลับ" — ทีมต่าง ๆ ไม่ได้รับอนุญาตให้พูดคุมข้ามแผน พนักงานที่ถามคำถามถูกมองว่า "ไม่เชื่อ mission" Tyler Shultz และ Erika Cheung ตัดสินใจเป็น whistleblower แม้ถูกขู่ฟ้องและเสียอาชีพ

ผลลัพธ์: Holmes ถูกตัดสินจำคุก 11 ปี (2022) บริษัทล้มละลาย ผู้ป่วยหลายพันคนได้ผลตรวจผิด

บทเรียน: ACM ข้อ 2 (Avoid harm) — ผลตรวจเลือดที่ผิดอาจนำไปสู่การรักษาที่ผิด ชีวิตคนเป็นเดิมพัน · ACM ข้อ 3 (Honesty) — ปกปิดข้อจำกัดของเทคโนโลยีเป็นการหลอกลวงผู้ใช้ · **กล้าพูด** — เมื่อรู้ว่า product เป็นอันตราย การเงียบ = การมีส่วนร่วม

---

## 1.6 Post-quiz (ท้ายคาบ 1:45–2:00, 1.5%)

### Section A: เลือกคำตอบที่ถูกต้องที่สุด (5 ข้อ × 0.3 = 1.5 คะแนน)

**A1.** PP Tip 5 ("Don't Live with Broken Windows") เกี่ยวกับแนวคิดใด
- A) ใช้เครื่องมือดี ๆ แก้ทุกปัญหา
- B) Software Entropy — อย่าปล่อยให้ bad code/poor design สะสม
- C) ทำงานล่วงเวลาเพื่อทีม
- D) Respect Privacy

**A2.** Project-based กับ Product-based Development ต่างกันอย่างไรในมิติ "ระยะเวลา"
- A) Project: ต่อเนื่องหลายปี / Product: มีจุดเริ่ม-จบ
- B) Project: มีจุดเริ่ม-จบชัดเจน / Product: ดำเนินต่อเนื่องหลายปี
- C) เหมือนกัน
- D) ทั้งคู่ไม่มีจุดเริ่ม-จบ

**A3.** Moore's Product Vision template (1991) ประกอบด้วยกี่ส่วนหลัก
- A) 3 (FOR, WHO, THE)
- B) 5 (FOR, WHO, THE, IS A, THAT)
- C) 7 (FOR, WHO, THE, IS A, THAT, UNLIKE, OUR PRODUCT)
- D) 9

**A4.** ข้อใดเป็นหลัก ACM Code of Ethics (2018)
- A) ทำงานล่วงเวลาเพื่อทีม
- B) Respect Privacy (เคารพความเป็นส่วนตัว)
- C) ใช้ Generative AI เขียนโค้ดแทนคน
- D) เรียนรู้เทคโนโลยีใหม่ทุกเดือน

**A5.** Knowledge Portfolio — หลักการ "Diversify" หมายถึงอะไร
- A) เรียนภาษาเดียวให้เชี่ยวชาญลึก
- B) กระจายความเชี่ยวชาญหลายเทคโนโลยี ไม่ผูก stack เดียว
- C) ลงทุนในหุ้นเทคโนโลยี
- D) อ่านหนังสือเทคนิคให้ได้เดือนละ 1 เล่ม

### เฉลย

- **A1. B** — Tip 5 คือ Software Entropy concept (Hunt & Thomas 2019)
- **A2. B** — Project มีจุดเริ่ม/จบ / Product ต่อเนื่อง (Sommerville 2019)
- **A3. C** — Moore template 7 ส่วน
- **A4. B** — Respect Privacy = ACM Code ข้อ 6 (ACM 2018)
- **A5. B** — Diversify = กระจาย risk ข้าม technologies

### Section B: Reflection (ไม่นับคะแนน) — ส่งเป็น `reflect.md`

**B1. Apply — Vision Filter (2–3 ประโยค)**

ทีมเสนอเพิ่มฟีเจอร์ "AI แนะนำ routine" ให้กับ Pragmatic Pomodoro — ใช้ Vision Statement ตัดสินใจว่าจะรับหรือปัด
- ระบุประโยคใน Vision ที่เกี่ยวข้อง
- สรุปการตัดสินใจ + เหตุผล

**B2. Connect — Broken Window (3–4 ประโยค)**

เลือก "broken window" 1 อย่างจากประสบการณ์จริง (โค้ด/กระบวนการ/พฤติกรรม)
- window คืออะไร
- ส่งผลอย่างไรเมื่อปล่อยไว้
- ถ้าซ่อมทันทีจะป้องกันอะไร

**B3. Reflect — Pragmatic Promise (1 ประโยค)**

เขียน "Pragmatic Promise" 1 ประโยค — พฤติกรรม concrete ที่จะเริ่มทำตั้งแต่วันนี้ (วัดผลได้ ไม่ใช่ "จะตั้งใจ")

### วิธีส่ง

1. สร้าง branch `feature/post-quiz-1` ใน team repo
2. สร้าง `reflect.md` ที่ root ของ repo
3. Commit + push + เปิด PR (merge พร้อม Lab 1)

---

## 1.7 สรุปสาระสำคัญ

บทที่ 1 ปูพื้นฐานทั้งรายวิชา:

- **จาก Project สู่ Product** — ซอฟต์แวร์สมัยใหม่เป็น Product ที่ต้องดูแลต่อเนื่อง ไม่ใช่โปรเจกต์ที่ส่งมอบครั้งเดียว การเปลี่ยน mindset ส่งผลต่อทุกอย่าง ตั้งแต่ architecture จนถึงการวัดผล
- **ปรัชญา Pragmatic** — เจ้าของผลงาน เสนอทางเลือกแทนข้อแก้ตัว อย่าปล่อยให้ broken windows สะสม เริ่มต้นเปลี่ยนแปลงด้วยชิ้นเล็กที่ทำได้ รู้จัก "ดีพอ" โดยตกลงกับผู้ใช้
- **DRY · ETC · Orthogonality** — ลด duplicate ออกแบบให้ง่ายต่อการเปลี่ยนแปลง จำกัดขอบเขตผลกระทบ ทั้งสามเป็นรากฐานของ architecture ที่ดี
- **Knowledge Portfolio** — ลงทุนในความรู้อย่างสม่ำเสมอ กระจายความเสี่ยง Five Whys ช่วยหา root cause ไม่ใช่แค่แก้ปัญหาที่ปลายเหตุ
- **จรรยาบรรณ** — ยึดหลัก ACM Code of Ethics ปกป้องผู้ใช้ เคารพความเป็นส่วนตัว กล้าพูด กรณี Theranos เตือนว่า "การเงียบ" เมื่อรู้ว่า product เป็นอันตราย คือการมีส่วนร่วม

แนวคิดเหล่านี้จะถูกนำไปใช้ในบทถัดไป — บทที่ 2 สอน Agile, บทที่ 3 สอน Requirements, บทที่ 4 สอบต้นแบบ

---

## 1.8 คำถามทบทวน

1. อธิบายความแตกต่างระหว่าง Project-based กับ Product-based Development พร้อมยกตัวอย่าง 2 ตัวอย่าง
2. ทีมเสนอเพิ่มฟีเจอร์นอก Vision — ใช้ Vision Statement ตัดสินใจอย่างไร
3. ยกตัวอย่าง Broken Window จากประสบการณ์ พร้อมอธิบายผลกระทบ
4. ทำไม "Good-Enough Software" ไม่ใช่ซอฟต์แวร์คุณภาพต่ำ
5. สร้าง Product Vision Statement ตาม Moore template สำหรับโปรเจกต์ที่สนใจ

---

## 1.9 แบบฝึกหัด

### 1.1 — Vision Statement สำหรับโปรเจกต์

เขียน Product Vision Statement ตาม Moore template (7 ส่วน) สำหรับโปรเจกต์ที่อยากทำในภาคเรียนนี้ พร้อมเหตุผลสั้น ๆ ว่าทำไมเลือก "For [customer]" นี้

### 1.2 — Broken Window Hunt

ในโค้ดเดิมที่เคยเขียน หา "broken window" 1 อย่าง
- window คืออะไร
- เกิดผลกระทบอะไร
- ถ้าซ่อมทันทีจะป้องกันอะไร

---

## บรรณานุกรมเพิ่มเติมประจำบท

- Hunt, A., & Thomas, D. (2019). *The Pragmatic Programmer: Your Journey to Mastery* (2nd ed.). Addison-Wesley Professional. Chapter 1.
- Sommerville, I. (2019). *Engineering Software Products*. Pearson. Chapter 1.
- Sommerville, I. (2016). *Software Engineering* (10th ed.). Pearson. Chapters 1–2.
- Wilson, J. Q., & Kelling, G. L. (1982). Broken Windows. *The Atlantic Monthly*, 249(3), 29–38.
- Moore, G. A. (1991). *Crossing the Chasm*. HarperBusiness.
- ACM Code of Ethics (2018). Association for Computing Machinery.

---

*จัดทำโดย: ธรรมรัตน์ ธรรมา · สาขาวิทยาการคอมพิวเตอร์ คณะเทคโนโลยีสารสนเทศและการสื่อสาร มหาวิทยาลัยพะเยา · ภาคเรียนที่ 1 ปีการศึกษา 2569*
