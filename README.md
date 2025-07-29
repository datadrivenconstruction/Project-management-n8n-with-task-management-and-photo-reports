# Project Management: Universal Task and Report Management System

![n8n](https://img.shields.io/badge/Platform-n8n-orange?style=flat-square) ![Telegram](https://img.shields.io/badge/Integration-Telegram-blue?style=flat-square&logo=telegram) ![Google Sheets](https://img.shields.io/badge/Integration-Google%20Sheets-green?style=flat-square&logo=google)

Welcome to the **Project Management** system repository! This is a universal automated free workflow based on n8n, designed for managing tasks and reports in any "manager-executor" relationships. The system uses a Telegram bot as a convenient interface for interaction, Google Sheets (or can be connected to any other spreadsheets) for data storage and automatic reminders about tasks and reports.

### 📋 Demo bot for task management
- 🤖 **Test Bot:** [@ProjectDiaryBot](https://t.me/ProjectDiaryBot)  
- 📊 **Report Spreadsheet:** [Google Sheets](https://docs.google.com/spreadsheets/d/14V795nago6Qt7PpECflnuFSTdTvwo-fWEG_n83wgKug)  
- 🎥 **Demo Video:** [Watch video](https://t.me/n8n_pipelines/1660)
  


🚀 **Key advantages**:
- **Universality**: Suitable for any scenarios — from construction projects to household chores, including task control for children, employees or contractors.
- **Automation**: Sending reminders, collecting text and photo reports, GPS markers and automatic data saving.
- **Simplicity**: Executors interact through Telegram, and managers manage through a spreadsheet (e.g., Google Sheets).
- **Flexibility**: The minimal set of parameters in the table can be supplemented with data from real conditions (e.g., weather, comments, photos, GPS).

The system allows managers to set tasks with minimal description, and executors supplement them with real data (status, comments, photos, geolocation), forming a complete picture of execution. 
The system is integrated with Telegram and Google Sheets, providing a convenient management interface.
![Application](https://datadrivenconstruction.io/wp-content/uploads/2025/07/Приложение-Менеджмент-проекта.jpg)

---

## 📋 System Features

- **Executor Registration** 👤: Automatic via `/start` with name and role request (e.g., "employee", "child", "contractor").
- **Task Reminders** ⏰: Distribution of tasks with priorities (🔴 High, 🟡 Medium, 🟢 Low) from the spreadsheet (Google Sheets).
- **Reports** 📝:
  - **Text**: Status (completed/partially/not completed) + comment.
  - **Photo**: Support for multiple files with comments, upload to Google Drive.
  - **Geolocation**: GPS for linking to tasks (e.g., execution location or whereabouts).
- **Bot Commands** 🤖:
  - `/start` — Registration.
  - `/help` — Help on usage.
  - `/status` — Report status for the day.
  - `/prochital` — Confirmation of reading reminders.
  - `/poluchil` — Confirmation of receiving tasks.
- **Automation** 🔄: Checks run every minute, real-time status updates.
- **Flexible Storage**: Spreadsheet (Google Sheets in this example) as a database for tasks with minimal parameters, which are supplemented by executors.

---

## 🌟 Universal Application

The system is suitable for any "manager-executor" relationships where you need to set tasks, track execution and collect reports. Here are several examples:

1. **Construction and Contractors** 🏗️:
   - Manager: Assigns tasks (e.g., "Lay 10 m² of tiles") and requests photo reports (work log, welding).
   - Executor: Sends status ("completed"), photos and construction site GPS.
   - Additions: Weather, comments about problems (e.g., "no materials").

2. **Household Chores and Children** 👨‍👩‍👧:
   - Manager (parent): Sets tasks ("Do homework", "Clean room") with reminder time.
   - Executor (child): Confirms completion with text ("done") or photo (cleaned room).
   - Additions: Comments ("Did math, but need help with physics").

3. **Office and Employees** 💼:
   - Manager: Assigns tasks ("Prepare presentation by 3:00 PM") with priorities.
   - Executor: Responds with status ("ready") and attaches file/screenshot.
   - Additions: Comments about progress or problems.

4. **Logistics and Delivery** 🚚:
   - Manager: Sets route or task ("Deliver cargo to point A").
   - Executor: Sends delivery point GPS, cargo photo.
   - Additions: Delivery time, cargo condition.

5. **Freelance and Projects** 💻:
   - Manager: Assigns tasks ("Develop design") with deadlines.
   - Executor: Sends intermediate results (screenshots, files).
   - Additions: Remarks or clarifications on the task.

The system allows starting with minimal task description (ID, name, executor, time) and supplementing it with real executor data (status, photos, comments, GPS), making it universal for any scenarios.

---

## 📸 System Workflow Stages

### 1. New Executor Registration
The manager adds an executor by sending the bot name. The executor goes to the bot and presses `/start` in Telegram. The bot requests name and role (e.g., "Child" or "Contractor"), then automatically records the data in the spreadsheet. This is the first step to begin interaction.
![Executor Registration](https://datadrivenconstruction.io/wp-content/uploads/2025/07/I.-Регистрация-нового-исполнителя.jpg)

### 2. Task Creation and Reminders by Manager
The manager opens the task spreadsheet and fills in the table with minimal parameters: Task_ID, Executor, Date, Send Time, Task and Priority. After saving, the system checks the table every minute and sends reminders to the executor via Telegram at the specified time.
![Task Creation](https://datadrivenconstruction.io/wp-content/uploads/2025/07/II.-Создание-задач-и-напоминаний-менеджером.jpg)

### 3. Executor Responds to Messages
The executor receives a reminder in Telegram and responds to it. For example, sends text status ("completed" with comment), attaches photo (e.g., completed work) or shares geolocation. All data is automatically updated in the spreadsheet.
![Executor Response](https://datadrivenconstruction.io/wp-content/uploads/2025/07/III.-Исполнитель-отвечает-на-сообщения-1.jpg)

### 4. Application and General Overview
After process completion, all data (statuses, photos, comments, GPS) is collected in a unified system. The manager can view them in the spreadsheet or use Telegram for quick access to information. This is a convenient management interface.
![Table Parameters](https://datadrivenconstruction.io/wp-content/uploads/2025/07/Параметры-заполняемые-менеджером-в-таблице.jpg)

---

## 🛠 Requirements

To run, you will need:
- **n8n** (version 1.0+): Self-hosted or cloud.
- **Telegram Bot**: Token from [@BotFather](https://t.me/BotFather).
- **Google Account**:
  - Sheets for storing tasks and reports (template in repository).
  - Drive for uploading photos/files.
  - OAuth2 for API (Sheets + Drive).

---

## 🚀 Installation and Setup

### 1. Clone the repository or simply download it to your computer
```bash
git clone https://github.com/your-username/project-manager-pipeline.git
cd project-manager-pipeline
```

### 2. Create a Telegram bot
- In the official Telegram bot [@BotFather](https://t.me/BotFather) create a bot and get a token.
- In n8n: Credentials → Add → Telegram API → Paste token.

### 3. Set up Google Sheets and Drive
- Copy the spreadsheet template in this repository (`Менеджмент проекта _ Управление задачами, напоминаниями и фотоотчётами.xlsx`) to Google Sheets.
- Sheets:
  - **Tasks**: For tasks (ID, executor, date, time, priority).
  - **Photo Report Log**: For reports (ID, type, date, time).
  - **Executors**: For user registration.
  - **Auxiliary Lists**: For report types and intervals.
- In n8n: Credentials → Add → Google Sheets OAuth2 API.
  - In Google Cloud Console: Enable Sheets and Drive API.
  - Scopes: `https://www.googleapis.com/auth/spreadsheets`, `https://www.googleapis.com/auth/drive`.
- Share the spreadsheet and Drive with the Google service account.

### 4. Import Workflow to n8n
- In n8n: Workflows → Import from File → Upload `Project Photo Report Pipeline 26072025 (1).json`.
- Connect credentials:
  - Telegram: To Telegram Trigger and Telegram nodes.
  - Google: To Google Sheets and Drive nodes, specify spreadsheet ID.
- Activate webhook:
  - n8n will generate URL for Telegram Trigger.
  - Set webhook:  
    ```bash
    curl https://api.telegram.org/bot[TOKEN]/setWebhook?url=[n8n-URL]
    ```

### 5. Configure the spreadsheet
- **Tasks**: Add rows with fields: Task_ID, Executor, Date (DD.MM.YYYY), Send Time (fraction of day, e.g., 0.5 = 12:00), Task, Object, Section, Priority, Executor ID (Telegram ID).
- **Photo Reports**: Specify Report_ID, Report Type (from auxiliary sheet), Date and Time.
- **Intervals**: In "Auxiliary Lists" configure report types (e.g., "Cleaning Photo", "Homework Report") and reminder intervals (e.g., 01:00).

### 6. Test
- Send `/start` in chat with bot — register.
- Add test task to spreadsheet — wait a minute, bot will send reminder.
- Reply with text, photo or GPS — check update in spreadsheet.

---

## 📖 How to Use

### For Managers 🧑‍💼
1. **Create tasks/reports**:
   - In Google Sheets add a task or report with minimal parameters (ID, executor, time, description).
   - Bot will automatically send reminders at the specified time.
2. **Monitor**:
   - Check spreadsheet: statuses, photos (Drive links), comments, GPS.
   - Use filters in Sheets by date, executor or status.
3. **Customize**:
   - Add your task/report types in "Auxiliary Lists".
   - Configure reminder intervals.

### For Executors 👷
1. **Registration**: Write `/start`, specify name and role (e.g., "Child", "Employee").
2. **Receiving reminders**:
   - Bot sends tasks/reports at specified time.
3. **Sending reports**:
   - **Tasks**: Reply to message in format:  
     ```
     completed
     Everything is fine
     ```
     (or "partially" / "not completed" + comment, e.g., "Waiting for materials").
   - **Photo**: Attach photo in response to reminder, add comment (e.g., "Cleaned up").
   - **GPS**: Send geolocation in response to report if required.
4. **Confirmations**:
   - `/prochital` — for photo reports.
   - `/poluchil` — for tasks.
5. **Status**: `/status` — list of reports for the day.
6. **Manual report**: `/report` → select type (1-5).

All data is saved automatically — just reply in Telegram!

---

## 🔧 Workflow Structure
- **Input**: Telegram Webhook for message processing.
- **Registration**: Check and record executors in Google Sheets.
- **Processing**: Nodes for parsing text, photos, GPS.
- **Automation**: Cron (every minute) for sending reminders.
- **Output**: Update Sheets/Drive, send confirmations.

Edit in n8n for customization (e.g., add manager notifications).

---

## ⚠️ Possible Issues
- **Bot not responding**: Check webhook and workflow status in n8n.
- **Google errors**: Ensure correct scopes and access to Sheets/Drive.
- **Time**: Set timezone in n8n to "Europe/Minsk" (or your region).
- **Logs**: Check errors in Executions section in n8n.

---

## 📑 Community and Discussion
📑 Start of discussion of the n8n task manager workflow in the "n8n Development" group:  
[Discussion](https://t.me/n8n_pipelines/831)

Want to discuss new automation pipelines, share your cases or get help? You can find more automation examples in the GitHub repository or in our Telegram chat "n8n Development | Automation practice and ready-made solutions". Join our Telegram community for live discussions, tips and exclusive content.  
![Executor Response](https://datadrivenconstruction.io/wp-content/uploads/2025/07/Чат-8n_development_channel.jpg)

---

## 📄 License
[MIT License](LICENSE) — use and modify freely!

## 👏 Contributors
- [Artem Boiko](https://github.com/boikoartem) — Developer.

📢 **Have questions?** Create an Issue or write in Discussions. Good luck with task management! 🚀