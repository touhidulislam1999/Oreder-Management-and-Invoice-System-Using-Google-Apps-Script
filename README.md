# 🧾 Order Management and Invoice System Using Google Apps Script

This project automates **order management** and **invoice generation** using Google Apps Script. It seamlessly integrates **Google Forms**, **Google Sheets**, and **Google Drive** to create a streamlined system for handling customer orders, generating invoices, and sending them via email.

---

## 📜 **Introduction**
The **Order Management and Invoice System** is designed to eliminate manual processes by automating:
1. **Order Handling**: Customer orders are submitted via a Google Form.
2. **Payment Confirmation**: The system identifies completed payments.
3. **Invoice Generation**: PDF invoices are generated dynamically.
4. **Email Dispatch**: Invoices are sent automatically to customers.

This system provides a reliable and efficient solution for managing orders and invoices, suitable for small businesses, educational institutions, event organizers, and more.

---

## ⚙️ **Features**

1. **Automated Order Summary Emails**: Sends an order confirmation email immediately after form submission.
2. **Integration with Google Sheets**: Stores order details and tracks invoice statuses (Sent/Unsent).
3. **PDF Invoice Generation**: Automatically generates invoices using a pre-defined template.
4. **Automated Email Dispatch**: Sends invoices via email after payment confirmation.
5. **Custom Google Sheets Menu**: Allows manual triggering of invoice sending through a custom "Send Mail" menu.

---

## 📂 **File Descriptions**

### **1. Submission.gs**
- **Purpose**: Handles form submissions by sending confirmation emails to customers.
- **Key Function**: `submit_mail(e)`  
   - Sends a confirmation email with the order details to the customer upon Google Form submission.
   - Requires a trigger: Set as **"On Form Submit"** in the Google Sheet’s triggers menu.

![Submission Email Example](https://github.com/user-attachments/assets/9a26143a-019f-4657-bff0-e412a9690a0b)

---

### **2. Mail.gs**
- **Purpose**: Manages the email-sending functionality for confirmation and invoices.
- **Key Function**: `mail(email, subject, message, attachment, name)`  
   - Sends an email to the specified address with an optional PDF attachment.

![Email Sending Example](https://github.com/user-attachments/assets/e882e7e8-feaa-48ef-951f-58c761a03c23)

---

### **3. Customer Code.gs**
- **Purpose**: Generates unique order codes for each entry.
- **Key Function**: `code_generator()`  
   - Ensures every order has a unique identifier for tracking and invoice generation.

---

### **4. Unsent.gs**
- **Purpose**: Identifies orders marked as "Unsent" in the Google Sheet.
- **Key Function**: `find_without_tick()`  
   - Scans the sheet for unsent orders and returns the relevant rows.

---

### **5. Document.gs**
- **Purpose**: Generates PDF invoices from a pre-defined template.
- **Key Function**: `make_PDF(Code, Date, Name, Email, Method, Details, Amount)`  
   - Creates a customized PDF invoice by replacing placeholders with order details.

---

### **6. Main.gs**
- **Purpose**: Automates the process of sending invoices.
- **Key Function**: `Send_Mail()`  
   - Sends PDF invoices via email for orders marked as "Unsent" and updates the status to "Sent."

![Google Sheet Integration Example](https://github.com/user-attachments/assets/1039b88a-3cc2-4f6b-83c0-313501cd6c35)

---

### **7. Button.gs**
- **Purpose**: Adds a custom menu in the Google Sheet to manually trigger invoice sending.
- **Key Function**: `onOpen(e)`  
   - Creates a "Send Mail" menu option that allows users to send all unsent invoices with a single click.

![Custom Menu Example](https://github.com/user-attachments/assets/a2b507ca-4099-4df0-bb10-7d275c524d73)

---

## 🛠️ **How to Use**

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/touhidulislam1999/Oreder-Management-and-Invoice-System-Using-Google-Apps-Script.git
