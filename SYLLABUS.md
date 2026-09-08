# ประมวลรายวิชา (Course Syllabus) 
## รายวิชา: Software Engineering Concepts (แนวคิดวิศวกรรมซอฟต์แวร์)

* **จำนวนสัปดาห์:** 15 สัปดาห์
* **รูปแบบการเรียนการสอน:** บรรยายร่วมกับการปฏิบัติการ (Lecture & Hands-on Lab)
* **การวัดผล:** โครงงานและการประเมินผลอย่างต่อเนื่อง 100% (ไม่มีการสอบทฤษฎีในห้องสอบ)

---

### 1. คำอธิบายรายวิชา (Course Description)

ศึกษาแนวคิด ปรัชญา และหลักการของวิศวกรรมซอฟต์แวร์สมัยใหม่ เปรียบเทียบการพัฒนารูปแบบโครงการ (Project-based) กับรูปแบบผลิตภัณฑ์ (Product-based) ปลูกฝังทัศนติแบบ "Pragmatic Programmer" การบริหารจัดการโครงการด้วยแนวคิด Agile (Scrum & Extreme Programming) การวิเคราะห์ความต้องการและการจำลองสถานการณ์ผู้ใช้ (Personas, User Stories) การสร้างต้นแบบอย่างรวดเร็วโดยใช้ AI ช่วยเหลือ (AI-Assisted Prototyping)

ศึกษาหลักการออกแบบสถาปัตยกรรมซอฟต์แวร์ (Software Architecture) และสถาปัตยกรรมสมัยใหม่บนคลาวด์ (Cloud-Native & Microservices) การสร้างสรรค์โค้ดที่สะอาด (Clean Code) การประกันคุณภาพและการทดสอบอัตโนมัติ (TDD, Unit Testing) วัฒนธรรมและกระบวนการ DevOps (CI/CD Pipeline, Infrastructure as Code) วิศวกรรมซอฟต์แวร์ที่ปลอดภัยและความเป็นส่วนตัวของข้อมูล (Secure by Design & Data Privacy) เทคนิคการปรับปรุงโครงสร้างโค้ด (Refactoring) เพื่อลดหนี้ทางเทคนิค ตลอดจนจรรยาบรรณวิชาชีพและแนวโน้มในอนาคตของวิศวกรรมซอฟต์แวร์

---

### 2. วัตถุประสงค์การเรียนรู้ (Learning Objectives)

เมื่อนิสิตศึกษาเนื้อหาและปฏิบัติงานในรายวิชานี้ครบ 15 สัปดาห์แล้ว จะมีความสามารถตามองค์ประกอบ 3 ด้าน ดังนี้:

#### 2.1 ด้านความรู้และทักษะทางปัญญา (Cognitive & Intellectual Skills)

* **LO1:** สามารถอธิบายและเปรียบเทียบความแตกต่างระหว่างการพัฒนารูปแบบโครงการ (Project-based) และการพัฒนาผลิตภัณฑ์ซอฟต์แวร์ (Product-based) ในบริบทของอุตสาหกรรมยุคปัจจุบันได้ถูกต้อง
* **LO2:** สามารถวิเคราะห์และตัดสินใจ (Trade-off Analysis) ในการเลือกรูปแบบสถาปัตยกรรมซอฟต์แวร์ (เช่น Monolith vs Microservices) และเทคโนโลยีสแตก (Tech Stack) ให้เหมาะสมกับข้อกำหนดของระบบทั้งในแง่ฟังก์ชันและคุณลักษณะที่ไม่ใช่ฟังก์ชัน (Non-functional attributes)
* **LO3:** สามารถออกแบบระบบการทดสอบและกระบวนการส่งมอบซอฟต์แวร์ โดยประยุกต์ใช้หลักการของ Test-Driven Development (TDD) และ DevOps (CI/CD) ได้อย่างเป็นระบบ

#### 2.2 ด้านทักษะการปฏิบัติและทักษะวิชาชีพ (Practical & Professional Skills)

