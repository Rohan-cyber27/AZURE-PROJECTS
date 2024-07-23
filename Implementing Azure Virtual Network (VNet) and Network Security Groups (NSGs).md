# Implementing Azure Virtual Network (VNet) and Network Security Groups (NSGs)

## Project Overview

**Objective:** Create an Azure Virtual Network (VNet), deploy a virtual machine (VM) within the VNet, and secure the VM using Network Security Groups (NSGs).

**Azure Services Used:** Azure Virtual Network, Azure Virtual Machines, Network Security Groups, Azure Bastion (optional for secure VM access).

## Step-by-Step Instructions

### 1. Create a Resource Group

1. **Log in to Azure Portal:**
   - Navigate to [Azure Portal](https://portal.azure.com).

2. **Create a Resource Group:**
   - Go to **Resource groups**.
   - Click **+ Add**.
   - Enter a name for your resource group (e.g., `VNet-Project-RG`).
   - Select a region.
   - Click **Review + Create** and then **Create**.

### 2. Create a Virtual Network (VNet)

1. **Navigate to Virtual Networks:**
   - In the Azure Portal, go to **Virtual networks**.
   - Click **+ Create**.

2. **Configure VNet Settings:**
   - **Subscription:** Select your subscription.
   - **Resource Group:** Select the resource group you created.
   - **Name:** Enter a name for the VNet (e.g., `MyVNet`).
   - **Region:** Select the same region as your resource group.
   - **IPv4 address space:** Enter an address space (e.g., `10.0.0.0/16`).
   - Click **Next: IP Addresses**.

3. **Add Subnet:**
   - Click **+ Add subnet**.
   - **Subnet name:** Enter a name for the subnet (e.g., `MySubnet`).
   - **Subnet address range:** Enter an address range (e.g., `10.0.1.0/24`).
   - Click **Add**.

4. **Review and Create:**
   - Click **Review + Create**.
   - Click **Create**.

### 3. Create a Network Security Group (NSG)

1. **Navigate to Network Security Groups:**
   - In the Azure Portal, go to **Network security groups**.
   - Click **+ Create**.

2. **Configure NSG Settings:**
   - **Subscription:** Select your subscription.
   - **Resource Group:** Select the resource group you created.
   - **Name:** Enter a name for the NSG (e.g., `MyNSG`).
   - **Region:** Select the same region as your VNet.
   - Click **Review + Create** and then **Create**.

### 4. Create Inbound and Outbound Security Rules

1. **Navigate to Your NSG:**
   - Go to **Network security groups** and select your NSG.

2. **Create Inbound Security Rules:**
   - Click on **Inbound security rules** and then **+ Add**.
   - **Source:** Any.
   - **Source port ranges:** *.
   - **Destination:** Any.
   - **Destination port ranges:** 22 (for SSH) or 3389 (for RDP).
   - **Protocol:** TCP.
   - **Action:** Allow.
   - **Priority:** Enter a priority (e.g., 100).
   - **Name:** Enter a name for the rule (e.g., `Allow-SSH` or `Allow-RDP`).
   - Click **Add**.

3. **Create Outbound Security Rules:**
   - Click on **Outbound security rules** and then **+ Add**.
   - **Destination:** Any.
   - **Destination port ranges:** *.
   - **Protocol:** Any.
   - **Action:** Allow.
   - **Priority:** Enter a priority (e.g., 100).
   - **Name:** Enter a name for the rule (e.g., `Allow-All-Outbound`).
   - Click **Add**.

### 5. Create a Virtual Machine (VM)

1. **Navigate to Virtual Machines:**
   - In the Azure Portal, go to **Virtual machines**.
   - Click **+ Create** and select **Azure virtual machine**.

2. **Configure VM Settings:**
   - **Subscription:** Select your subscription.
   - **Resource Group:** Select the resource group you created.
   - **Virtual machine name:** Enter a name for the VM (e.g., `MyVM`).
   - **Region:** Select the same region as your VNet.
   - **Image:** Select an OS image (e.g., Ubuntu or Windows Server).
   - **Size:** Select an appropriate VM size.
   - **Authentication type:** SSH public key (for Linux) or Password (for Windows).
   - **Username:** Enter a username.
   - **Password/SSH key:** Enter the password or SSH public key.
   - Click **Next: Disks**.

3. **Configure Networking:**
   - **Virtual network:** Select the VNet you created.
   - **Subnet:** Select the subnet you created.
   - **Public IP:** Create a new public IP.
   - **NIC network security group:** Select the NSG you created.
   - Click **Review + Create** and then **Create**.

### 6. Access the Virtual Machine

1. **Access via SSH or RDP:**
   - **SSH (Linux):** Use an SSH client to connect to the VM using its public IP address.
     ```sh
     ssh <username>@<public-ip>
     ```
   - **RDP (Windows):** Use Remote Desktop Connection to connect to the VM using its public IP address.

2. **Optional: Use Azure Bastion for Secure Access:**
   - In the Azure Portal, navigate to your VM.
   - Click **Connect** and select **Bastion**.
   - Click **Use Bastion** and configure it for secure VM access without exposing a public IP.

### 7. Monitor and Manage the VNet and VM

1. **Monitor Network Traffic:**
   - Navigate to your NSG and click on **Network security group flow logs** to enable and view flow logs.

2. **Monitor VM Performance:**
   - Navigate to your VM and click on **Monitoring** to view performance metrics and logs.

3. **Manage NSG Rules:**
   - Modify or add new security rules as needed to control network traffic to and from your VM.

## Conclusion

This project walks you through the process of creating a secure and isolated network environment in Azure using Virtual Network (VNet) and Network Security Groups (NSGs).
