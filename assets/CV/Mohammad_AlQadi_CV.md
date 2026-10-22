# Mohammad Ayman Ghazi Al Qadi

Amman, Jordan | +962-79-767-8128 | mohqa.dev@outlook.com | <a href="https://www.linkedin.com/in/mohammad-al-qadi-a96643261" target="_blank">LinkedIn</a> | Age: 22

---

**About me**

Final-year Computer Science student at PSUT with hands-on experience building full-stack applications across mobile, backend, database, and enterprise cloud layers. Comfortable taking a project from schema design to deployment, and quick to pick up new stacks. Looking to join a team where I can contribute from day one and keep growing as a developer.

<div style="page-break-inside: avoid; break-inside: avoid;">

## EDUCATION

**Princess Sumaya University of Technology** — Amman, Jordan
Bachelor of Science — Major in Computer Science *(ABET Accredited)*
*Sep 2022 – Expected Sep 2026*

- Relevant Coursework: Data Analysis, Software Engineering, Operating Systems, Data Structures, Algorithms, AI, Software Development

**Al-Rowad International Schools** — Riyadh, Saudi Arabia
IGCSE & A-Level *(Tawjihi Equivalency)* | *Graduated 2022*

- A-Level Subjects: Physics, Mathematics, Computer Science
- Grade: A
- Equated Average: 94.4% *(Jordanian Ministry of Education Equivalency)*

## LANGUAGES

- **Arabic** — Native
- **English** — Fluent (Academic & Professional)

</div>
<div style="page-break-inside: avoid; break-inside: avoid;">

## RELEVANT EXPERIENCE

### UNRWA HQA (Headquarters) — Amman, Jordan

**Digital Transformation Intern** | *Aug 2026 – Present*

- **AutoDoc (Enterprise AI Documentation Tool):** Conceived and engineered an automated documentation generator following an enterprise AI research initiative. The system pulls repositories from Azure and deploys cloud-based agents to generate architecture-compliant documentation accompanied by diagrams conforming strictly to Microsoft Azure standards (icons, styling, and layouts), supporting multi-project queueing and parallel agent execution.
  - **Cost & Vector Optimization:** Integrated `fastembedder` and Qdrant vector database storage to drastically reduce AI operational token costs while maintaining high semantic accuracy.
  - **Spec-Driven Rendering:** Leveraged `korki`, `korki-mermaid`, and `weasyprint` driven by custom `.mjs` scripting to render clean HTML, PDF, Markdown, and fully editable Draw.io architecture diagrams directly from specs at minimal cost.
  - **Enterprise Publishing Pipeline:** Automated the end-to-end publishing workflow to generate Backstage-friendly TechDocs, enabling seamless integration and developer viewing across the enterprise GitHub portal.
- **KFW_Reports:** Developed and **deployed** a new version of the KFW Reports application using **PowerApps** to track business progress goals across UNRWA’s education and health departments. Integrated Metaverse databases and **SharePoint** for attachments, adding custom screens, views, and functional features.
- **eUNURWA:** Contributing to the ongoing development of the eUNURWA platform, working with **React Native, PostgreSQL, Metaverse DB, Logic Apps, Dynamics 365, and Power Automate**.

### JoBlood – Open-Source Blood Bank System

**Flutter Developer & Backend Developer** | *University Final Year Project*

