# Azure Logic Apps Project: Email Notification on New Gmail Messages

This project uses Azure Logic Apps to send a notification whenever a new email arrives in your Gmail account. This guide will walk you through the steps of creating the Logic App and setting up the necessary triggers and actions.

## Azure Services Used

- **Azure Logic Apps**

## Project Overview

### Objective

The objective of this project is to create an automated workflow that triggers a notification whenever a new email is received in a specified Gmail account.

### Prerequisites

1. An active Azure subscription.
2. Access to the Azure Portal.
3. A Gmail account.

## Step-by-Step Instructions

### 1. Create a Logic App

1. **Log in to the Azure Portal:**
   - Navigate to [Azure Portal](https://portal.azure.com).

2. **Create a New Logic App:**
   - In the left-hand menu, select **Create a resource**.
   - Search for **Logic App** and select it.
   - Click **Create**.
   - Fill in the required details:
     - **Name:** Enter a name for your Logic App (e.g., `GmailNotificationApp`).
     - **Subscription:** Select your subscription.
     - **Resource Group:** Select or create a new resource group.
     - **Region:** Choose the region closest to you.
   - Click **Review + Create** and then **Create**.

### 2. Design Workflow: When a New Email Arrives

1. **Open Logic App Designer:**
   - Once the Logic App is created, navigate to **Logic Apps** in the left-hand menu.
   - Select your newly created Logic App and click on **Logic App Designer**.

2. **Add Trigger:**
   - In the Logic App Designer, search for **Gmail** and select the **When a new email arrives** trigger.
   - Sign in to your Gmail account to grant necessary permissions to the Logic App.

### 3. Configure Trigger

1. **Set Up Trigger:**
   - After signing in, configure the trigger settings:
     - **Label:** Select the label you want to monitor (e.g., `Inbox`).
     - **Include Attachments:** Choose whether to include attachments.
     - **Importance:** Select the importance level of the emails to trigger notifications (e.g., `Any`).
   - Click **Save**.

### 4. Add an Action: Send Notification

1. **Add New Step:**
   - Click **+ New step**.
   - Search for **Notification** and select **Send me a mobile notification** (or choose a different notification action if preferred).

2. **Configure Notification Action:**
   - **Text:** Enter the text for your notification (e.g., `You have a new email in your Gmail inbox: ${subject}`).
   - Use dynamic content to include the subject of the email by selecting `Subject` from the dynamic content list.

### 5. Save and Test the Logic App

1. **Save Logic App:**
   - Click **Save** to save your Logic App.

2. **Test Logic App:**
   - Send a test email to your Gmail account.
   - Verify that you receive a notification with the specified message content.

### 6. Monitor and Manage the Logic App

1. **Monitor Runs:**
   - In the Logic App Designer, click on **Overview**.
   - Review the **Run history** to monitor the execution of your Logic App and troubleshoot any issues.

2. **Manage Triggers and Actions:**
   - Modify the trigger settings or add more actions as needed to enhance the functionality of your Logic App.

## Conclusion

successfully created a Logic App that triggers a notification whenever a new email arrives in your Gmail account. This setup helps in automating the process of monitoring your inbox and ensures you are promptly notified of any new emails.

By following these detailed steps, you can replicate this project in your Azure environment and customize it further to meet your specific requirements.
