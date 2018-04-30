---
title: Реагирование на запросы субъектов данных (DSR) на экспорт пользовательских данных PowerApps | Документация Майкрософт
description: Реагирование на запросы субъектов данных (DSR) на экспорт пользовательских данных PowerApps
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms-topic: article
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/18/2018
ms.author: jamesol
ms.openlocfilehash: 58edfa4d82f58094f12df47ed330783cd3c40a40
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-export-data-subject-rights-dsr-requests-for-powerapps-customer-data"></a>Реагирование на запросы субъектов данных (DSR) на экспорт пользовательских данных PowerApps

*Право переносимости данных* позволяет субъектам данных запрашивать копии персональных данных в электронном формате (то есть в структурированном, часто используемом, пригодном для машинного чтения совместимом формате), которые можно передавать другому контроллеру данных.

* Доступ к веб-сайтам: [портал создателей PowerApps](https://web.powerapps.com), [центр администрирования PowerApps](https://admin.powerapps.com/) и [портал Office 365 Service Trust Portal](https://servicetrust.microsoft.com/).

* Доступ к PowerShell. Командлеты PowerApps ([командлеты создателей](https://go.microsoft.com/fwlink/?linkid=871448), [командлеты администраторов](https://go.microsoft.com/fwlink/?linkid=871804)) и [командлеты локального шлюза](https://go.microsoft.com/fwlink/?linkid=872238).

Ниже приведены типы персональных данных, которые могут храниться в PowerApps для конкретного пользователя, а также способы поиска и экспорта этих данных.

Ресурсы, содержащие персональные данные | Доступ к веб-сайтам |   Доступ к PowerShell
--- | --- | --
Среда | Центр администрирования PowerApps |  Командлеты PowerApps
Разрешения среды**   | Центр администрирования PowerApps    | Командлеты PowerApps
Приложение на основе холста  | Центр администрирования PowerApps <br> Портал создателей PowerApps |  Командлеты PowerApps
Разрешения для приложения на основе холста  | Центр администрирования PowerApps <br> Портал создателей PowerApps    | Командлеты PowerApps
Шлюз | Портал создателей PowerApps*** | Командлеты локального шлюза
Разрешения шлюза | Портал создателей PowerApps*** |
Настраиваемый соединитель | |    Создатель: доступен <br> Администратор: на стадии разработки
Разрешения для настраиваемого соединителя | |    Создатель: доступен <br> Администратор: на стадии разработки
Подключение | | Создатель: доступен <br> Администратор: на стадии разработки
Разрешения подключения  | | Создатель: доступен <br> Администратор: на стадии разработки
Параметры пользователя, параметры приложения пользователя и уведомления PowerApps | | Создатель: доступен <br> Администратор: на стадии разработки

> ** С выходом службы Common Data Service for Apps, если в среде создается база данных, разрешения среды и приложения на основе модели хранятся в виде записей в экземпляре базы данных CDS for Apps. Руководство по реагированию на запросы DSR для пользователей, использующих CDS for Apps, см. [здесь](https://go.microsoft.com/fwlink/?linkid=872251).

> *** Администратор будет иметь доступ к этим ресурсам из [PowerApps](https://web.powerapps.com), только если их владелец явно предоставил ему разрешения.  В противном случае администратору необходимо использовать [командлеты PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

## <a name="prerequisites"></a>Технические условия

### <a name="for-users"></a>Для пользователей
Любой пользователь с действующей лицензией PowerApps может выполнять операции пользователя, описанные в этом документе, с помощью [PowerApps](https://web.powerapps.com) или [командлетов создателя](https://go.microsoft.com/fwlink/?linkid=871448).

### <a name="for-admins"></a>Для администраторов
Для выполнения операций администрирования, описанных в этом документе, в центре администрирования PowerApps, центре администрирования Microsoft Flow или с помощью [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) вам понадобится учетная запись со следующими разрешениями.

* Платная лицензия PowerApps (план 2) или бесплатная ознакомительная версия PowerApps (план 2). Вы можете зарегистрироваться для бесплатного использования 30-дневной пробной лицензии здесь: [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Лицензии на пробную версию можно продлить по истечении их срока действия.

* Если вам необходимо выполнить поиск по ресурсам другого пользователя, также необходимы разрешения [глобального администратора Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) или [глобального администратора Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal). Вам доступны только те среды и ресурсы среды, на которые у вас есть права администратора среды.

## <a name="step-1-export-personal-data-contained-within-environments-created-by-the-user"></a>Шаг 1. Экспорт персональных данных, содержащихся в средах, созданных пользователем

### <a name="powerapps-admin-center"></a>Центр администрирования PowerApps
Администраторы могут экспортировать все среды, созданные определенным пользователем, из [центра администрирования PowerApps](https://admin.powerapps.com/), выполнив следующие действия:
1. В [центре администрирования PowerApps](https://admin.powerapps.com/) выберите все среды вашей организации.

  ![Целевая страница центра администрирования](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Если среда была создана пользователем, отправившим запрос DSR, перейдите к странице **Подробности**, скопируйте данные и вставьте их в редактор документов (например, в Microsoft Word).

  ![Сведения о среде](./media/powerapps-gdpr-export-dsr/environment-details.png)

### <a name="powerapps-maker-powershell-cmdlets"></a>Командлеты PowerShell для создателей PowerApps
Пользователи могут экспортировать среды, к которым у них имеется доступ в PowerApps, с помощью **Get-PowerAppsEnvironment**, одного из [командлетов PowerShell для создателей PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount
Get-PowerAppsEnvironment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>Командлеты PowerShell для администраторов PowerApps
Администраторы могут экспортировать все среды, которые были созданы пользователем, с помощью **Get-AdminEnvironment**, одного из [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "7557f390-5f70-4c93-8bc4-8c2faabd2ca0"
Get-AdminEnvironment -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-2-export-the-users-environment-permissions"></a>Шаг 2. Экспорт разрешений пользователя для среды
В среде пользователям могут назначаться разрешения (например, "Администратор окружения", "Создатель окружения" и т. д.), которые хранятся в PowerApps как *назначение ролей*. С выходом службы CDS for Apps, если в среде создается база данных, эти назначения ролей хранятся в виде записей в экземпляре базы данных CDS for Apps. Дополнительные сведения см. в статье [Администрирование сред в PowerApps](environments-administration.md).

### <a name="for-environments-without-a-cds-for-apps-database"></a>Для сред без базы данных CDS for Apps

#### <a name="powerapps-admin-center"></a>Центр администрирования PowerApps
Администраторы могут экспортировать разрешения среды пользователя из [центра администрирования PowerApps](https://admin.powerapps.com/), выполнив следующие действия:

1. В [центре администрирования PowerApps](https://admin.powerapps.com/) выберите все среды вашей организации. Вы должны быть [глобальным администратором Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) или [глобальным администратором Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), чтобы иметь возможность просматривать все среды, созданные в вашей организации.

  ![Целевая страница центра администрирования](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2.  Выберите **Безопасность**.

    Если в вашей среде нет базы данных CDS for Apps, вы увидите раздел **Роли среды**.

3. Выберите **Администратор окружения** и **Создатель окружения** отдельно, а затем в панели поиска выполните поиск по имени пользователя.

  ![Страница "Роли среды"](./media/powerapps-gdpr-export-dsr/admin-environment-role-share-page.png)

5. Если у пользователя есть доступ к любой роли, перейдите на страницу **Пользователи**, скопируйте данные и вставьте их в редактор документов (например, в Microsoft Word).

#### <a name="powerapps-admin-powershell-cmdlets"></a>Командлеты PowerShell для администраторов PowerApps
Администраторы могут экспортировать все назначения ролей среды для пользователя во всех средах без базы данных CDS for Apps с помощью **Get-AdminEnvironmentRoleAssignment**, одного из [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminEnvironmentRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

> [!IMPORTANT]
>  Эта функция работает только в средах, где нет экземпляра базы данных CDS for Apps.
>
>

### <a name="for-environments-with-a-cds-for-apps-database"></a>Для сред с базой данных CDS for Apps
С выходом службы CDS for Apps, если в среде создается база данных, назначения ролей хранятся в виде записей в экземпляре базы данных CDS for Apps. Сведения о том, как удалить персональные данные из экземпляра базы данных CDS for Apps, см. в [этой](https://go.microsoft.com/fwlink/?linkid=871886) статье.
 
## <a name="step-3-export-personal-data-contained-within-canvas-apps-created-by-the-user"></a>Шаг 3. Экспорт персональных данных, содержащихся в приложениях на основе холста, созданных пользователем

### <a name="powerapps-maker-portal"></a>Портал создателей PowerApps
Пользователь может экспортировать приложение из [PowerApps](https://web.powerapps.com). Пошаговые инструкции по экспорту приложения см. в [этом](environment-and-tenant-migration.md#exporting-an-app) разделе.

### <a name="powerapps-admin-center"></a>Центр администрирования PowerApps
Администраторы могут экспортировать созданные пользователем приложения из [центра администрирования PowerApps](https://admin.powerapps.com/), выполнив следующие действия:

1. В [центре администрирования PowerApps](https://admin.powerapps.com/) выберите все среды вашей организации. Вы должны быть [глобальным администратором Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) или [глобальным администратором Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), чтобы иметь возможность просматривать все среды, созданные в вашей организации.

  ![Целевая страница центра администрирования](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2.  Выберите **Ресурсы**, а затем щелкните **Приложения**.

3. Используя панель поиска, выполните поиск по имени пользователя. Вы получите список названий всех приложений, созданных пользователем в этой среде.

  ![Поиск приложений](./media/powerapps-gdpr-export-dsr/search-apps.png)

4. Выберите **Share** (Предоставить доступ) для всех приложений, созданных данным пользователем, и предоставьте себе доступ **Can edit** (Может изменять) к приложению.

  ![Выбор параметра предоставления доступа](./media/powerapps-gdpr-export-dsr/select-share.png)

  ![Предоставление доступа пользователю](./media/powerapps-gdpr-export-dsr/grant-access.png)

5. Получив доступ ко всем приложениям пользователя, можно экспортировать приложения из [PowerApps](https://web.powerapps.com). Пошаговые инструкции по экспорту приложения см. в [этом](environment-and-tenant-migration.md#exporting-an-app) разделе.

### <a name="powerapps-admin-powershell-cmdlets"></a>Командлеты PowerShell для администраторов PowerApps
Администраторы могут экспортировать приложения, которые были созданы пользователем, с помощью **Get-AdminApp**, одного из [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminApp -Owner $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-4-export-the-users-permissions-to-canvas-apps"></a>Шаг 4. Экспорт разрешений пользователя в приложения на основе холста
Каждый раз, когда к приложению получает общий доступ один из пользователей, PowerApps сохраняет запись с именем *назначение ролей*, в которой описываются разрешения пользователя в приложении (CanEdit или CanUser). Дополнительные сведения см. в разделе о [предоставлении совместного доступа к приложениям](../maker/canvas-apps/share-app.md#share-an-app).

### <a name="powerapps-maker-powershell-cmdlets"></a>Командлеты PowerShell для создателей PowerApps
Пользователи могут экспортировать назначения ролей приложения для всех приложений, к которым у них имеется доступ, с помощью **Get-RoleAssignment**, одного из [командлетов PowerShell для создателей PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount
Get-AppRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-center"></a>Центр администрирования PowerApps
Администраторы могут экспортировать назначения ролей приложения для пользователя из [центра администрирования PowerApps](https://admin.powerapps.com/), выполнив следующие действия:

1. В [центре администрирования PowerApps](https://admin.powerapps.com/) выберите все среды вашей организации. Вы должны быть [глобальным администратором Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) или [глобальным администратором Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), чтобы иметь возможность просматривать все среды, созданные в вашей организации.

  ![Целевая страница центра администрирования](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Для каждой среды выберите **Ресурсы**, а затем щелкните **Приложения**.

3. Выберите **Share** (Предоставить доступ) для каждого из приложений в среде.

  ![Выбор параметра предоставления доступа](./media/powerapps-gdpr-export-dsr/select-admin-share-nofilter.png)

4. Если пользователь имеет доступ к приложению, перейдите на страницу **Share** (Предоставление доступа), скопируйте данные и вставьте их в редактор документов (например, в Microsoft Word).

  ![Страница предоставления общего доступа к приложению администратора](./media/powerapps-gdpr-export-dsr/admin-share-page.png)

### <a name="powerapps-admin-powershell-cmdlets"></a>Командлеты PowerShell для администраторов PowerApps
Администраторы могут экспортировать все назначения ролей приложения для пользователя во всех приложениях клиента с помощью **Get-AdminAppRoleAssignment**, одного из [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminAppRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-5-export-personal-data-contained-within-connections-created-by-the-user"></a>Шаг 5. Экспорт персональных данных, содержащихся в подключениях, созданных пользователем
Подключения используются вместе с соединителями при установке подключения к другим API и системам SaaS. Подключения включают в себя ссылки на пользователя, который их создал, и могут быть удалены, чтобы удалить все ссылки на пользователя.

### <a name="powerapps-maker-powershell-cmdlets"></a>Командлеты PowerShell для создателей PowerApps
Пользователи могут экспортировать все подключения, к которым у них имеется доступ, с помощью **Get-Connection**, одного из [командлетов PowerShell для создателей PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount
Get-Connection | ConvertTo-Json | out-file -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>Командлеты PowerShell для администраторов PowerApps
Функция, позволяющая администраторам экспортировать созданные пользователем подключения с помощью [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804), находится в стадии разработки.
 
## <a name="step-6-export-the-users-permissions-to-shared-connections"></a>Шаг 6. Экспорт разрешений пользователя на общедоступные подключения
### <a name="powerapps-maker-powershell-cmdlets"></a>Командлеты PowerShell для создателей PowerApps
Пользователи могут экспортировать назначения ролей подключения для всех подключений, к которым у них имеется доступ, с помощью одного из [командлетов PowerShell для создателей PowerApps](https://go.microsoft.com/fwlink/?linkid=871448) (**Get-ConnectionRoleAssignment**).

~~~~
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | out-file -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>Командлеты PowerShell для администраторов PowerApps
Функция, позволяющая администраторам экспортировать назначения ролей подключения для пользователя с помощью [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804), находится в стадии разработки.

## <a name="step-7-export-personal-data-contained-within-custom-connectors-created-by-the-user"></a>Шаг 7. Экспорт персональных данных, содержащихся в настраиваемых соединителях, созданных пользователем
Настраиваемые соединители дополняют имеющиеся встроенные соединители и позволяют подключаться к другим API, SaaS и системам собственной разработки.

### <a name="powerapps-maker-powershell-cmdlets"></a>Командлеты PowerShell для создателей PowerApps
Пользователи могут экспортировать все созданные ими настраиваемые соединители с помощью **Get-Connector**, одного из [командлетов PowerShell для создателей PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount  
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>Командлеты PowerShell для администраторов PowerApps
Функция, позволяющая администраторам экспортировать созданные пользователем настраиваемые соединители с помощью [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804), находится в стадии разработки.

## <a name="step-8-export-the-users-permissions-to-custom-connectors"></a>Шаг 8. Экспорт разрешений пользователя на настраиваемые соединители

### <a name="powerapps-maker-powershell-cmdlets"></a>Командлеты PowerShell для создателей PowerApps
Пользователи могут экспортировать назначения ролей для настраиваемых соединителей, к которым у них имеется доступ, с помощью **Get-ConnectorRoleAssignment**, одного из [командлетов PowerShell для создателей PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount  
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-powershell-cmdlets"></a>Командлеты PowerShell для администраторов PowerApps
Функция, позволяющая администраторам экспортировать назначения ролей настраиваемого соединителя для пользователя с помощью [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804), находится в стадии разработки.
 
## <a name="step-9-export-powerapps-notifications-user-settings-and-user-app-settings"></a>Шаг 9. Экспорт уведомлений, параметров пользователя и параметров приложений пользователя PowerApps
PowerApps отправляет пользователям несколько типов уведомлений, в том числе в случае предоставления им общего доступа к приложению и при завершении операции экспорта в CDS for Apps. Журнал уведомлений доступен для пользователей в [PowerApps](https://web.powerapps.com).

В PowerApps также хранятся несколько разных пользовательских настроек и параметров, связанных со средой выполнения PowerApps и работой на портале, в том числе сведения о том, когда пользователь последний раз открывал или закреплял приложение и т. д.

### <a name="powerapps-maker-powershell-cmdlets"></a>Командлеты PowerShell для создателей PowerApps
Функция, позволяющая экспортировать пользовательские уведомления, параметры пользователя и параметры приложения PowerApps с помощью [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804), находится в стадии разработки.

### <a name="powerapps-admin-powershell-cmdlets"></a>Командлеты PowerShell для администраторов PowerApps
Функция, позволяющая администраторам экспортировать пользовательские уведомления, параметры пользователя и параметры приложения PowerApps с помощью [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804), находится в стадии разработки.

## <a name="step-10-export-personal-data-contained-for-a-user-stored-gateway-or-in-the-users-gateway-permissions"></a>Шаг 10. Экспорт персональных данных, содержащихся в пользовательском шлюзе или в разрешениях пользовательского шлюза

### <a name="powerapps-maker-portal"></a>Портал создателей PowerApps
Пользователи могут экспортировать персональные данные, хранящиеся в службе шлюза, из [PowerApps](https://web.powerapps.com), выполнив следующие действия:

1. В [PowerApps](https://web.powerapps.com) в среде клиента по умолчанию выберите **Шлюзы**, а затем щелкните **Подробности** для всех шлюзов, к которым имеется доступ.

  ![Целевая страница шлюза](./media/powerapps-gdpr-export-dsr/gateway-select-details.png)

2. На странице **Подробности**, если сведения о шлюзе содержат персональные данные, скопируйте эти сведения, а затем вставьте их в текстовый редактор (например, в Microsoft Word).

  ![Сведения о шлюзе](./media/powerapps-gdpr-export-dsr/gateway-details-drillin.png)

3. Выберите **Share** (Предоставить доступ), скопируйте содержимое страницы и вставьте его в текстовый редактор (например, в Microsoft Word).

  ![Сведения о шлюзе](./media/powerapps-gdpr-export-dsr/gateway-details-share.png)

### <a name="gateway-powershell-cmdlets"></a>Командлеты PowerShell шлюза
Имеются также командлеты PowerShell, позволяющие извлечь, изменить и удалить персональные шлюзы. Дополнительные сведения см. в разделе о [командлетах локального шлюза](https://go.microsoft.com/fwlink/?linkid=872238).

## <a name="step-11-export-the-users-personal-data-in-microsoft-flow"></a>Шаг 11. Экспорт персональных данных пользователя в Microsoft Flow
Лицензии PowerApps всегда содержат возможности Microsoft Flow. Помимо этого, Microsoft Flow также доступна в качестве автономной службы. Рекомендации по реагированию на запросы DSR для пользователей, использующих службу Microsoft Flow, см. [здесь](https://go.microsoft.com/fwlink/?linkid=872250).

> [!IMPORTANT] 
>  Рекомендуется, чтобы администраторы выполнили этот шаг для пользователей PowerApps.
>
>

## <a name="step-12-export-the-users-personal-data-in-cds-for-apps-instances"></a>Шаг 12. Экспорт персональных данных пользователя из экземпляров CDS for Apps
Некоторые лицензии PowerApps позволяют пользователям вашей организации создавать экземпляры CDS for Apps и приложения в этой службе, в том числе "План сообщества PowerApps", который является бесплатной лицензией, позволяющей пользователям тестировать CDS for Apps в отдельной среде. Чтобы узнать, какие возможности CDS for Apps включены во всех лицензиях PowerApps, см. [страницу с ценами на PowerApps](https://powerapps.microsoft.com/pricing).

Руководство по реагированию на запросы DSR для пользователей, использующих CDS for Apps, см. [здесь](https://go.microsoft.com/fwlink/?linkid=872251).

> [!IMPORTANT]
>  Рекомендуется, чтобы администраторы выполнили этот шаг для пользователей PowerApps.
>
>