- Developing a **full-stack**, multi-role blood bank management system that digitizes the full donation lifecycle — from donor scheduling and staff-recorded donations to lab storage monitoring and administrative oversight.
- **Frontend (Flutter/Dart):** Built a **responsive cross-platform interface** supporting mobile, web, and desktop; implemented **role-based navigation** across four user roles (Donor, Lab Staff, Lab Manager, Admin), a 4-step donation scheduling wizard, live temperature graphs using CustomPainter, and a live Arabic/English language toggle — all using ValueNotifier with no external state management packages.
- **Backend (Shelf/Dart):** Designed and implemented a stateless REST API using Shelf and shelf_router, covering 30+ endpoints across auth, users, labs, donations, blood units, temperature logs, and scheduling.
- **Database:** Designed the full **PostgreSQL** schema (10+ tables) with relational constraints, foreign keys, and business rules such as unique booking enforcement, auto-calculated blood expiry, and blacklist checks.
- **Deployment:** Application is being **containerized using Docker** towards end of development for streamlined deployment and **environment consistency**.
- Portfolio: [JoBlood](https://MohQaDev.github.io/projects/joblood/)

### ISS Dashboard – Mobile SOC for Linux

**Flutter Developer** | *University Information Security Project*

- Built a Flutter application that turns a phone into a live **Security Operations Center (SOC)** for a Linux server — one codebase ships in two modes: **host** (runs on the monitored Linux machine) and **client** (Android, connects over SSH).
- **Architecture:** Designed a `CmdRunner` abstraction with `LocalRunner` (`Process.run` / `Process.start`) and `SshRunner` (`dartssh2`) implementations — every panel calls the same `runCmd` / `streamCmd` wrappers, so a single codebase serves both modes with **zero conditional UI logic**.
- **Eight panels across four tabs:** live RX/TX traffic chart from `/proc/net/dev` with a rolling hour/day/month aggregator, streaming `journalctl -f` viewer, Fail2Ban jail control (banned IPs, one-tap unban), UFW / iptables firewall management, a **ransomware detector** running an embedded Python script that computes Shannon entropy on open file descriptors and one-tap `kill -9`s suspect processes, systemd services, Lynis security audits + Nmap scans, and an interactive terminal.
- **Cross-platform:** Single **Flutter** codebase shipping to **Android and Linux desktop**; panels stay alive in memory via `IndexedStack` so streams and timers never reset on tab switch.
- Portfolio: [ISS Dashboard](https://MohQaDev.github.io/projects/iss/)

### NestJS

**Backend Trainee** | *Dec 2023 During University*

- Collaborated with a NestJS instructor on a social media project — a developer-friendly application with advanced privacy features — and a shopping application integrated with Shopify for an online client.

- Contributed to both backend and frontend components, working through business logic and API implementation to provide the best user experience.

- **NoSQL Databases:** Self-studied and applied NoSQL database concepts (including document-oriented and key-value stores), gaining hands-on experience in schema design, querying, and integration within backend applications.
  
  </div>
  <div style="page-break-inside: avoid; break-inside: avoid;">

## ACHIEVEMENTS

- **ACM Coding Marathon** — Amman, Jordan | May 2024 *(University Competition)*
  - Ranked 19th / 28

</div>

<div style="page-break-inside: avoid; break-inside: avoid;">

## PROJECTS *(All projects completed during university studies)*

**OOP – Pharmacy Simulator**

- Implemented a pharmacy management simulation using C++, focusing on object-oriented design to handle inventory management, sales processing, and customer data storage.
- GitHub: [CPP-Pharmacy-Simulator](https://github.com/MohQaDev/CPP-Pharmacy-Simulator)

</div>

<div style="page-break-inside: avoid; break-inside: avoid;">

**Hardware Store – E-Commerce Website**

- Developed a hardware e-commerce website using HTML, CSS, JavaScript, PHP, and SQL, implementing product listings, basic backend logic, and database interaction.
- GitHub: [Hardware-Store](https://github.com/MohQaDev/Hardware-Store)

</div>

<div style="page-break-inside: avoid; break-inside: avoid;">

**E-Commerce App – UI/UX Design (Figma)**

- Designed an e-commerce application interface using Figma, focusing on human-computer interaction (HCI) principles to create a clear and user-friendly UI.
- GitHub: [E-Commerce-Design-Figma](https://github.com/MohQaDev/E-Commerce-Design-Figma)

</div>

<div style="page-break-inside: avoid; break-inside: avoid;">

**Social Media Backend – NestJS (Sample)**

- Contributed to a backend sample for a social media application using NestJS, written under the guidance of an experienced instructor, focusing on backend structure and best practices.

- GitHub: [Social-Media-Be-Backend-Sample](https://github.com/MohQaDev/Social-Media-Be-Backend-Sample)
  
  </div>
  <div style="page-break-inside: avoid; break-inside: avoid;">

## CERTIFICATIONS & COURSES

**Amazon Web Services – Cloud Practitioner Training**

- Completed the AWS Cloud Practitioner training program offered through the **Jordanian Ministry of Digital Affairs**, covering cloud fundamentals, and cloud architecture at scale.
- Currently in the process of sitting for the **official AWS Cloud Practitioner certification exam**.

</div>
<div style="page-break-inside: avoid; break-inside: avoid;">

**AWS – Basic Cloud Computing Course**

- Completed an AWS course covering the basics of cloud computing and how AWS delivers services at scale.

</div>

<div style="page-break-inside: avoid; break-inside: avoid;">

**AWS – Basic AI Course**

- Completed an AWS course on AI fundamentals, covering neural networks, evolving algorithms, and core concepts behind building AI systems.

</div>

<div style="page-break-inside: avoid; break-inside: avoid;">

**Bookkeeping Basics** — Coursera

- Completed a Coursera course on bookkeeping, gaining foundational knowledge in accounting basics.

</div>

<div style="page-break-inside: avoid; break-inside: avoid;">

**ISACA Session — AI & Digital Transformation**

- Attended an ISACA session focused on AI and digital transformation.

</div>

## SKILLS & ATTRIBUTES

- **Fast Learner & Adaptable:** Demonstrates a strong ability to rapidly pick up new technologies, frameworks, and environments — evidenced by contributions across mobile, backend, web, low-code/cloud platforms, and AI tooling.
  - **Linux:** Daily driver for development — comfortable with the command line, file system, process management, and server-side operations.
- **Languages & Frameworks:** Power Fx, C++, Dart, Flutter, Shelf, NestJS, NodeJs, JavaScript, React Native, HTML/CSS, SQL, NoSQL, PostgreSQL, Java, C# / .NET
  - Comfortable working across multiple paradigms and runtimes — primary depth in Dart/Flutter and Node.js, with working knowledge of Java and C# / .NET applied through academic coursework and self-study.
- **Tools & Platforms:** Azure, PowerApps, Power Automate, Dynamics 365, SharePoint, Metaverse DB, Backstage, Firebase, AWS, Figma, Git/GitHub, Linux
- **AI Proficiency:** Adept at leveraging AI tools and building agentic document generation workflows effectively to accelerate development and optimize operational costs.
