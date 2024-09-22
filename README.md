# Oreder-Management-and-Invoice-System-Using-Google-Apps-Script
This project is a Google Apps Script solution for automating order management, payment confirmation, and invoice generation. It integrates Google Forms, Sheets, and Drive to provide a streamlined, fully automated process for handling customer orders and generating invoices.

# Introduction
This project is a Google Apps Script-based automated response and invoice generation system. The workflow begins when a customer submits a Google Form. Upon submission, the system generates and sends a confirmation email with the order details to the customer. The form responses are stored in a Google Sheet. After payment confirmation, the system generates a PDF invoice, which is sent to the customer via email. This project streamlines order handling and invoice generation, eliminating manual processes and ensuring efficient communication with customers.

# Features:
1. Automated order summary email to customers upon submission.
2. Integration with Google Sheets for storing order data.
3. PDF invoice generation and email dispatch after payment confirmation.
4. Simple Google Apps Script integration with Google services (Forms, Sheets, Drive).

# File Descriptions

**Submission.gs**

***Purpose:*** Handles form submission. Once a customer submits the Google Form, this script is triggered. It generates an order confirmation email containing the user's details (name, student ID, payment method) and sends it to the provided email address.

***Key Function:*** submit_mail(e) - Sends the confirmation email using the customer’s data from the form submission. As this function is listing an envet and it need to be triggred on Form Submit. To do thatyou have to go to Triggers Options on the left, then click on "Add Triggers", then choose the function name, source should be from spreadsheet and event type should be "On form submit".


![image](https://github.com/user-attachments/assets/9a26143a-019f-4657-bff0-e412a9690a0b)

![image](https://github.com/user-attachments/assets/e882e7e8-feaa-48ef-951f-58c761a03c23)

**Mail.gs**

***Purpose:*** Manages the email sending functionality. This script is used to send emails with or without attachments.

***Key Function:*** mail(email,subject,message,attachment,name) - Sends an email to the specified address with or without PDF attachments, depending on the parameters.

**Customer Code.gs**

***Purpose:*** Generates unique order codes for each customer entry. It ensures that each order in the Google Sheet has a unique identifier, which is necessary for invoice tracking and generation.

***Key Function:*** code_generator() - Generates unique order codes for new entries in the Google Sheet.

**Unsent.gs**

***Purpose:*** Finds orders that have not been sent yet. This script scans the Google Sheet to identify rows where invoices are marked as "Unsent" and returns the relevant rows.

***Key Function:*** find_without_tick() - Returns a list of rows with unsent orders.

**Document.gs**

***Purpose:*** Creates the PDF invoice using a template. This script pulls customer data from the Google Sheet and populates a pre-defined template with order details to generate a PDF invoice.

***Key Function:*** make_PDF(Code,Date,Name,Email,Method,Details,Amount) - Creates the PDF invoice by replacing placeholders in the template with actual customer data.

**Main.gs**

***Purpose:*** Sends PDF invoices via email to customers whose orders are marked as "Unsent." After sending, it updates the status to "Sent" in the Google Sheet.

***Key Function:*** Send_Mail() - Handles the process of sending the invoice email and updating the order status.

![image](https://github.com/user-attachments/assets/1039b88a-3cc2-4f6b-83c0-313501cd6c35)

![image](https://github.com/user-attachments/assets/8aea6a0f-ed90-47e9-95d0-828c20429921)



**Button.gs**

***Purpose:*** Adds a custom menu in the Google Sheet to trigger the sending of invoices. The "Send" button in the UI allows users to manually trigger the sending of all unsent invoices.

***Key Function:*** onOpen(e) - Adds the "Send Mail" menu option when the Google Sheet is opened.

![image](https://github.com/user-attachments/assets/a2b507ca-4099-4df0-bb10-7d275c524d73)


# Use Cases
This project can be used in various scenarios, such as:

**1. Small Business Invoice System:**
This project can be used by small businesses or freelancers to automate order management and invoice generation. Customers can place orders via a form, and after payment confirmation, invoices are sent automatically without manual intervention.

**2. Event Management:**
Event organizers can use this system to handle registration and payment confirmations for participants. The order summary can act as a confirmation, and invoices can be generated for any payments made.

**3. Educational Institution Fees:**
Schools or universities can use this system to manage fee collection. Students submit their details via a form, and upon payment confirmation, they receive an official invoice.

**4. E-commerce Stores:**
Small online stores can automate their order management and invoicing process by adapting this system, ensuring customers receive timely order summaries and invoices.