* **LO4:** สามารถประยุกต์ใช้กระบวนการทำงานแบบ Agile (Scrum & XP) เพื่อบริหารจัดการงานและสปรินต์ (Sprint) ร่วมกับทีมผ่านเครื่องมือสมัยใหม่ (เช่น GitHub Projects) ได้อย่างมีประสิทธิภาพ
* **LO5:** สามารถแปลงความต้องการของผู้ใช้ (Requirements) จากรูปแบบ Personas และ Scenarios ให้กลายเป็น User Stories และเกณฑ์การยอมรับ (Acceptance Criteria) ที่สามารถนำไปพัฒนาต่อได้จริง
* **LO6:** สามารถสร้าง ปรับปรุง (Refactor) และปกป้องซอฟต์แวร์ โดยใช้แนวคิด Clean Code หลักการ DRY/ETC การเขียน Dockerfile และการประยุกต์ใช้มาตรการความปลอดภัยขั้นพื้นฐาน (Secure by Design)
* **LO7:** สามารถเลือกและใช้เครื่องมือ Generative AI (เช่น GitHub Copilot, ChatGPT) ในฐานะผู้ช่วยเพื่อเพิ่มประสิทธิภาพในการทำต้นแบบ (Prototyping) การเขียนโค้ด และการสร้างชุดทดสอบอัตโนมัติได้อย่างชาญฉลาด

#### 2.3 ด้านทักษะทางสังคม จริยธรรม และการสื่อสาร (Soft Skills, Ethics & Communication)

* **LO8:** สามารถสื่อสาร นำเสนอ และสาธิตซอฟต์แวร์ (Software Demo) ที่ทำงานได้จริงให้แก่ผู้มีส่วนได้ส่วนเสีย พร้อมทั้งอธิบายเหตุผลเบื้องหลังการตัดสินใจเชิงวิศวกรรมได้อย่างชัดเจนและเป็นมืออาชีพ
* **LO9:** มีความรับผิดชอบในการทำงานร่วมกันเป็นทีมผ่านระบบควบคุมเวอร์ชัน (Git/GitHub) มีวินัยในการส่งมอบงานอย่างสม่ำเสมอ และสามารถตรวจสอบย้อนกลับกระบวนการทำงานของตนเองได้ (Git Contribution)
* **LO10:** มีความตระหนักรู้ในเรื่องจรรยาบรรณวิชาชีพ (Professional Ethics) และตระหนักถึงความรับผิดชอบในประเด็นความปลอดภัยและความเป็นส่วนตัวของข้อมูลผู้ใช้ (Data Privacy / PDPA)

---

### 3. ปรัชญาและแนวทางการวัดผล (Grading & Assessment Philosophy)

รายวิชานี้เน้นการลงมือทำและแก้ปัญหาจริงจากประสบการณ์ การประเมินผลจะพิจารณาจากผลงานที่จับต้องได้และกระบวนการทำงานที่มีคุณภาพผ่านระบบ GitHub เป็นหลัก โดยเก็บคะแนนสะสมอย่างต่อเนื่องตลอดทั้งภาคการศึกษา (Continuous Assessment 100%) เพื่อส่งเสริมการเรียนรู้เชิงลึก **(ไม่มีการสอบทฤษฎีในห้องสอบ)**

#### สัดส่วนการประเมินผล (Grading Scheme)

| องค์ประกอบการประเมิน (Assessment Component) | สัดส่วนคะแนน | วัตถุประสงค์ที่สอดคล้อง |
| --- | --- | --- |
| **A. งานปฏิบัติการรายสัปดาห์ (Weekly Labs)** | **25%** | LO4, LO5, LO6, LO7, LO9 |
| **B. สอบกลางภาค: Project Milestone 1** | **25%** | LO1, LO2, LO5, LO6, LO9 |
| **C. โครงงานปลายภาค และการนำเสนอ (Final Project & Demo)** | **35%** | LO2, LO3, LO6, LO8, LO9 |
| **D. การมีส่วนร่วมและผลงานรายบุคคล (Individual Contribution)** | **15%** | LO9, LO10 |
| **รวม** | **100%** |  |

---

### 4. รายละเอียดเกณฑ์การประเมินผล (Rubrics)

