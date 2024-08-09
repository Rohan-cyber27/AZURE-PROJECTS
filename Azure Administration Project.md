
# Azure Administration Project Summary![Screenshot 2024-08-09 224019](https://github.com/user-attachments/assets/abaceec9-049b-4dc0-8dbe-4aaabb7d600c)


This project involves a series of advanced Azure administration tasks that are critical for monitoring, logging, security, and automation in an enterprise environment. Below is a simplified explanation of each task and its purpose.

## 1. Installing and Configuring IIS on a Windows Server

- **Install IIS and Management Tools:**
  - Command: `Install-WindowsFeature Web-Server -IncludeAllSubFeature -IncludeManagementTools`
  - Purpose: Set up IIS (Internet Information Services) to host web applications on a Windows Server.

- **Download Sample HTML File:**
  - Command: `Wget https://raw.githubusercontent.com/Azure-Samples/html-docs-hello-world/master/index.html -OutFile index.html`
  - Purpose: Download a simple HTML file to verify that the IIS web server is working correctly.

## 2. Creating and Configuring a Log Analytics Workspace

- **Log Analytics Workspace:**
  - Purpose: Centralized platform to collect and analyze log data from Azure resources, on-premises servers, and other environments.

- **Data Retention and Archiving:**
  - Set retention to 60 days and daily data cap to 10 GB.
  - Purpose: Manage costs and ensure that logs are stored for the required period.

- **Access Control:**
  - Set permissions for users/groups.
  - Purpose: Secure access to the Log Analytics workspace, allowing only authorized personnel.

## 3. Enabling Application Insights

- **Application Insights:**
  - Purpose: Monitor the performance and health of your web applications in real-time.

- **Disabling .NET Core Snapshot Debugger Logging:**
  - Purpose: Reduce unnecessary logging in production to optimize performance.

## 4. Configuring Diagnostic Settings

- **Web App HTTP Logs:**
  - Purpose: Log all web traffic for monitoring and troubleshooting.

- **SQL Insights Data:**
  - Purpose: Collect and analyze database performance data.

- **File and Configuration Change Tracking:**
  - Purpose: Monitor changes to your web apps' files and configurations for security and operational integrity.

## 5. Creating Data Collection Endpoints and Rules

- **Data Collection Endpoint:**
  - Purpose: Custom endpoint to collect logs from various sources, such as on-premises servers or Azure VMs.

- **Data Collection Rule:**
  - Purpose: Define which logs (e.g., Windows Event Logs, IIS Logs) to collect and where to send them.

## 6. Monitoring Network Connections

- **Network Connection Monitor:**
  - Purpose: Monitor and test network connectivity between Azure virtual machines (VMs) to ensure reliable communication.

- **Creating Test Configurations:**
  - Purpose: Continuously monitor the connection between VMs to detect and troubleshoot issues.

## 7. Creating Alerts and Action Groups

- **Action Group for Notifications:**
  - Purpose: Set up notifications (e.g., email, SMS) that trigger when specific conditions (like high CPU usage) are met.

- **Alert for CPU Utilization:**
  - Purpose: Automatically monitor VM performance and notify the relevant team if CPU usage exceeds a threshold.

# Purpose of the Project

This project equips you with the tools and configurations needed to effectively manage, monitor, and optimize an Azure environment. The tasks ensure comprehensive logging, performance monitoring, and automated alerts, all of which are crucial for maintaining high availability, security, and efficiency in cloud services.
