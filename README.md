# 🌴 Vacation Tracking System

*An application to make managing and requesting vacation time much easier and more controlled.*

---

## ✨ The Vision

Allow employees to manage their vacation, sick leave, and personal time off without needing expertise in company policies. It also helps streamline Human Resources (HR) functions, minimizing non-core business-related activities for management, and empowering employees.

---

## 📌 The Domain

The project was created to fix the problem of managing employee vacation time being too slow and complicated. This happened because more people now work on different teams and for different managers, making it hard to keep track of their time off.

---

## 📋 Requirements

### 🔹 1. Functional:

1. **📅 Manage Time**  
   - A key goal is for the employee to submit a new request for vacation time. The system should look up the current status and balances, display the information, allow the employee to review and change request information, and handle withdrawals and submissions, including prompting for confirmation and highlighting errors.

2. **✅ Manage Requests**  
   - This use case describes how a Manager approves or rejects employee leave requests.

3. **⚙️ Override Leave Records**  
   - This describes how a Manager may override system rejections of leave time requests. An HR clerk also has the ability to override any rejection of leave time requests made by the system's rules, with logging of those overrides.

4. **🎁 Award Personal Leave**  
   - This allows managers to directly award personal leave time (with system-set limits).

5. **🌐 Web Service Interface**  
   - Provides an interface for other internal systems to query any given employee's vacation request summary.

6. **🔗 Interface with HR Department Legacy Systems**  
   - The system must interface with HR department legacy systems to retrieve required employee information and changes.

7. **🏢 Manage Locations**  
   - Describes how an HR clerk manages location records and their rules.

8. **📂 Manage Leave Categories**  
   - Describes how an HR clerk manages leave categories and their rules.

9. **💾 Back Up System Logs**  
   - Describes how the system administrator backs up the system's logs.

### 🔹 2. Non-Functional:

1. **⚡ Performance**  
   - Loading forms or displaying history should be fast, as well as handling peak user load without slowdowns.

2. **🔒 Security**  
   - Ensure proper access controls (employees only control their data, managers their direct reports, HR/Admin full override).

3. **📜 Auditability**  
   - Log all transactions and overrides.

4. **🖥️ Usability/User Experience (UX)**  
   - Ease of Use and timely email notifications for approvals and status changes.

5. **🛠️ Maintainability**  
   - Easily update rules and add new leave types.

---

## 👥 The Actors

- **Employee** – Uses the system to manage their vacation time.  
- **Manager** – A high-level employee with the responsibility of approving vacation requests for immediate subordinates.  
- **Clerk** – HR member with sufficient rights to add or remove nearly any record in the system.  
- **System Admin** – Responsible for the smooth running of the system's technical resources.

---

## 📜 Use Cases

### 1. Manage Time
- **Actor:** Employee  
- **Goal:** Control requests for vacation time (viewing, creating, canceling), being able to manage time provides significant value.
#### ER Diagram:
<img width="1041" alt="erd" src="https://github.com/user-attachments/assets/deb51f04-054a-462c-af47-6a7b8efaa20b" />


#### 📝 Create
The system displays a summary of the current requests, balances for different time categories, and status information for active requests within a specific timeframe. The employee selects a leave category with available balance. The system prompts for dates and times, and a visual calendar is displayed to assist in selection. The employee enters selected dates, hours per date, a short title, and a description. Finally, the employee submits the request.
#### Flowchart:
![fc](https://github.com/user-attachments/assets/c65d19d6-194c-4da9-a926-989024a017f9)

#### Sequence Diagram:
![create_sd](https://github.com/user-attachments/assets/08eea636-0c1c-402c-9c72-479d83adfdbb)

#### ❌ Withdraw
An employee can withdraw a request that is still pending approval. This is initiated from the home page where outstanding requests are listed. The system may prompt for confirmation before withdrawing.
#### Flowchart:
![withdraw_fc](https://github.com/user-attachments/assets/b52d7a49-0091-4fff-970b-bd45e2cdb2fc)

#### Sequence Diagram:
![withdraw_sd](https://github.com/user-attachments/assets/05cc80e0-b426-45d5-bf4c-a855ed09c370)

#### ✏️ Edit
An employee can select a pending request to edit. The system presents an editable view, allowing changes to the title, comments, or dates. The employee can also choose to delete or cancel the request from this editing page. Changes are submitted; if there's any error in the request, it results in the editing page being redisplayed with the problems highlighted.
#### Flowchart:
![edit_fs](https://github.com/user-attachments/assets/32aa0051-6719-452f-ac67-b486da87be0f)

#### Sequence Diagram:
![edit_sd](https://github.com/user-attachments/assets/c16cfa7f-ae55-4836-b61a-5ac7806fabd1)