* **A. งานปฏิบัติการรายสัปดาห์ (Weekly Labs) - 25%:** ตรวจสอบจากการส่งงาน (Commit) บน GitHub Repository ของแต่ละทีม เน้นการให้คะแนนแบบ *Completion and Effort* (ทำครบถ้วนตามโจทย์และแสดงให้เห็นถึงความพยายาม) เพื่อกระตุ้นให้นิสิตกล้าทดลองและเรียนรู้จากข้อผิดพลาด
* **B. สอบกลางภาค: Project Milestone 1 - 25%:** ประเมินความสมบูรณ์ของคลังโค้ด ณ สิ้นสุดสัปดาห์ที่ 7 แบ่งเป็น Project Management & Process (5%), Requirements & Design Artifacts (5%), Code Quality (10%), และ Repository & Docker Documentation (5%)
* **C. โครงงานปลายภาคและการนำเสนอ (Final Project & Demo) - 35%:** ประเมิน ณ สัปดาห์ที่ 14 จากความสามารถในการทำงานของซอฟต์แวร์จริง (10%), ความยอดเยี่ยมทางเทคนิคและสถาปัตยกรรม (10%), ความสมบูรณ์ของ DevOps Pipeline (5%), ทักษะการนำเสนอและสาธิต Demo (5%), และเอกสารคู่มือพัฒนา (5%)
* **D. การมีส่วนร่วมและผลงานรายบุคคล (Individual Contribution) - 15%:** วิเคราะห์ผลงานรายบุคคลผ่าน Git History Analysis ดูความถี่และความสม่ำเสมอในการส่งมอบงาน (10%) และการส่งงานเขียนถอดบทเรียนและความเข้าใจท้ายเทอม Final Reflection (5%)

---

### 5. แผนการเรียนรายสัปดาห์และเอกสารอ่านประกอบ (15-Week Course Outline)

