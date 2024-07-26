# Implementing Windows Server Active Directory Federation Services (AD FS)

## Project Overview

**Objective:** Set up and configure Active Directory Federation Services (AD FS) to enable single sign-on (SSO) for applications across multiple domains or forests. This project includes installing and configuring AD FS, setting up a relying party trust, and configuring claims-based authentication.

### Prerequisites

- Existing Active Directory domain.
- Domain-joined Windows Server for AD FS role installation.
- Domain Administrator credentials.
- SSL certificate for AD FS.

## Step-by-Step Instructions

### 1. Install Active Directory Federation Services (AD FS)

#### Log in to the Windows Server

- Use a domain administrator account to log in to the server.

#### Open Server Manager

- Click on the Start menu, type `Server Manager`, and press Enter.

#### Add Roles and Features

- In Server Manager, click `Manage > Add Roles and Features`.
- Click `Next` until you reach the **Select server roles** page.

#### Select AD FS

- Check the **Active Directory Federation Services** box.
- Click `Next` until you reach the **Confirmation** page.
- Click `Install`.

### 2. Configure Active Directory Federation Services (AD FS)

#### Post-Installation Configuration

- After installation, click `Configure the federation service on this server` in the AD FS results window.

#### Create the First Federation Server in a Federation Server Farm

- On the **Welcome** page, select `Create the first federation server in a federation server farm` and click `Next`.

#### Connect to AD DS

- On the **Connect to AD DS** page, specify a domain administrator account to perform the configuration and click `Next`.

#### Specify Service Properties

- On the **Specify Service Properties** page, import your SSL certificate, provide the federation service name (e.g., `fs.yourdomain.com`), and click `Next`.

#### Specify Service Account

- On the **Specify Service Account** page, select `Create a Group Managed Service Account` and click `Next`.

#### Specify Configuration Database

- On the **Specify Configuration Database** page, select `Create a database on this server using Windows Internal Database` and click `Next`.

#### Review Options and Configure

- Review your configuration options and click `Next`.
- Click `Configure`.
- Once the configuration is complete, click `Close`.

### 3. Configure Relying Party Trust

#### Open AD FS Management

- In Server Manager, click `Tools > AD FS Management`.

#### Add Relying Party Trust

- In the AD FS Management console, expand **Trust Relationships** and right-click **Relying Party Trusts**.
- Select `Add Relying Party Trust`.

#### Configure Relying Party Trust

- On the **Welcome** page, click `Start`.
- On the **Select Data Source** page, select `Enter data about the relying party manually` and click `Next`.
- On the **Specify Display Name** page, enter a display name (e.g., `MyApp`) and click `Next`.
- On the **Choose Profile** page, select `AD FS profile` and click `Next`.
- On the **Configure Certificate** page, click `Next` (no certificate needed for now).
- On the **Configure URL** page, if your application uses SAML, check `Enable support for the SAML 2.0 WebSSO protocol` and enter the **Relying party SAML 2.0 SSO service URL**.
- On the **Configure Identifiers** page, add the relying party trust identifier (e.g., `https://myapp.yourdomain.com`) and click `Next`.
- On the **Configure Multi-factor Authentication Now** page, click `Next`.
- On the **Choose Issuance Authorization Rules** page, select `Permit all users to access this relying party` and click `Next`.
- On the **Ready to Add Trust** page, review the settings and click `Next`.
- On the **Finish** page, click `Close`.

### 4. Configure Claims Issuance Policy

#### Edit Claim Issuance Policy

- In the AD FS Management console, select the relying party trust you just created and click `Edit Claim Issuance Policy`.

#### Add Rule

- Click `Add Rule`.
- Select `Send LDAP Attributes as Claims` and click `Next`.

#### Configure Rule

- **Claim rule name:** Enter a name for the rule (e.g., `Send UPN as NameID`).
- **Attribute store:** Select `Active Directory`.
- **Mapping of LDAP attributes to outgoing claim types:** Map `User-Principal-Name` to `Name ID`.
- Click `Finish`.

### 5. Test the AD FS Configuration

#### Access AD FS Metadata

- Navigate to `https://fs.yourdomain.com/FederationMetadata/2007-06/FederationMetadata.xml` to ensure that the AD FS metadata is accessible.

#### Test SSO

- Configure an application to use AD FS for authentication.
- Attempt to log in to the application using AD FS credentials.

## Conclusion

successfully set up and configured Active Directory Federation Services (AD FS) to enable single sign-on (SSO) for applications across multiple domains or forests. This advanced project enhances security and simplifies user access to applications by leveraging AD FS for authentication.
