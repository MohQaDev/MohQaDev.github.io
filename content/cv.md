---
title: "CV"
url: "/cv/"
ShowToc: true
ShowBreadCrumbs: false
---

📄 **[Download CV (PDF)](/MohammadAlQadi_CV.pdf)**  •  📜 **[AWS Cloud Practitioner — Course Completion Certificate (PDF)](/AWS_CloudPractitioner_Certificate.pdf)**

---

## Mohammad Ayman Ghazi Al Qadi

Amman, Jordan  •  +962-79-767-8128  •  [mohqa.dev@outlook.com](mailto:mohqa.dev@outlook.com)  •  [LinkedIn](https://www.linkedin.com/in/mohammad-al-qadi-a96643261)  •  Age: 22

**About me** — Final-year Computer Science student at PSUT with hands-on experience building full-stack applications across mobile, backend, database, and enterprise cloud/AI layers. Comfortable taking a project from schema design to deployment, and quick to pick up new stacks. Looking to join a team where I can contribute from day one and keep growing as a developer.

---

## Education

**Princess Sumaya University of Technology** — Amman, Jordan
B.Sc. in Computer Science *(ABET Accredited)* — *Sep 2022 – Expected Sep 2026*

- Relevant coursework: Data Analysis, Software Engineering, Operating Systems, Data Structures, Algorithms, AI, Software Development

**Al-Rowad International Schools** — Riyadh, Saudi Arabia
IGCSE & A-Level *(Tawjihi Equivalency)* — *Graduated 2022*

- A-Level subjects: Physics, Mathematics, Computer Science — Grade **A**
- Equated average: **94.4%** *(Jordanian Ministry of Education Equivalency)*

---

## Languages

- **Arabic** — Native
- **English** — Fluent (Academic & Professional)

---

## Relevant Experience

### UNRWA HQA (Headquarters) — Amman, Jordan

**Digital Transformation Intern**  •  *Aug 2026 – Present*

- **AutoDoc (Enterprise AI Documentation Tool):** Conceived and developed an automated documentation generator following an AI research initiative. Pulls repos from Azure, runs cloud-based agents to generate architecture-compliant documentation with diagrams conforming to Microsoft Azure standards (icons, styling). Features multi-project queueing and parallel execution. Optimized costs and maintained high accuracy using `fastembedder` and Qdrant vector search. Utilized `korki`, `korki-mermaid`, and `weasyprint` with `.mjs` scripts to generate HTML, PDF, Markdown, and editable Draw.io diagrams. Automated publishing pipelines for Backstage-friendly TechDocs pushed directly to enterprise GitHub.
- **KFW_Reports:** Developed and deployed a new version of the KFW Reports application in PowerApps to track business progress goals across UNRWA’s education and health departments, integrating Metaverse DB and SharePoint for attachments.
- **eUNURWA:** Contributing to the eUNURWA platform, working with React Native, PostgreSQL, Metaverse DB, Logic Apps, Dynamics 365, and Power Automate.

### JoBlood — Open-Source Blood Bank System

**Flutter Developer & Backend Developer**  •  *University Final Year Project*

- Built a **full-stack**, multi-role blood bank management system that digitizes the full donation lifecycle — from donor scheduling and staff-recorded donations to lab storage monitoring and administrative oversight.
- **Frontend (Flutter/Dart):** Responsive cross-platform interface (mobile, web, desktop); role-based navigation across four user roles (Donor, Lab Staff, Lab Manager, Admin); a 4-step donation scheduling wizard; live temperature graphs drawn with `CustomPainter`; live Arabic/English language toggle — all using `ValueNotifier` with no external state-management packages.
- **Backend (Shelf/Dart):** Designed and implemented a stateless REST API using Shelf and shelf_router — 30+ endpoints across auth, users, labs, donations, blood units, temperature logs, and scheduling.
- **Database:** Designed the full **PostgreSQL** schema (10+ tables) with relational constraints, foreign keys, and business rules such as unique booking enforcement, auto-calculated blood expiry, and blacklist checks.
- **Deployment:** Containerized with **Docker** for streamlined deployment and environment consistency.
- Portfolio: [JoBlood](/projects/joblood/)

### ISS Dashboard — Mobile SOC for Linux

**Flutter Developer**  •  *University Information Security Project*

- Built a Flutter application that turns a phone into a live **Security Operations Center (SOC)** for a Linux server — one codebase ships in two modes: **host** (runs on the monitored Linux machine) and **client** (Android, connects over SSH).
- **Architecture:** Designed a `CmdRunner` abstraction with `LocalRunner` (`Process.run` / `Process.start`) and `SshRunner` (`dartssh2`) implementations — every panel calls the same `runCmd` / `streamCmd` wrappers, so a single codebase serves both modes with **zero conditional UI logic**.
- **Eight panels across four tabs:** live RX/TX traffic chart from `/proc/net/dev` with a rolling hour/day/month aggregator, streaming `journalctl -f` viewer, Fail2Ban jail control (banned IPs, one-tap unban), UFW / iptables firewall management, a **ransomware detector** running an embedded Python script that computes Shannon entropy on open file descriptors and one-tap `kill -9`s suspect processes, systemd services, Lynis security audits + Nmap scans, and an interactive terminal.
- **Cross-platform:** Single **Flutter** codebase shipping to **Android and Linux desktop**; panels stay alive in memory via `IndexedStack` so streams and timers never reset on tab switch.
- Portfolio: [ISS Dashboard](/projects/iss/)

### NestJS

**Backend Trainee**  •  *Dec 2023 (during university)*

- Collaborated with a NestJS instructor on a social-media project — a developer-friendly application with advanced privacy features — and a shopping application integrated with Shopify for an online client.
- Contributed to both backend and frontend components, working through business logic and API implementation.
- **NoSQL databases:** Self-studied and applied NoSQL concepts (document-oriented and key-value stores), gaining hands-on experience in schema design, querying, and integration.

---

## Achievements

- **ACM Coding Marathon** — Amman, Jordan, May 2024 *(University Competition)* — ranked **19 / 28**.

---

## Projects *(completed during university studies)*

**OOP — Pharmacy Simulator**  
Pharmacy management simulation in C++ focused on object-oriented design for inventory management, sales processing, and customer data storage.  
GitHub: [CPP-Pharmacy-Simulator](https://github.com/MohQaDev/CPP-Pharmacy-Simulator)

**Hardware Store — E-Commerce Website**  
Hardware e-commerce site using HTML, CSS, JavaScript, PHP, and SQL — product listings, basic backend logic, and database interaction.  
GitHub: [Hardware-Store](https://github.com/MohQaDev/Hardware-Store)

**E-Commerce App — UI/UX Design (Figma)**  
E-commerce application interface designed in Figma, applying HCI principles for a clear and user-friendly UI.  
GitHub: [E-Commerce-Design-Figma](https://github.com/MohQaDev/E-Commerce-Design-Figma)

**Social Media Backend — NestJS (Sample)**  
Sample backend for a social media application using NestJS, written under guidance — focused on backend structure and best practices.  
GitHub: [Social-Media-Be-Backend-Sample](https://github.com/MohQaDev/Social-Media-Be-Backend-Sample)

---

## Certifications & Courses

- **Amazon Web Services — Cloud Practitioner Training** *(Jordanian Ministry of Digital Affairs)*  
  Covered cloud fundamentals and cloud architecture at scale. Currently in the process of sitting for the **official AWS Cloud Practitioner certification exam**.  [📜 Course Completion Certificate (PDF)](/AWS_CloudPractitioner_Certificate.pdf)
- **AWS — Basic Cloud Computing Course** — basics of cloud computing and how AWS delivers services at scale.
- **AWS — Basic AI Course** — AI fundamentals: neural networks, evolving algorithms, and core concepts behind building AI systems.
- **Bookkeeping Basics** — Coursera — foundational accounting basics.
- **ISACA Session** — AI & Digital Transformation.

---

## Skills & Attributes

- **Fast learner & adaptable** — picks up new technologies, frameworks, and environments quickly; demonstrated across mobile, backend, web, low-code/cloud platforms, and AI domains.
- **Linux** — daily driver for development; comfortable with the command line, file system, process management, and server-side operations.
- **Languages & Frameworks:** C++, Dart, Flutter, Shelf, NestJS, Node.js, JavaScript, React Native, HTML/CSS, SQL, NoSQL, PostgreSQL, Java, C# / .NET
  - Comfortable working across multiple paradigms and runtimes — primary depth in Dart/Flutter and Node.js, with working knowledge of Java and C# / .NET applied through academic coursework and self-study.
- **Tools & Platforms:** Azure, PowerApps, Power Automate, Dynamics 365, SharePoint, Metaverse DB, Backstage, Firebase, AWS, Figma, Git/GitHub, Linux
- **AI proficiency:** adept at leveraging AI tools and building agentic document generation workflows effectively to accelerate development and optimize operational costs.
