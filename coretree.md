# Technical Specification Document for Core Tree

![Core Tree Logo](https://coretreecare.com/wp-content/uploads/2020/04/Core-Tree-Care-Logo-Regular.png "Core Tree Care")


## Table of Contents
- [Technical Specification Document for Core Tree](#technical-specification-document-for-core-tree)
  - [Table of Contents](#table-of-contents)
  - [1. Introduction](#1-introduction)
    - [1.1 Purpose](#11-purpose)
    - [1.2 Scope](#12-scope)
  - [2. User Roles](#2-user-roles)
    - [2.1 Client Admin](#21-client-admin)
    - [2.2 CDL DOT Regulated Employee](#22-cdl-dot-regulated-employee)
    - [2.3 General Industry Employee (Non-Driver)](#23-general-industry-employee-non-driver)
  - [3. Public Pages](#3-public-pages)
    - [3.1 HUB Drive Online](#31-hub-drive-online)
  - [4. App Menu](#4-app-menu)
    - [4.1 Main Menu](#41-main-menu)
    - [4.2 Welcome Email](#42-welcome-email)
  - [5. Access Privileges](#5-access-privileges)
  - [6. Individual Page Details](#6-individual-page-details)
    - [6.1 User Management](#61-user-management)
    - [6.2 Welcome Email Update](#62-welcome-email-update)
  - [7. Conclusion](#7-conclusion)

## 1. Introduction

### 1.1 Purpose
This document provides a detailed technical specification for the development of the Core Tree Care HUB Drive Online Applicant Tracking System. The system is designed to facilitate the onboarding process for different user roles, including Client Admin, CDL DOT Regulated Employee, and General Industry Employee (Non-Driver).

### 1.2 Scope
The scope of this project includes the implementation of user roles, public pages, app menu functionality, access privileges, and individual page details as outlined in the requirements document.

## 2. User Roles

### 2.1 Client Admin
1. **Details:** Admin responsible for adding users via user management and initiating pre-hire services.

### 2.2 CDL DOT Regulated Employee
1. **Details:** Users filling out DOT Application and Driver Information form.

### 2.3 General Industry Employee (Non-Driver)
1. **Details:** Users filling out General Industry Onboard form and Driver Information form.

## 3. Public Pages

### 3.1 HUB Drive Online
1. **User Management:**
    - **Role:** Client Admin
2. **DOT Application Onboard form and Driver Information form:**
    - **Role:** CDL DOT Regulated Employee
3. **General Industry Onboard form and Driver Information form:**
    - **Role:** General Industry Employee (Non-Driver)

## 4. App Menu

### 4.1 Main Menu
1. **Level 1 Menu:**
    - HUB Drive Online homepage.
2. **Level 2 Menu:**
    - User Management – Add users.
    - View added users in User Management and Onboard list view.
3. **Navigation Type:**
    - On Submit: Addition of new users.
4. **Access:**
    - Client Admin

### 4.2 Welcome Email
1. **Login Page:**
    - DOT Application form
    - Onboarding: DOT Driver
2. **Login Page:**
    - General Industry Onboard form
    - Onboarding: General Industry Employee

    #### Implementation of Spanish Welcome Email

    The Spanish welcome email functionality has been implemented using the following template file:

    **SpanishWelcomeEmail.tpl:**
    ```tpl
    Subject: Bienvenido a HUB Drive Online - Sistema de Seguimiento de Solicitantes de Core Tree Care

    Estimado/a {user_name},
    {company_name} utiliza HUB Drive Online como su sistema de contratación y seguimiento de nuevos solicitantes.
    Usted ha sido agregado como nuevo solicitante. Por favor, inicie sesión en HUB Drive Online y complete su solicitud.
    
    Su información de inicio de sesión es:
    Nombre de usuario: {user_email}
    Enlace para establecer la contraseña: {login_link}
    
    ¿Necesita ayuda para completar su solicitud? Envíe un correo electrónico a {hr_email} o llame al {hr_phone} para obtener asistencia.
    
    Gracias,
    HUB Drive Online
    ```

    The placeholders like `{user_name}`, `{company_name}`, `{user_email}`, `{login_link}`, `{hr_email}`, and `{hr_phone}` should be dynamically replaced with actual values during runtime.

## 5. Access Privileges

1. **Action:**
    - Add users via User Management.
    - View users added via user management under onboarding list view.
    - Fill respective IC Onboard form and Driver Information form with Esign.
    - Start Pre-hire services.
2. **Client Admin**

| Access | Another header | Yet another header |
|--- |--- |--- |
| Admin | column 2 | column 3 |
| Client | row 2 column 2 | row 2 column 3 |


## 6. Individual Page Details

### 6.1 User Management

1. **Type:**
    - Access
2. **URL:**
    - User Management
3. **Conditions:**
    - As an HR Director (Admin role) at Core Tree Care, I want to have the ability to create onboarding accounts for our applicants without the need for a registration link.
4. **User Story:**
    - As an HR Director (Admin role) at Core Tree Care, I want to have the ability to create onboarding accounts for our applicants without the need for a registration link. I will utilize User Management to add applicants and select their user type (DOT Driver or General Industry).
  
5. **Acceptance Criteria:**
    1. User Management must allow the HR Director to add applicants and select their user type as either "DOT Driver" or "General Industry”, from the user type dropdown.
    2. After adding an applicant, the system should automatically generate a welcome login for that applicant, with the Username and link to reset password.
    3. When the applicant logs in using the provided credentials, they should be directed to the respective onboard form based on the driver type selected and mapping given below.
    4. Post submission of the Onboard form, the driver information form and Esign tab must be displayed. Once the driver information form is submitted, Pre-Hire services must not get triggered.
    5. The HR Director must see the onboard entries in the Onboard list view of all driver and should have the option to start the Pre Hire Services, on right-click.
    6. Upon clicking "Start Pre Hire Services," the system should initiate Foley services for the applicant's onboarding.

>[!VIDEO](https://video.tv.adobe.com/v/29770/?quality=12)


This is `inline code` within a paragraph of text.

See [Overview example article](../../overview.md)




### 6.2 Welcome Email Update

1. **Subject:**
    - Bienvenido a HUB Drive Online - Sistema de Seguimiento de Solicitantes de [Nombre de la Empresa]
2. **Text:**
    - Estimado/a [Nombre del Usuario],
      [Nombre de la Empresa] utiliza HUB Drive Online como su sistema de contratación y seguimiento de nuevos solicitantes. Usted ha sido agregado como nuevo solicitante. Por favor, inicie sesión en HUB Drive Online y complete su solicitud. 
      Su información de inicio de sesión es: 
      Nombre de usuario: 
      [Enlace para establecer la contraseña]

      ¿Necesita ayuda para completar su solicitud? Envíe un correo electrónico a HR@coretreecare.com o llame al (951)471-8333 para obtener asistencia.
      
      Gracias,
      HUB Drive Online.

## 7. Conclusion

This technical specification provides a comprehensive overview of the Core Tree Care HUB Drive Online Applicant Tracking System, incorporating the Spanish welcome email template for enhanced user communication.
