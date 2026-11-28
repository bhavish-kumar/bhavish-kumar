<p align="center">
  <img src="./assets/banner.png" alt="Bhavish Kumar — I build web apps, APIs and AI-powered tools that solve real problems" width="100%">
</p>

<p align="center">
  <a href="https://bhavish-kumar-portfolio.netlify.app/">Portfolio</a> ·
  <a href="https://www.linkedin.com/in/bhavish-kumaar">LinkedIn</a> ·
  <a href="mailto:bhavishkumar799@gmail.com">Email</a>
  <!-- · <a href="UPWORK_URL">Upwork</a> · <a href="FIVERR_URL">Fiverr</a> -->
</p>

## Hi, I'm Bhavish 👋

I'm a **Full Stack Developer** from Hyderabad, Pakistan. I build complete web applications, from the React interface to the API and database behind it, and I connect them to large language models when AI makes the product more useful.

- 🧩 I've built an AI document automation platform, a CRM, a library management system, an AI interview practice platform and an AI student assistant.
- 🤖 I integrate LLMs (Google Gemini, Groq) into real apps, and I design them to say "I don't know" instead of inventing answers.
- 🎓 I'm finishing my BS in Computer Science and I'm open to **full-time roles (on-site, hybrid or remote)** and **freelance projects**.

## 🛠️ Tech stack

**Frontend**

<img src="https://skillicons.dev/icons?i=react,nextjs,ts,js,html,css,tailwind,vite" alt="React, Next.js, TypeScript, JavaScript, HTML, CSS, Tailwind, Vite">

**Backend & databases**

<img src="https://skillicons.dev/icons?i=nodejs,express,python,mongodb,postgres,supabase,sqlite" alt="Node.js, Express, Python, MongoDB, PostgreSQL, Supabase, SQLite">

**AI & integration:** LLM APIs (Google Gemini, Groq, OpenAI) · n8n workflow automation · retrieval over custom data · REST APIs · JWT authentication

**Tools**

<img src="https://skillicons.dev/icons?i=git,github,vscode,jest" alt="Git, GitHub, VS Code, Jest">

## 🚀 Featured projects

### [DocFlow: AI Document & Workflow Automation](https://github.com/bhavish-kumar/DocFlow-AI-Document-Automation)
**An AI platform that reads invoices, purchase orders and goods receipts, checks them against each other, and sends problems to a person for review.**
Documents are uploaded as PDFs or scans. DocFlow reads them with OCR, classifies each one with a rules + machine-learning model, and extracts header fields and line items. It then runs invoice ↔ PO ↔ GRN **3-way matching**, detects duplicate invoices and flags unusual ones, and puts anything that fails into a review queue where a person approves or rejects it. Two AI assistants answer questions: one searches the documents with citations (RAG), the other turns plain-English questions into safe, read-only SQL. All AI runs **locally**, so no document leaves the machine and no paid API key is needed. It has JWT login with roles, audit logs and 351 passing tests.

`Python` `FastAPI` `React` `PostgreSQL` `Tesseract OCR` `scikit-learn` `RAG` `JWT + RBAC`

### [AI Interview Assistant](https://github.com/bhavish-kumar/AI-Interview-Assistant)
**Practice job interviews and get instant AI feedback.**
Candidates pick a track (software engineering, DSA, system design, data science, behavioral and more), answer by typing or speaking, and Google Gemini scores each answer with short tips. Users can upload a resume PDF for an AI summary and track their scores over time.

`Next.js 15` `TypeScript` `MongoDB` `Gemini API` `Tailwind CSS` `JWT`

### [SZABIST AI Student Assistant](https://github.com/bhavish-kumar/SZABIST-AI-CHATBOT)
**An AI assistant that answers student questions using official university data.**
It answers questions about admissions, programs, fees, campus, policies and class timetables for SZABIST Hyderabad. Answers are grounded in stored university data through a retrieval step, and missing facts are flagged as unverified rather than made up. It has both a terminal chatbot and a responsive React web app with dark mode.

