---
title: Реагирование на запросы по правам субъекта данных (DSR) на экспорт данных клиента PowerApps | Документы Майкрософт
description: Пошаговое руководство о том, как реагировать на запросы по правам субъекта данных (DSR) на экспорт данных клиента PowerApps.
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: 000f15ea7b1fa4e11cbe49b44e57017daf973a89
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "34552974"
---
# <a name="responding-to-data-subject-rights-dsr-requests-to-export-powerapps-customer-data"></a>Реагирование на запросы по правам субъекта данных (DSR) на экспорт данных клиента PowerApps
"Право переносимости данных" позволяет субъектам данных запрашивать копии персональных данных в электронном формате (то есть в структурированном, часто используемом, пригодном для машинного чтения совместимом формате), которые можно передавать другому контроллеру данных.

* Доступ к веб-сайтам: [портал PowerApps](https://web.powerapps.com), [центр администрирования PowerApps](https://admin.powerapps.com/) и [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)

* Доступ к PowerShell: командлеты PowerApps ([командлеты для создателей приложений](https://go.microsoft.com/fwlink/?linkid=871448), [командлеты для администраторов](https://go.microsoft.com/fwlink/?linkid=871804)) и [командлеты локального шлюза](https://go.microsoft.com/fwlink/?linkid=872238)

Ниже приведены типы персональных данных, которые могут храниться в PowerApps для конкретного пользователя, а также способы поиска и экспорта этих данных.

Ресурсы, содержащие персональные данные | Доступ к веб-сайтам |   Доступ к PowerShell
--- | --- | --
Среда | Центр администрирования PowerApps |  Командлеты PowerApps
Разрешения среды**   | Центр администрирования PowerApps    | Командлеты PowerApps
Приложение на основе холста  | Центр администрирования PowerApps <br> Портал PowerApps |    Командлеты PowerApps
Разрешения для приложения на основе холста  | Центр администрирования PowerApps <br> Портал PowerApps  | Командлеты PowerApps
Шлюз | Портал PowerApps ***   | Командлеты локального шлюза
Разрешения шлюза | Портал PowerApps ***   |
Настраиваемый соединитель | |    Разработчик приложений: доступно <br> Администратор: доступно
Разрешения для настраиваемого соединителя | |    Разработчик приложений: доступно <br> Администратор: доступно
Подключение | | Разработчик приложений: доступно <br> Администратор: доступно
Разрешения подключения  | | Разработчик приложений: доступно <br> Администратор: доступно
Параметры пользователя, параметры приложения пользователя и уведомления PowerApps | | Разработчик приложений: доступно <br> Администратор: доступно

> ** С выходом службы Common Data Service (CDS) for Apps, если в среде создается база данных, разрешения среды и приложения на основе модели хранятся в виде записей в экземпляре базы данных CDS for Apps. Руководство по реагированию на запросы DSR для пользователей, использующих CDS for Apps, см. в разделе [Реагирование на запросы по правам субъекта данных (DSR) для данных клиента в Common Data Service for Apps](common-data-service-gdpr-dsr-guide.md).

> *** Администратор имеет доступ к этим ресурсам с [портала PowerApps](https://web.powerapps.com), только если их владелец явно предоставил ему разрешения. В противном случае администратору потребуется использовать [командлеты PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

## <a name="prerequisites"></a>Технические условия

### <a name="for-users"></a>Для пользователей
Любой пользователь с действующей лицензией PowerApps может выполнять операции пользователя, описанные в этом документе, с помощью [портала PowerApps](https://web.powerapps.com) или [командлетов для создателей приложений](https://go.microsoft.com/fwlink/?linkid=871448).

### <a name="for-admins"></a>Для администраторов
Для выполнения операций администрирования, описанных в этом документе, в центре администрирования PowerApps, центре администрирования Microsoft Flow или с помощью [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) вам понадобится следующее:

* Платная лицензия PowerApps (план 2) или лицензия на пробную версию PowerApps (план 2). Вы можете зарегистрироваться для бесплатного использования 30-дневной пробной лицензии здесь: [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Лицензии на пробную версию можно продлить по истечении их срока действия.

* Права [глобального администратора Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) или [глобального администратора Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), если вам нужно выполнить поиск по ресурсам другого пользователя. (Помните, что администраторы среды имеют доступ только к тем средам и ресурсам среды, на которые у них есть разрешения.)

## <a name="step-1-export-personal-data-contained-within-environments-created-by-the-user"></a>Шаг 1. Экспорт персональных данных, содержащихся в средах, созданных пользователем

### <a name="powerapps-admin-center"></a>Центр администрирования PowerApps
Администраторы могут экспортировать все среды, созданные определенным пользователем, из [центра администрирования PowerApps](https://admin.powerapps.com/), выполнив следующие действия:

1. В [центре администрирования PowerApps](https://admin.powerapps.com/) выберите все среды вашей организации.

    ![Целевая страница центра администрирования](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Если среда была создана пользователем, отправившим запрос DSR, перейдите к странице **Подробности**, скопируйте данные и вставьте их в редактор документов (например, в Microsoft Word).

    ![Сведения о среде](./media/powerapps-gdpr-export-dsr/environment-details.png)

### <a name="powershell-cmdlets-for-app-creators"></a>Командлеты PowerShell для создателей приложений
Пользователи могут экспортировать среды, к которым у них имеется доступ в PowerApps, с помощью функции **Get-PowerAppsEnvironment** из состава [командлетов PowerShell для создателей приложений PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount
Get-PowerAppsEnvironment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Командлеты PowerShell для администраторов
Администраторы могут экспортировать все среды, которые были созданы пользователем, с помощью **Get-AdminEnvironment**, одного из [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "7557f390-5f70-4c93-8bc4-8c2faabd2ca0"
Get-AdminEnvironment -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-2-export-the-users-environment-permissions"></a>Шаг 2. Экспорт разрешений пользователя для среды
В среде пользователям могут назначаться разрешения (например, "Администратор окружения", "Создатель окружения" и т. д.), которые хранятся в PowerApps как *назначение ролей*. С выходом службы CDS for Apps, если в среде создается база данных, назначения ролей хранятся в виде записей в экземпляре базы данных CDS for Apps. Дополнительные сведения см. в статье [Администрирование сред в PowerApps](environments-administration.md).

### <a name="for-environments-without-a-cds-for-apps-database"></a>Для сред без базы данных CDS for Apps

#### <a name="powerapps-admin-center"></a>Центр администрирования PowerApps
Администраторы могут экспортировать разрешения среды пользователя из [центра администрирования PowerApps](https://admin.powerapps.com/), выполнив следующие действия:

1. В [центре администрирования PowerApps](https://admin.powerapps.com/) выберите все среды вашей организации. Вы должны быть [глобальным администратором Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) или [глобальным администратором Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), чтобы иметь возможность просматривать все среды, созданные в вашей организации.

    ![Целевая страница центра администрирования](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Выберите **Безопасность**.

    Если в вашей среде нет базы данных CDS for Apps, вы увидите раздел **Роли среды**.

3. Выберите **Администратор окружения** и **Создатель окружения** отдельно, а затем в панели поиска выполните поиск по имени пользователя.

    ![Страница "Роли среды"](./media/powerapps-gdpr-export-dsr/admin-environment-role-share-page.png)

4. Если у пользователя есть доступ к любой роли, перейдите на страницу **Пользователи**, скопируйте данные и вставьте их в редактор документов (например, в Microsoft Word).

#### <a name="powershell-cmdlets-for-admins"></a>Командлеты PowerShell для администраторов
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

### <a name="powerapps-portal"></a>Портал PowerApps
Пользователь может экспортировать приложение с [портала PowerApps](https://web.powerapps.com). Пошаговые инструкции по экспорту приложения см. в [этом](environment-and-tenant-migration.md#exporting-an-app) разделе.

### <a name="powerapps-admin-center"></a>Центр администрирования PowerApps
Администраторы могут экспортировать созданные пользователем приложения из [центра администрирования PowerApps](https://admin.powerapps.com/), выполнив следующие действия:

1. В [центре администрирования PowerApps](https://admin.powerapps.com/) выберите все среды вашей организации. Вы должны быть [глобальным администратором Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) или [глобальным администратором Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), чтобы иметь возможность просматривать все среды, созданные в вашей организации.

    ![Целевая страница центра администрирования](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Выберите **Ресурсы**, а затем щелкните **Приложения**.

3. Используя панель поиска, выполните поиск по имени пользователя. Вы получите список названий всех приложений, созданных пользователем в этой среде.

    ![Поиск приложений](./media/powerapps-gdpr-export-dsr/search-apps.png)

4. Выберите **Share** (Предоставить доступ) для всех приложений, созданных данным пользователем, и предоставьте себе доступ **Can edit** (Может изменять) к приложению.

    ![Выбор параметра предоставления доступа](./media/powerapps-gdpr-export-dsr/select-share.png)

    ![Предоставление доступа пользователю](./media/powerapps-gdpr-export-dsr/grant-access.png)

5. Получив доступ ко всем приложениям пользователя, можно экспортировать приложения с [портала PowerApps](https://web.powerapps.com). Пошаговые инструкции по экспорту приложения см. в [этом](environment-and-tenant-migration.md#exporting-an-app) разделе.

### <a name="powershell-cmdlets-for-admins"></a>Командлеты PowerShell для администраторов
Администраторы могут экспортировать приложения, которые были созданы пользователем, с помощью **Get-AdminApp**, одного из [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminApp -Owner $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-4-export-the-users-permissions-to-canvas-apps"></a>Шаг 4. Экспорт разрешений пользователя в приложения на основе холста
Каждый раз, когда к приложению получает общий доступ один из пользователей, PowerApps сохраняет запись с именем *назначение ролей*, в которой описываются разрешения пользователя в приложении (CanEdit или CanUser). Дополнительные сведения см. в разделе о [предоставлении совместного доступа к приложениям](../maker/canvas-apps/share-app.md#share-an-app).

### <a name="powershell-cmdlets-for-app-creators"></a>Командлеты PowerShell для создателей приложений
Пользователи могут экспортировать назначения ролей приложения для всех приложений, к которым у них имеется доступ, с помощью функции **Get-RoleAssignment** из состава [командлетов PowerShell для создателей приложений PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

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

### <a name="powershell-cmdlets-for-admins"></a>Командлеты PowerShell для администраторов
Администраторы могут экспортировать все назначения ролей приложения для пользователя во всех приложениях клиента с помощью **Get-AdminAppRoleAssignment**, одного из [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminAppRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-5-export-personal-data-contained-within-connections-created-by-the-user"></a>Шаг 5. Экспорт персональных данных, содержащихся в подключениях, созданных пользователем
Подключения используются вместе с соединителями при установке подключения к другим API и системам SaaS. Подключения включают в себя ссылки на пользователя, который их создал, и могут быть удалены, чтобы удалить все ссылки на пользователя.

### <a name="powershell-cmdlets-for-app-creators"></a>Командлеты PowerShell для создателей приложений
Пользователи могут экспортировать все подключения, к которым у них имеется доступ, с помощью функции **Get-Connection** из состава [командлетов PowerShell для создателей приложений PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount
Get-Connection | ConvertTo-Json | out-file -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Командлеты PowerShell для администраторов
Администраторы могут экспортировать все подключения, которые были созданы пользователем, с помощью функции **Get-AdminConnection** из состава [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnection -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-6-export-the-users-permissions-to-shared-connections"></a>Шаг 6. Экспорт разрешений пользователя на общедоступные подключения

### <a name="powershell-cmdlets-for-app-creators"></a>Командлеты PowerShell для создателей приложений
Пользователи могут экспортировать назначения ролей подключения для всех подключений, к которым у них имеется доступ, с помощью функции **Get-ConnectionRoleAssignment** из состава [командлетов PowerShell для создателей приложений PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-file -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Командлеты PowerShell для администраторов
Администраторы могут экспортировать все назначения ролей подключения для пользователя с помощью функции **Get-AdminConnectionRoleAssignment** из состава [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-7-export-personal-data-contained-within-custom-connectors-created-by-the-user"></a>Шаг 7. Экспорт персональных данных, содержащихся в настраиваемых соединителях, созданных пользователем
Настраиваемые соединители дополняют имеющиеся встроенные соединители и позволяют подключаться к другим API, SaaS и системам собственной разработки.

### <a name="powerapps-app-creator-powershell-cmdlets"></a>Командлеты PowerShell для создателей приложений PowerApps
Пользователи могут экспортировать все созданные ими настраиваемые соединители с помощью функции **Get-Connector** из состава [командлетов PowerShell для создателей приложений PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount  
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Командлеты PowerShell для администраторов
Администраторы могут экспортировать все созданные пользователем настраиваемые соединители с помощью функции **Get-AdminConnector** из состава [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-8-export-the-users-permissions-to-custom-connectors"></a>Шаг 8. Экспорт разрешений пользователя на настраиваемые соединители

### <a name="powershell-cmdlets-for-app-creators"></a>Командлеты PowerShell для создателей приложений
Пользователи могут экспортировать все назначения ролей для настраиваемых соединителей, к которым у них имеется доступ, с помощью функции **Get-ConnectorRoleAssignment** из состава [командлетов PowerShell для создателей приложений PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount  
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Командлеты PowerShell для администраторов
Администраторы могут экспортировать все назначения ролей настраиваемых соединителей для пользователя с помощью функции **Get-AdminConnectorRoleAssignment** из состава [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-9-export-powerapps-notifications-user-settings-and-user-app-settings"></a>Шаг 9. Экспорт уведомлений, параметров пользователя и параметров приложений пользователя PowerApps
PowerApps отправляет пользователям несколько типов уведомлений, в том числе в случае предоставления им общего доступа к приложению и при завершении операции экспорта в CDS for Apps. Журнал уведомлений доступен для пользователей на [портале PowerApps](https://web.powerapps.com).

В PowerApps также хранятся несколько разных пользовательских настроек и параметров, связанных со средой выполнения PowerApps и работой на портале, в том числе сведения о том, когда пользователь последний раз открывал или закреплял приложение и т. д.

### <a name="powershell-cmdlets-for-app-creators"></a>Командлеты PowerShell для создателей приложений
Пользователи могут экспортировать собственные уведомления, параметры пользователя и параметры приложений PowerApps с помощью функции **Get-AdminPowerAppsUserDetails** из состава [командлетов PowerShell для создателей приложений PowerApps](https://go.microsoft.com/fwlink/?linkid=871448).

~~~~
Add-PowerAppsAccount  
Get-AdminPowerAppsUserDetails -WriteToFile -OutputFilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Командлеты PowerShell для администраторов
Администраторы могут экспортировать уведомления, параметры пользователя и параметры приложений PowerApps для пользователя с помощью функции **Get-AdminPowerAppsUserDetails** из состава [командлетов PowerShell для администраторов PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminPowerAppsUserDetails -WriteToFile -OutputFilePath "UserDetails.json" -UserPrincipalName foobar@microsoft.com
~~~~

## <a name="step-10-export-personal-data-contained-for-a-user-stored-gateway-or-in-the-users-gateway-permissions"></a>Шаг 10. Экспорт персональных данных, содержащихся в пользовательском шлюзе или в разрешениях пользовательского шлюза

### <a name="powerapps-portal"></a>Портал PowerApps
Пользователи могут экспортировать персональные данные, хранящиеся в службе шлюза, с [портала PowerApps](https://web.powerapps.com), выполнив указанные ниже действия.

1. На [портале PowerApps](https://web.powerapps.com) в среде клиента по умолчанию выберите **Шлюзы**, а затем щелкните **Подробности** для всех шлюзов, к которым имеется доступ.

    ![Целевая страница шлюза](./media/powerapps-gdpr-export-dsr/gateway-select-details.png)

2. На странице **Подробности**, если сведения о шлюзе содержат персональные данные, скопируйте эти сведения, а затем вставьте их в текстовый редактор (например, в Microsoft Word).

    ![Сведения о шлюзе](./media/powerapps-gdpr-export-dsr/gateway-details-drillin.png)

3. Выберите **Share** (Предоставить доступ), скопируйте содержимое страницы и вставьте его в текстовый редактор (например, в Microsoft Word).

    ![Сведения о шлюзе](./media/powerapps-gdpr-export-dsr/gateway-details-share.png)

### <a name="gateway-powershell-cmdlets"></a>Командлеты PowerShell шлюза
Имеются также командлеты PowerShell, позволяющие извлечь, изменить и удалить персональные шлюзы. Дополнительные сведения см. в разделе о [командлетах локального шлюза](https://go.microsoft.com/fwlink/?linkid=872238).

### <a name="administrators"></a>Администраторы
Инструкции по управлению шлюзами в организации см. в разделе **Администрирование на уровне клиента** в статье [Общие сведения о локальных шлюзах данных в Microsoft PowerApps](https://docs.microsoft.com/powerapps/maker/canvas-apps/gateway-reference#tenant-level-administration).

## <a name="step-11-export-the-users-personal-data-in-microsoft-flow"></a>Шаг 11. Экспорт персональных данных пользователя в Microsoft Flow
Лицензии PowerApps всегда содержат возможности Microsoft Flow. Помимо этого, Microsoft Flow также доступна в качестве автономной службы. Рекомендации по реагированию на запросы DSR для пользователей, использующих службу Microsoft Flow, см. в разделе [Реагирование на запросы субъектов данных GDPR для Microsoft Flow](https://go.microsoft.com/fwlink/?linkid=872250).

> [!IMPORTANT]
>  Рекомендуется, чтобы администраторы выполнили этот шаг для пользователей PowerApps.
>
>

## <a name="step-12-export-the-users-personal-data-in-cds-for-apps-instances"></a>Шаг 12. Экспорт персональных данных пользователя из экземпляров CDS for Apps
Некоторые лицензии PowerApps позволяют пользователям вашей организации создавать экземпляры CDS for Apps и приложения в этой службе, в том числе "План сообщества PowerApps", который является бесплатной лицензией, позволяющей пользователям тестировать CDS for Apps в отдельной среде. Чтобы узнать, какие возможности CDS for Apps включены во всех лицензиях PowerApps, см. [страницу с ценами на PowerApps](https://powerapps.microsoft.com/pricing).

Руководство по реагированию на запросы DSR для пользователей, использующих CDS for Apps, см. в разделе [Реагирование на запросы по правам субъекта данных (DSR) для данных клиента в Common Data Service for Apps](common-data-service-gdpr-dsr-guide.md).

> [!IMPORTANT]
>  Рекомендуется, чтобы администраторы выполнили этот шаг для пользователей PowerApps.
>
>
