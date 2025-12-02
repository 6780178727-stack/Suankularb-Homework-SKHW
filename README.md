
<html lang="th">
  <head>
    <meta charset="UTF-8" />
    <title>SKHW Homework Tracker</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <style>
      :root {
        font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
        color: #0f172a;
        background: linear-gradient(to bottom, #fff1f2, #f8fafc);
      }

      *,
      *::before,
      *::after {
        box-sizing: border-box;
      }

      body {
        margin: 0;
      }

      .app-root {
        min-height: 100vh;
      }

      .container {
        max-width: 1120px;
        margin: 0 auto;
        padding: 16px;
      }

      .header {
        position: sticky;
        top: 0;
        z-index: 10;
        backdrop-filter: blur(10px);
        background: rgba(255, 255, 255, 0.9);
        border-bottom: 1px solid #e5e7eb;
      }

      .header-inner {
        max-width: 1120px;
        margin: 0 auto;
        padding: 12px 16px;
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 12px;
      }

      .brand {
        display: flex;
        align-items: center;
        gap: 12px;
      }

      .brand-icon {
        width: 44px;
        height: 44px;
        border-radius: 18px;
        background: transparent;
        display: flex;
        align-items: center;
        justify-content: center;
        overflow: hidden;
      }

      .brand-text h1 {
        font-size: 18px;
        margin: 0;
      }

      .brand-text p {
        margin: 2px 0 0;
        font-size: 11px;
        color: #6b7280;
      }

      .btn {
        border-radius: 999px;
        padding: 6px 14px;
        font-size: 13px;
        border: 1px solid #e5e7eb;
        background: white;
        cursor: pointer;
        display: inline-flex;
        align-items: center;
        gap: 6px;
      }

      .btn-primary {
        background: #e11d48;
        color: white;
        border-color: #e11d48;
      }

      .btn-sm {
        padding: 4px 10px;
        font-size: 12px;
      }

      .btn-ghost {
        border-color: transparent;
        background: transparent;
      }

      .btn:disabled {
        opacity: 0.6;
        cursor: default;
      }

      .tab-list {
        display: grid;
        grid-template-columns: repeat(3, minmax(0, 1fr));
        margin-top: 16px;
        border-radius: 999px;
        background: #f3f4f6;
        padding: 4px;
        gap: 4px;
      }

      .tab {
        border-radius: 999px;
        padding: 8px 10px;
        font-size: 13px;
        border: none;
        cursor: pointer;
        background: transparent;
        color: #4b5563;
      }

      .tab-active {
        background: white;
        box-shadow: 0 1px 4px rgba(148, 27, 82, 0.2);
        color: #be123c;
        font-weight: 600;
      }

      .main {
        padding: 16px 0 32px;
      }

      .card {
        background: white;
        border-radius: 16px;
        border: 1px solid #e5e7eb;
        padding: 16px 16px 18px;
        margin-bottom: 16px;
        box-shadow: 0 2px 5px rgba(15, 23, 42, 0.03);
      }

      .card-title {
        font-size: 16px;
        margin: 0 0 4px;
      }

      .card-description {
        font-size: 12px;
        color: #6b7280;
        margin: 0 0 10px;
      }

      .grid-3 {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
        gap: 12px;
      }

      .label {
        display: block;
        font-size: 12px;
        margin-bottom: 4px;
        color: #374151;
      }

      .input,
      .textarea,
      .select {
        width: 100%;
        border-radius: 12px;
        border: 1px solid #e5e7eb;
        padding: 6px 10px;
        font-size: 13px;
      }

      .textarea {
        min-height: 70px;
        resize: vertical;
      }

      .helper {
        font-size: 11px;
        color: #6b7280;
        margin-top: 3px;
      }

      .row-between {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 8px;
        margin-top: 8px;
      }

      .chip {
        display: inline-flex;
        align-items: center;
        border-radius: 999px;
        border: 1px solid #e5e7eb;
        font-size: 11px;
        padding: 4px 8px;
        margin-right: 6px;
        margin-bottom: 4px;
      }

      .chip-filter-group {
        display: flex;
        flex-wrap: wrap;
        gap: 8px;
        align-items: center;
      }

      .table {
        width: 100%;
        border-collapse: collapse;
        font-size: 13px;
      }

      .table th,
      .table td {
        padding: 8px 6px;
        border-bottom: 1px solid #e5e7eb;
        text-align: left;
      }

      .table th {
        font-size: 12px;
        color: #6b7280;
        font-weight: 500;
      }

      .badge {
        display: inline-flex;
        border-radius: 999px;
        padding: 2px 8px;
        font-size: 11px;
        border: 1px solid transparent;
      }

      .badge-outline {
        border-color: #e5e7eb;
        background: #f9fafb;
      }

      .badge-danger {
        background: #fee2e2;
        color: #b91c1c;
      }

      .badge-warn {
        background: #fef3c7;
        color: #92400e;
      }

      .badge-soft {
        background: #f3f4f6;
        color: #374151;
      }

      .footer {
        max-width: 1120px;
        margin: 0 auto;
        padding: 24px 16px 32px;
        font-size: 11px;
        text-align: center;
        color: #9ca3af;
      }

      .mt-8 {
        margin-top: 8px;
      }

      .mt-12 {
        margin-top: 12px;
      }

      .text-right {
        text-align: right;
      }

      .text-center {
        text-align: center;
      }

      .hidden {
        display: none;
      }

      @media (max-width: 640px) {
        .header-inner {
          flex-direction: column;
          align-items: flex-start;
        }
      }
    </style>
  </head>
  <body>
    <div class="app-root">
      <header class="header">
        <div class="header-inner">
          <div class="brand">
            <div class="brand-icon">
              <!-- ใส่ไฟล์ skhw-logo.png ไว้โฟลเดอร์เดียวกับ index.html -->
              <img
                src="skhw-logo.png"
                alt="SKHW Homework Tracker logo"
                style="width: 100%; height: 100%; object-fit: contain"
              />
            </div>
            <div class="brand-text">
              <h1>SKHW Homework Tracker</h1>
              <p>Smart Learning • Suankularb Wittayalai</p>
            </div>
          </div>
          <div style="display: flex; gap: 8px">
            <button class="btn btn-sm" id="export-btn">⬇ Export</button>
            <label class="btn btn-sm" style="position: relative; overflow: hidden">
              ⬆ Import
              <input
                id="import-input"
                type="file"
                accept="application/json"
                style="position: absolute; inset: 0; opacity: 0; cursor: pointer"
              />
            </label>
          </div>
        </div>
      </header>

      <main class="container main">
        <!-- Tabs -->
        <div class="tab-list">
          <button class="tab tab-active" data-tab="teacher">สำหรับครู</button>
          <button class="tab" data-tab="student">สำหรับนักเรียน</button>
          <button class="tab" data-tab="admin">แดชบอร์ดผู้บริหาร</button>
        </div>

        <!-- TEACHER TAB -->
        <section id="tab-teacher" class="tab-panel">
          <div class="card">
            <h2 class="card-title">มอบหมายการบ้าน</h2>
            <p class="card-description">ระบุรายวิชา ระดับชั้น และกำหนดส่ง</p>

            <div class="grid-3 mt-12">
              <div>
                <label class="label">รายวิชา</label>
                <select id="subject-select" class="select"></select>
              </div>
              <div>
                <label class="label">ระดับชั้น</label>
                <select id="class-select" class="select"></select>
              </div>
              <div>
                <label class="label">หัวข้อการบ้าน</label>
                <input
                  id="title-input"
                  class="input"
                  placeholder="เช่น แบบฝึกหัดหน้าที่ 45 ข้อ 1–10"
                />
              </div>
            </div>

            <div class="grid-3 mt-12">
              <div>
                <label class="label">วันที่มอบ</label>
                <input id="assigned-input" type="date" class="input" />
              </div>
              <div>
                <label class="label">กำหนดส่ง</label>
                <input id="due-input" type="date" class="input" />
              </div>
              <div>
                <label class="label">แนบลิงก์</label>
                <input
                  id="link-input"
                  class="input"
                  placeholder="Google Doc / Classroom / YouTube"
                />
              </div>
            </div>

            <div class="mt-12">
              <label class="label">คำอธิบาย</label>
              <textarea
                id="desc-input"
                class="textarea"
                placeholder="รายละเอียด / เกณฑ์การให้คะแนน"
              ></textarea>
            </div>

            <div class="mt-12">
              <span class="label">แม่แบบด่วน</span>
              <div id="template-buttons"></div>
            </div>

            <div class="row-between mt-12">
              <p class="helper">ระบบจะบันทึกข้อมูลอัตโนมัติในอุปกรณ์นี้ (ต้นแบบ)</p>
              <button id="add-homework-btn" class="btn btn-primary">เพิ่มการบ้าน</button>
            </div>
          </div>

          <div class="card">
            <div class="row-between">
              <div>
                <h2 class="card-title">รายการการบ้านทั้งหมด</h2>
                <p class="card-description">จัดเรียง/ค้นหาตามตัวกรองด้านขวา</p>
              </div>
              <div class="chip-filter-group">
                <span class="chip">ตัวกรอง</span>
                <select id="filter-subject" class="select" style="max-width: 150px"></select>
                <select id="filter-class" class="select" style="max-width: 120px"></select>
                <input
                  id="filter-search"
                  class="input"
                  style="min-width: 180px"
                  placeholder="ค้นหา..."
                />
              </div>
            </div>

            <div class="mt-12" style="overflow-x: auto">
              <table class="table">
                <thead>
                  <tr>
                    <th>หัวข้อ</th>
                    <th>วิชา</th>
                    <th>ชั้น</th>
                    <th>มอบ</th>
                    <th>กำหนดส่ง</th>
                    <th class="text-right">จัดการ</th>
                  </tr>
                </thead>
                <tbody id="teacher-table-body"></tbody>
              </table>
            </div>
          </div>
        </section>

        <!-- STUDENT TAB -->
        <section id="tab-student" class="tab-panel hidden">
          <div class="card">
            <h2 class="card-title">นักเรียนเช็คการบ้าน</h2>
            <p class="card-description">
              เลือกระดับชั้นและกรอกชื่อนักเรียนเพื่อบันทึกความคืบหน้าเฉพาะบุคคล
            </p>

            <div class="grid-3 mt-12">
              <div>
                <label class="label">ระดับชั้น</label>
                <select id="student-class-select" class="select"></select>
              </div>
              <div style="grid-column: span 2">
                <label class="label">ชื่อนักเรียน</label>
                <input
                  id="student-name-input"
                  class="input"
                  placeholder="พิมพ์ชื่อ–นามสกุล"
                />
                <p class="helper">ระบบจะจดจำสถานะการบ้านตามชื่อที่กรอก (ใช้ชื่อเดิมทุกครั้ง)</p>
              </div>
            </div>

            <div class="row-between mt-12">
              <label style="display: flex; align-items: center; gap: 6px">
                <input type="checkbox" id="show-completed-checkbox" checked />
                <span style="font-size: 13px">แสดงรายการที่ทำแล้ว</span>
              </label>
              <div id="student-summary" style="font-size: 13px; color: #4b5563"></div>
            </div>

            <div id="student-list" class="mt-12"></div>
          </div>
        </section>

        <!-- ADMIN TAB -->
        <section id="tab-admin" class="tab-panel hidden">
          <div class="card">
            <h2 class="card-title">จำนวนการบ้านตามรายวิชา</h2>
            <p class="card-description">
              ใช้ดูภาพรวมภาระงานนักเรียนในแต่ละวิชา (นับตามจำนวนงานที่มอบ)
            </p>
            <div class="mt-12" style="overflow-x: auto">
              <table class="table">
                <thead>
                  <tr>
                    <th>วิชา</th>
                    <th>จำนวนการบ้าน</th>
                  </tr>
                </thead>
                <tbody id="subject-summary-body"></tbody>
              </table>
            </div>
          </div>

          <div class="card">
            <h2 class="card-title">สรุปภาพรวมตามระดับชั้น</h2>
            <p class="card-description">
              จำนวนงานที่มอบและจำนวนการติ๊ก “ทำแล้ว” (รวมทุกนักเรียน) เพื่อประเมินแนวโน้มการส่งงาน
            </p>
            <div class="mt-12" style="overflow-x: auto">
              <table class="table">
                <thead>
                  <tr>
                    <th>ระดับชั้น</th>
                    <th>จำนวนงานทั้งหมด</th>
                    <th>จำนวนติ๊กทำแล้ว (รวม)</th>
                    <th>% การทำงาน (คร่าว ๆ)</th>
                  </tr>
                </thead>
                <tbody id="class-summary-body"></tbody>
              </table>
            </div>
            <p class="helper mt-8">
              * ตัวเลข % เป็นการประเมินจากจำนวนการติ๊กทำแล้ว (ไม่ได้แยกตามรายชื่อจริงในระดับระบบใหญ่)
            </p>
          </div>
        </section>
      </main>

      <footer class="footer">
        © <span id="year-span"></span> Suankularb Wittayalai • SKHW Homework Tracker • ICT Smart
        School Initiative
      </footer>
    </div>

    <script>
      // -----------------------------
      // Data & Helpers
      // -----------------------------
      const SUBJECTS = [
        "Thai",
        "Mathematics",
        "Science",
        "Physics",
        "Chemistry",
        "Biology",
        "English",
        "Social Studies",
        "Computer",
        "Health & PE",
        "Art",
        "Music"
      ];

      const CLASS_LEVELS = ["M.1", "M.2", "M.3", "M.4", "M.5", "M.6"];

      const QUICK_TEMPLATES = [
        { title: "แบบฝึกหัดหน้า 45 ข้อ 1–10", description: "ให้แสดงวิธีทำทุกข้อ" },
        { title: "บทอ่าน Unit 3 + คำศัพท์ 20 คำ", description: "จดลงสมุดและถ่ายรูปแนบ" },
        { title: "Worksheet เรื่องแรงและการเคลื่อนที่", description: "ทำข้อ 1–8" }
      ];

      const LS_KEYS = {
        HOMEWORKS: "skhw_hw_items_v1",
        PROGRESS: "skhw_hw_progress_v1",
        SEEDED: "skhw_hw_seeded_v1"
      };

      let items = [];
      let progress = {}; // studentName -> { homeworkId: boolean }

      function isoToday() {
        const d = new Date();
        return d.toISOString().slice(0, 10);
      }

      function daysUntil(dateStr) {
        const now = new Date();
        const due = new Date(dateStr + "T00:00:00");
        const diff = due.getTime() - now.getTime();
        return Math.ceil(diff / (1000 * 60 * 60 * 24));
      }

      function displayDate(d) {
        try {
          return new Date(d + "T00:00:00").toLocaleDateString();
        } catch {
          return d;
        }
      }

      function dueLabel(days) {
        if (days < 0) return { text: "เลยกำหนด " + Math.abs(days) + " วัน", className: "badge badge-danger" };
        if (days === 0) return { text: "ถึงกำหนดวันนี้", className: "badge badge-warn" };
        if (days <= 2) return { text: "อีก " + days + " วัน", className: "badge badge-soft" };
        return { text: "อีก " + days + " วัน", className: "badge badge-outline" };
      }

      function uid() {
        return (
          Math.random().toString(36).slice(2, 10) +
          Date.now().toString(36).slice(-4)
        );
      }

      function loadHomeworks() {
        try {
          const rawNew = localStorage.getItem(LS_KEYS.HOMEWORKS);
          if (rawNew) return JSON.parse(rawNew);
          const rawOld = localStorage.getItem("skv_hw_items_v1");
          return rawOld ? JSON.parse(rawOld) : [];
        } catch {
          return [];
        }
      }

      function saveHomeworks() {
        localStorage.setItem(LS_KEYS.HOMEWORKS, JSON.stringify(items));
      }

      function loadProgress() {
        try {
          const rawNew = localStorage.getItem(LS_KEYS.PROGRESS);
          if (rawNew) return JSON.parse(rawNew);
          const rawOld = localStorage.getItem("skv_hw_progress_v1");
          return rawOld ? JSON.parse(rawOld) : {};
        } catch {
          return {};
        }
      }

      function saveProgress() {
        localStorage.setItem(LS_KEYS.PROGRESS, JSON.stringify(progress));
      }

      // -----------------------------
      // Init DOM
      // -----------------------------
      document.addEventListener("DOMContentLoaded", () => {
        document.getElementById("year-span").textContent = new Date().getFullYear();

        // Fill selects
        const subjectSelect = document.getElementById("subject-select");
        const classSelect = document.getElementById("class-select");
        const filterSubject = document.getElementById("filter-subject");
        const filterClass = document.getElementById("filter-class");
        const studentClassSelect = document.getElementById("student-class-select");

        SUBJECTS.forEach((s) => {
          const o1 = document.createElement("option");
          o1.value = s;
          o1.textContent = s;
          subjectSelect.appendChild(o1);

          const o2 = document.createElement("option");
          o2.value = s;
          o2.textContent = s;
          filterSubject.appendChild(o2);
        });
        const allSubOpt = document.createElement("option");
        allSubOpt.value = "ALL";
        allSubOpt.textContent = "ทุกวิชา";
        filterSubject.insertBefore(allSubOpt, filterSubject.firstChild);
        filterSubject.value = "ALL";

        CLASS_LEVELS.forEach((c) => {
          const o1 = document.createElement("option");
          o1.value = c;
          o1.textContent = c;
          classSelect.appendChild(o1);

          const o2 = document.createElement("option");
          o2.value = c;
          o2.textContent = c;
          filterClass.appendChild(o2);

          const o3 = document.createElement("option");
          o3.value = c;
          o3.textContent = c;
          studentClassSelect.appendChild(o3);
        });
        const allClassOpt = document.createElement("option");
        allClassOpt.value = "ALL";
        allClassOpt.textContent = "ทุกชั้น";
        filterClass.insertBefore(allClassOpt, filterClass.firstChild);
        filterClass.value = "ALL";

        studentClassSelect.value = CLASS_LEVELS[0];

        // Quick templates
        const tplContainer = document.getElementById("template-buttons");
        QUICK_TEMPLATES.forEach((tpl) => {
          const btn = document.createElement("button");
          btn.type = "button";
          btn.className = "btn btn-sm";
          btn.style.marginRight = "6px";
          btn.style.marginTop = "4px";
          btn.textContent = "➕ " + tpl.title;
          btn.addEventListener("click", () => {
            document.getElementById("title-input").value = tpl.title;
            if (tpl.description) {
              document.getElementById("desc-input").value = tpl.description;
            }
          });
          tplContainer.appendChild(btn);
        });

        // Tabs
        document.querySelectorAll(".tab").forEach((btn) => {
          btn.addEventListener("click", () => {
            const tab = btn.getAttribute("data-tab");
            document
              .querySelectorAll(".tab")
              .forEach((b) => b.classList.remove("tab-active"));
            btn.classList.add("tab-active");
            document
              .querySelectorAll(".tab-panel")
              .forEach((p) => p.classList.add("hidden"));
            document.getElementById("tab-" + tab).classList.remove("hidden");
          });
        });

        // Load data
        const seeded = localStorage.getItem(LS_KEYS.SEEDED);
        items = loadHomeworks();
        if (!seeded && items.length === 0) {
          items = [
            {
              id: uid(),
              title: "Worksheet บทที่ 2",
              subject: "Mathematics",
              classLevel: "M.2",
              assignedDate: isoToday(),
              dueDate: isoToday(),
              description: "ทำข้อ 1–10"
            },
            {
              id: uid(),
              title: "Lab Report เคมี",
              subject: "Chemistry",
              classLevel: "M.5",
              assignedDate: isoToday(),
              dueDate: isoToday(),
              description: "ใส่รูปผลทดลอง"
            },
            {
              id: uid(),
              title: "อ่านบทที่ 4 + สรุปย่อ",
              subject: "English",
              classLevel: "M.3",
              assignedDate: isoToday(),
              dueDate: isoToday(),
              description: "ครึ่งหน้า"
            }
          ];
          localStorage.setItem(LS_KEYS.SEEDED, "1");
          saveHomeworks();
        }
        progress = loadProgress();

        // Set default dates
        document.getElementById("assigned-input").value = isoToday();
        document.getElementById("due-input").value = isoToday();

        // Event handlers
        document
          .getElementById("add-homework-btn")
          .addEventListener("click", onAddHomework);

        document
          .getElementById("filter-subject")
          .addEventListener("change", renderAll);
        document
          .getElementById("filter-class")
          .addEventListener("change", renderAll);
        document
          .getElementById("filter-search")
          .addEventListener("input", renderAll);

        document
          .getElementById("student-class-select")
          .addEventListener("change", renderStudent);
        document
          .getElementById("student-name-input")
          .addEventListener("input", renderStudent);
        document
          .getElementById("show-completed-checkbox")
          .addEventListener("change", renderStudent);

        document
          .getElementById("export-btn")
          .addEventListener("click", onExport);
        document
          .getElementById("import-input")
          .addEventListener("change", onImport);

        // Initial render
        renderAll();
      });

      function onAddHomework() {
        const title = document.getElementById("title-input").value.trim();
        if (!title) return;
        const subject = document.getElementById("subject-select").value;
        const classLevel = document.getElementById("class-select").value;
        const assignedDate = document.getElementById("assigned-input").value || isoToday();
        const dueDate = document.getElementById("due-input").value || isoToday();
        const link = document.getElementById("link-input").value.trim();
        const description = document.getElementById("desc-input").value.trim();

        const hw = {
          id: uid(),
          title,
          subject,
          classLevel,
          assignedDate,
          dueDate,
          link: link || undefined,
          description: description || undefined
        };
        items.unshift(hw);
        saveHomeworks();

        document.getElementById("title-input").value = "";
        document.getElementById("link-input").value = "";
        document.getElementById("desc-input").value = "";

        renderAll();
      }

      function renderAll() {
        renderTeacher();
        renderStudent();
        renderAdmin();
      }

      // -------- Teacher render --------
      function renderTeacher() {
        const tbody = document.getElementById("teacher-table-body");
        tbody.innerHTML = "";

        const filterSubject = document.getElementById("filter-subject").value;
        const filterClass = document.getElementById("filter-class").value;
        const q = document.getElementById("filter-search").value.trim().toLowerCase();

        let list = items.slice();
        list = list.filter((i) =>
          filterSubject === "ALL" ? true : i.subject === filterSubject
        );
        list = list.filter((i) =>
          filterClass === "ALL" ? true : i.classLevel === filterClass
        );
        if (q) {
          list = list.filter((i) => {
            return (
              i.title.toLowerCase().includes(q) ||
              (i.description || "").toLowerCase().includes(q) ||
              i.subject.toLowerCase().includes(q) ||
              i.classLevel.toLowerCase().includes(q)
            );
          });
        }
        list.sort((a, b) => a.dueDate.localeCompare(b.dueDate));

        if (list.length === 0) {
          const tr = document.createElement("tr");
          const td = document.createElement("td");
          td.colSpan = 6;
          td.className = "text-center";
          td.textContent = "ยังไม่มีการบ้าน หรือเงื่อนไขตัวกรองไม่ตรงกับข้อมูล";
          tr.appendChild(td);
          tbody.appendChild(tr);
          return;
        }

        list.forEach((i) => {
          const tr = document.createElement("tr");

          const tdTitle = document.createElement("td");
          tdTitle.innerHTML = `<div>${i.title}</div>`;
          if (i.description) {
            const d = document.createElement("div");
            d.className = "helper";
            d.textContent = i.description;
            tdTitle.appendChild(d);
          }
          if (i.link) {
            const d = document.createElement("div");
            const a = document.createElement("a");
            a.href = i.link;
            a.target = "_blank";
            a.rel = "noreferrer";
            a.textContent = "เปิดลิงก์";
            a.style.color = "#2563eb";
            a.className = "helper";
            d.appendChild(a);
            tdTitle.appendChild(d);
          }
          tr.appendChild(tdTitle);

          const tdSub = document.createElement("td");
          tdSub.textContent = i.subject;
          tr.appendChild(tdSub);

          const tdClass = document.createElement("td");
          tdClass.textContent = i.classLevel;
          tr.appendChild(tdClass);

          const tdAssigned = document.createElement("td");
          tdAssigned.className = "helper";
          tdAssigned.textContent = displayDate(i.assignedDate);
          tr.appendChild(tdAssigned);

          const tdDue = document.createElement("td");
          const days = daysUntil(i.dueDate);
          const badge = dueLabel(days);
          const span = document.createElement("span");
          span.className = badge.className;
          span.textContent = badge.text;
          tdDue.appendChild(span);
          tr.appendChild(tdDue);

          const tdActions = document.createElement("td");
          tdActions.className = "text-right";
          const btn = document.createElement("button");
          btn.className = "btn btn-ghost btn-sm";
          btn.textContent = "ลบ";
          btn.addEventListener("click", () => {
            removeHomework(i.id);
          });
          tdActions.appendChild(btn);
          tr.appendChild(tdActions);

          tbody.appendChild(tr);
        });
      }

      function removeHomework(id) {
        items = items.filter((i) => i.id !== id);
        // remove from progress
        Object.keys(progress).forEach((stu) => {
          if (progress[stu] && progress[stu][id] !== undefined) {
            delete progress[stu][id];
          }
        });
        saveHomeworks();
        saveProgress();
        renderAll();
      }

      // -------- Student render --------
      function renderStudent() {
        const studentClass = document.getElementById("student-class-select").value;
        const studentName = document
          .getElementById("student-name-input")
          .value.trim();
        const showCompleted = document.getElementById(
          "show-completed-checkbox"
        ).checked;

        const listContainer = document.getElementById("student-list");
        const summary = document.getElementById("student-summary");
        listContainer.innerHTML = "";

        let list = items.filter((i) => i.classLevel === studentClass);
        list.sort((a, b) => a.dueDate.localeCompare(b.dueDate));

        const studentData = studentName ? progress[studentName] || {} : {};
        const visible = list.filter((i) => {
          const done = !!studentData[i.id];
          return showCompleted ? true : !done;
        });

        summary.textContent =
          "ทั้งหมด " + list.length + " งาน • แสดง " + visible.length;

        if (visible.length === 0) {
          const div = document.createElement("div");
          div.className = "text-center helper";
          div.style.padding = "32px 0";
          div.textContent =
            "ยังไม่มีการบ้านสำหรับชั้นนี้ หรือทำครบแล้ว 🎉";
          listContainer.appendChild(div);
          return;
        }

        visible.forEach((i) => {
          const card = document.createElement("div");
          card.className = "card";
          card.style.padding = "12px";
          card.style.marginBottom = "10px";
          card.style.borderRadius = "14px";

          const row = document.createElement("div");
          row.className = "row-between";

          const left = document.createElement("div");
          const topRow = document.createElement("div");
          topRow.style.marginBottom = "4px";

          const badgeSub = document.createElement("span");
          badgeSub.className = "badge badge-outline";
          badgeSub.style.marginRight = "6px";
          badgeSub.textContent = i.subject;
          topRow.appendChild(badgeSub);

          const days = daysUntil(i.dueDate);
          const badgeInfo = dueLabel(days);
          const badgeDue = document.createElement("span");
          badgeDue.className = badgeInfo.className;
          badgeDue.textContent = badgeInfo.text;
          topRow.appendChild(badgeDue);
          left.appendChild(topRow);

          const titleDiv = document.createElement("div");
          titleDiv.style.fontWeight = "600";
          titleDiv.textContent = i.title;
          left.appendChild(titleDiv);

          if (i.description) {
            const d = document.createElement("div");
            d.className = "helper";
            d.style.marginTop = "4px";
            d.textContent = i.description;
            left.appendChild(d);
          }

          if (i.link) {
            const d = document.createElement("div");
            d.style.marginTop = "4px";
            const a = document.createElement("a");
            a.href = i.link;
            a.target = "_blank";
            a.rel = "noreferrer";
            a.textContent = "เปิดลิงก์งาน";
            a.className = "helper";
            a.style.color = "#2563eb";
            d.appendChild(a);
            left.appendChild(d);
          }

          const d2 = document.createElement("div");
          d2.className = "helper";
          d2.style.marginTop = "6px";
          d2.textContent =
            "มอบ " +
            displayDate(i.assignedDate) +
            " • กำหนดส่ง " +
            displayDate(i.dueDate);
          left.appendChild(d2);

          row.appendChild(left);

          const rightLabel = document.createElement("label");
          rightLabel.style.display = "flex";
          rightLabel.style.alignItems = "center";
          rightLabel.style.gap = "6px";

          const checkbox = document.createElement("input");
          checkbox.type = "checkbox";
          checkbox.checked = !!studentData[i.id];
          checkbox.addEventListener("change", (e) => {
            if (!studentName) return;
            if (!progress[studentName]) progress[studentName] = {};
            progress[studentName][i.id] = checkbox.checked;
            saveProgress();
            renderStudent();
          });

          const span = document.createElement("span");
          span.style.fontSize = "13px";
          span.textContent = "ทำแล้ว";

          rightLabel.appendChild(checkbox);
          rightLabel.appendChild(span);

          row.appendChild(rightLabel);
          card.appendChild(row);
          listContainer.appendChild(card);
        });
      }

      // -------- Admin render --------
      function renderAdmin() {
        const subjectBody = document.getElementById("subject-summary-body");
        const classBody = document.getElementById("class-summary-body");
        subjectBody.innerHTML = "";
        classBody.innerHTML = "";

        // Subject summary
        const subjectMap = {};
        items.forEach((i) => {
          subjectMap[i.subject] = (subjectMap[i.subject] || 0) + 1;
        });

        const subjectEntries = Object.entries(subjectMap);
        if (subjectEntries.length === 0) {
          const tr = document.createElement("tr");
          const td = document.createElement("td");
          td.colSpan = 2;
          td.className = "text-center";
          td.textContent = "ยังไม่มีข้อมูลการบ้าน";
          tr.appendChild(td);
          subjectBody.appendChild(tr);
        } else {
          subjectEntries.forEach(([subject, count]) => {
            const tr = document.createElement("tr");
            const td1 = document.createElement("td");
            td1.textContent = subject;
            const td2 = document.createElement("td");
            td2.textContent = count;
            tr.appendChild(td1);
            tr.appendChild(td2);
            subjectBody.appendChild(tr);
          });
        }

        // Class summary
        const stats = {};
        items.forEach((i) => {
          if (!stats[i.classLevel]) stats[i.classLevel] = { total: 0, doneCount: 0 };
          stats[i.classLevel].total += 1;
        });

        Object.keys(progress).forEach((stu) => {
          const rec = progress[stu];
          Object.entries(rec).forEach(([hwId, done]) => {
            if (!done) return;
            const hw = items.find((h) => h.id === hwId);
            if (!hw) return;
            if (!stats[hw.classLevel]) stats[hw.classLevel] = { total: 0, doneCount: 0 };
            stats[hw.classLevel].doneCount += 1;
          });
        });

        const classEntries = Object.entries(stats);
        if (classEntries.length === 0) {
          const tr = document.createElement("tr");
          const td = document.createElement("td");
          td.colSpan = 4;
          td.className = "text-center";
          td.textContent = "ยังไม่มีข้อมูลเพียงพอ";
          tr.appendChild(td);
          classBody.appendChild(tr);
        } else {
          classEntries.forEach(([classLevel, s]) => {
            const total = s.total;
            const doneCount = s.doneCount;
            const percent = total ? Math.round((doneCount / total) * 100) : 0;

            const tr = document.createElement("tr");
            const td1 = document.createElement("td");
            td1.textContent = classLevel;
            const td2 = document.createElement("td");
            td2.textContent = total;
            const td3 = document.createElement("td");
            td3.textContent = doneCount;
            const td4 = document.createElement("td");
            td4.textContent = percent + "%";

            tr.appendChild(td1);
            tr.appendChild(td2);
            tr.appendChild(td3);
            tr.appendChild(td4);
            classBody.appendChild(tr);
          });
        }
      }

      // -------- Export / Import --------
      function onExport() {
        const data = { items, progress };
        const blob = new Blob([JSON.stringify(data, null, 2)], {
          type: "application/json"
        });
        const url = URL.createObjectURL(blob);
        const a = document.createElement("a");
        a.href = url;
        a.download = "skhw-homework-" + isoToday() + ".json";
        a.click();
        URL.revokeObjectURL(url);
      }

      function onImport(e) {
        const file = e.target.files && e.target.files[0];
        if (!file) return;
        const reader = new FileReader();
        reader.onload = () => {
          try {
            const parsed = JSON.parse(String(reader.result));
            if (Array.isArray(parsed.items)) items = parsed.items;
            if (parsed.progress && typeof parsed.progress === "object")
              progress = parsed.progress;
            saveHomeworks();
            saveProgress();
            renderAll();
          } catch {
            alert("ไฟล์ไม่ถูกต้อง (ต้องเป็น JSON ที่ได้จากปุ่ม Export)");
          }
        };
        reader.readAsText(file);
        e.target.value = "";
      }
    </script>
  </body>
</html>
# Suankularb-Homework-SKHW