`Python` `Groq LLM` `Retrieval` `React` `Vite`

### [Smart Business CRM](https://github.com/bhavish-kumar/Smart-business-CRM)
**A CRM for small businesses to manage their sales pipeline.**
It tracks leads from New to Won, converts them into clients, schedules follow-ups and manages team roles. A dashboard and reports show conversion rates with charts.

`React 19` `Node.js` `Express 5` `PostgreSQL (Supabase)` `JWT`

### [SZABIST Smart Digital Library](https://github.com/bhavish-kumar/Szabist-library-management-system)
**A full library system with separate student and librarian portals.**
Students can search the catalogue, reserve books, join a waitlist that promotes them automatically (with an email alert) when a copy is returned, renew books and download e-books. Librarians manage books, issues, returns and fines, with analytics and CSV export. Integration tests use Jest and Supertest.

`React` `Node.js` `Express` `SQLite` `Jest`

## 🤖 AI Automation & n8n Workflows

Beyond full-stack apps, I build automations in **n8n** that connect email, AI models and web services.

### AI-Powered Email Draft Automation (Orders & Inquiries)
**Reads new emails, sorts them as orders or inquiries, and drafts a reply for each one.**
A Gmail trigger picks up each incoming email. A Text Classifier using an OpenAI chat model decides whether it is an **order** or an **inquiry**, and an OpenAI model writes a reply suited to that type. The reply is saved as a **Gmail draft**, not sent, so a person can check and edit it before it goes out.

<p align="center">
  <img src="./assets/n8n/email-draft-workflow.webp" alt="n8n workflow: Gmail Trigger, Text Classifier with OpenAI Chat Model, Order and Inquiry branches with OpenAI replies, and Gmail Create a draft" width="100%">
</p>

<table>
  <tr>
    <th>Incoming email</th>
    <th>Draft created by the workflow</th>
  </tr>
  <tr>
    <td align="center" valign="top"><img src="./assets/n8n/email-order-request.webp" alt="Test email asking to order a pizza with extra ketchup and asking for the price and delivery time" width="360"></td>
    <td align="center" valign="top"><img src="./assets/n8n/email-ai-draft-reply.webp" alt="AI-generated draft reply to the pizza order email, saved in Gmail for review" width="360"></td>
  </tr>
</table>

`n8n` `Gmail` `OpenAI` `Text Classifier`

### Website Error Detection
**A scheduled website availability check that emails an alert when the site does not respond correctly.**
A Schedule Trigger starts the check, an HTTP Request calls the website URL, and an If node checks the result. When the site is available, the workflow only records its status. When it is not, it marks the site as offline and sends an alert email through Gmail. The offline path was tested using an endpoint that returns **HTTP 503**.

<p align="center">
  <img src="./assets/n8n/website-error-detection-workflow.webp" alt="n8n workflow: Schedule Trigger, Edit Fields, HTTP Request to a test URL returning 503, If node, and Gmail alert on the offline branch" width="100%">
</p>

<table>
  <tr>
    <td align="center" valign="top" width="50%"><img src="./assets/n8n/website-down-alert.webp" alt="Website Down Alert email received from the n8n workflow during the HTTP 503 test" width="360"></td>
    <td valign="top">
      <b>What happens in the test</b><br><br>
      1. The schedule starts the check.<br>
      2. The HTTP request receives a 503 response.<br>
      3. The If node sends it down the offline path.<br>
      4. Gmail sends the <i>Website Down Alert!</i> email shown here.
    </td>
  </tr>
</table>

`n8n` `HTTP Request` `Gmail` `Schedule Trigger`

## 📫 Let's work together

I'm available for **junior developer roles (on-site, hybrid or remote)** and **freelance projects**, including web apps, REST APIs, dashboards and AI chatbots.
The best way to reach me is by [email](mailto:bhavishkumar799@gmail.com) or on [LinkedIn](https://www.linkedin.com/in/bhavish-kumaar).