| สัปดาห์ | หัวข้อ/เนื้อหาบทเรียน (Lecture Topics) | งานปฏิบัติการที่ต้องส่งมอบ (Weekly Labs) | คะแนน | เอกสารอ่านประกอบ |
| --- | --- | --- | --- | --- |
| **1** | [Intro to SE & Pragmatic Mindset / Project vs Product / ความรับผิดชอบของนักพัฒนา](https://github.com/Software-Engineering-Concepts-2026/se-course-materials-2026/tree/main/Week1) | **Lab 1:** First Pragmatic Commit / ส่งไฟล์ `<your-name>.md` สะท้อนความคิดลง GitHub | 1% | [ESP] Ch.1-2, [PP] Ch.1 |
| **2** | Agile Methodologies / พิธีกรรมและบทบาทใน Scrum / แนวปฏิบัติทางเทคนิคพื้นฐานตามวิถี XP | **Lab 2:** Sprint Zero Setup / ตั้งค่า GitHub Projects Board และสร้าง Product Backlog | 2% | [ESP] Ch.3 |
| **3** | Modern Requirements / การเข้าใจผู้ใช้ผ่าน Personas และ Scenarios / การเขียน User Stories | **Lab 3:** Requirements Docs / ส่งมอบเอกสารวิเคราะห์และจัดเก็บลงในโฟลเดอร์ `docs/` | 2% | [ESP] Ch.4-5 |
| **4** | Prototyping / การสร้างต้นแบบเพื่อทดสอบแนวคิด / ใช้ GenAI (Copilot/ChatGPT) ช่วยขึ้นโครง | **Lab 4:** Rapid Prototyping / ส่งมอบไฟล์ต้นแบบหน้าจอ (HTML/CSS/JS) ที่โต้ตอบได้ | 2% | [ESP] Ch.6, [SCG] Ch.1-3 |
| **5** | Fundamentals of Software Architecture / การวิเคราะห์ Trade-offs / Non-functional / Decomposition | **Lab 5:** Architectural Artifacts / ออกแบบ C4 Diagrams และเขียนสรุป `tech_stack.md` | 2% | [ESP] Ch.7, [PP] Ch.5 |
| **6** | Architectural Patterns / แนวคิด Cloud-Native, Virtualization & Containers / Microservices | **Lab 6:** First Container / เขียน Dockerfile สำหรับระบบย่อย และ Push ขึ้น Docker Hub | 3% | [ESP] Ch.8-9 |
| **7** | Pragmatic Programming / เขียนโค้ดสะอาดตามหลัก DRY, Orthogonality / แนวคิดโค้ดพร้อมรับการเปลี่ยน (ETC) | **Lab 7:** Refactoring Commit / ปรับปรุงโค้ดให้คลีนตามมาตรฐาน *(ส่งมอบ Project Milestone 1)* | 2% *(MS1: 25%)* | [PP] Ch.2, 4 |
| **8** | **Midterm Examination Period (No Classes)** / งดการเรียนการสอนสัปดาห์สอบกลางภาควิชาอื่น | *ไม่มีการเรียนการสอนและการส่งงานในสัปดาห์นี้* | - | - |
| **9** | QA & Automated Testing / วัฒนธรรมคุณภาพผ่าน TDD / Unit, Integration & System Testing / AI Test Gen | **Lab 9:** Unit Test Implementation / ส่งไฟล์ทดสอบ (`test_*.py`) และรันระบบ CI ขั้นพื้นฐาน | 3% | [ESP] Ch.11, [PP] Ch.7, [SCG] Ch.6 |
| **10** | DevOps Pipeline / การบริหาร Git Branching / สร้างระบบ CI/CD Pipeline / แนวคิด Infrastructure as Code | **Lab 10:** Full CI/CD Pipeline / ส่งมอบไฟล์ Workflow สมบูรณ์ที่ Build และ Test อัตโนมัติ | 3% | [ESP] Ch.10, [SCG] Ch.8 |
| **11** | Secure Software Engineering / ออกแบบระบบให้ปลอดภัย (Secure by Design) / ช่องโหว่พื้นฐาน / Data Privacy & PDPA | **Lab 11:** Security Hardening / ทำ Input Validation และซ่อนข้อมูลความลับผ่านไฟล์ `.env` | 3% | [ESP] Ch.12, [PP] Ch.6 |
| **12** | Advanced Refactoring / การบริหารจัดการหนี้ทางเทคนิค (Technical Debt) / ตรวจจับ Code Smells / AI Assistant | **Lab 12:** Advanced Refactoring / ไล่เคลียร์และปิดประเด็น (Issues) ข้อบกพร่องในคลังโค้ด | 2% | [PP] Ch.8, [SCG] Ch.5 |
| **13** | Project Workshop / คาบปฏิบัติการลุยงานกลุ่มใน Sprint สุดท้าย / รับคำปรึกษาเชิงลึกจากผู้สอน (Consultation) | *ไม่มีคะแนน Lab ย่อย* / นิสิตทำงานร่วมกันเพื่อเตรียมระบบให้พร้อมสำหรับวันนำเสนอ | - | [PP] Ch.9 |
| **14** | **Final Project Presentations & Demo Day** / นำเสนอซอฟต์แวร์จริงที่ทำงานได้ (Working Software) ต่อสาธารณะ | **Final Project Presentation** / ประเมินผลงานสุดท้าย โครงสร้างวิศวกรรม ท่อ DevOps และการสาธิต | *(Final Proj: 35%)* | - |
| **15** | Professional Practice / จรรยาบรรณวิชาชีพและแนวทางอาชีพ / อนาคตของวิศวกรรมซอฟต์แวร์ในยุค AI | **Final Reflection** / ส่งงานเขียนถอดบทเรียนรายบุคคลหลังทำกิจกรรม Retrospective และวัดผล Git History | *(Reflect: 5%)* *(Git Anal: 10%)* | [ESP] Ch.13, [PP] Ch.1 |

---

### 6. เอกสารอ้างอิงเพื่อการศึกษาค้นคว้าหลัก (Core References)

* **[ESP]** Sommerville, I. (2019). *Engineering Software Products: An Introduction to Modern Software Engineering*. Pearson.
* **[PP]** Hunt, A., & Thomas, D. (2019). *The Pragmatic Programmer: Your Journey to Mastery* (2nd ed.). Addison-Wesley Professional.
* **[SCG]** Herszfang, H. P., & Henstock, P. V. (2025). *Supercharged Coding with GenAI*. Packt Publishing.
