---
title: Поддержка PowerShell (предварительная версия) | Документация Майкрософт
description: Описание различных командлетов PowerShell и пошаговое руководство по их установке и запуску.
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: reference
ms.date: 08/23/2018
ms.author: jamesol
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 0d5d2cee770e03c4e587db0bff624f34395ed92c
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864435"
---
# <a name="powershell-support-for-powerapps-preview"></a>Поддержка PowerShell в PowerApps (предварительная версия)
С помощью предварительной версии командлетов PowerShell для создателей и администраторов приложений вы можете автоматизировать многие задачи мониторинга и управления, которые раньше выполнялись только вручную в [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) или [центре администрирования PowerApps](https://admin.powerapps.com).

## <a name="installation"></a>Установка
Прежде чем выполнять командлеты PowerShell для создателей приложений, выполните указанные ниже действия.

1. Скачайте [файл сценариев PowerShell](https://go.microsoft.com/fwlink/?linkid=2006349).

2. Распакуйте файлы в папку.

3. Откройте командное окно PowerShell (с правами администратора) в этой же папке.

4. Выполните следующую одноразовую команду PowerShell (предполагается, что вы никогда не выполняли команды PowerShell на текущем компьютере):

    ```
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Force
    ```

5. Импортируйте необходимые модули, используя следующие команды:

    ```
    Import-Module .\Microsoft.PowerApps.Administration.PowerShell.psm1 -Force
    Import-Module .\Microsoft.PowerApps.PowerShell.psm1 -Force
    ```

6.  Существует [известная проблема](https://powerusers.microsoft.com/t5/Administering-PowerApps/Getting-errors-when-I-try-to-import-the-preview-powerapps/td-p/109036), из-за которой может потребоваться ручная разблокировка файлов PowerShell с помощью следующей команды:

    ```
    dir . | Unblock-File
    ```
7. Прежде чем обращаться к любой из команд, укажите свои учетные данные, используя команду ниже. Эти учетные данные обновляются максимум за 8 часов, прежде чем вам потребуется снова войти в систему, чтобы продолжить использование командлетов.

    ```
    # This call will open a prompt to collect the credentials (AAD account & password) that will be used by the commands
    Add-PowerAppsAccount
    ```

    ```
    # Here is how you can pass in credentials (avoiding opening a prompt)
    $pass = ConvertTo-SecureString "password" -AsPlainText -Force
    Add-PowerAppsAccount -Username foo@bar.com -Password $pass
    ```


## <a name="powerapps-cmdlets-for-app-creators-preview"></a>Командлеты PowerApps для создателей приложений (предварительная версия)

### <a name="prerequisite"></a>Необходимое условие
Пользователи с действующей лицензией PowerApps могут выполнять операции в этих командлетах. При этом они будут иметь доступ только к ресурсам (например, приложениям, потокам и т. д.), которые были созданы или предоставлены им для общего доступа.

### <a name="cmdlet-list"></a>Список командлетов
> [!NOTE]
> В последнем выпуске мы обновили некоторые из имен функций командлетов, добавив подходящие префиксы для предотвращения конфликтов. Обзор изменений см. в таблице ниже.

| Цель | Командлет |
| --- | --- |
| Чтение сред | Get-PowerAppEnvironment *(ранее Get-PowerAppsEnvironment)* <br> Get-FlowEnvironment
| Чтение, обновление и удаление приложения на основе холста | Get-PowerApp *(ранее Get-App)* <br> Remove-PowerApp *(ранее Remove-App)* <br> Publish-PowerApp *(ранее Publish-App)* <br> Set-AppDisplayName *(ранее Set-PowerAppDisplayName)*<br> Get-PowerAppVersion *(ранее Get-AppVersion)* <br> Restore-PowerAppVersion *(ранее Restore-AppVersion)*
| Чтение, обновление и удаление разрешений приложений на основе холста | Get-PowerAppRoleAssignment *(ранее Get-AppRoleAssignment)* <br> Set-PowerAppRoleAssignment *(ранее Set-AppRoleAssignment)* <br> Remove-PowerAppRoleAssignment *(ранее Remove-AppRoleAssignment)*
| Read, update, and delete a flow | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow
| Чтение, обновление и удаление разрешений потоков | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole
| Чтение и ответ на утверждения потоков | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest
| Чтение и удаление соединений | Get-PowerAppConnection *(ранее Get-Connection)* <br> Remove-PowerAppConnection *(ранее Remove-Connection)*
| Чтение, обновление и удаление разрешений соединений | Get-PowerAppConnectionRoleAssignment *(ранее Get-ConnectionRoleAssignment)* <br> Set-PowerAppConnectionRoleAssignment *(ранее Set-ConnectionRoleAssignment)* <br> Remove-PowerAppConnectionRoleAssignment *(ранее Remove-ConnectionRoleAssignment)*
| Чтение и удаление соединителей | Get-PowerAppConnector *(ранее Get-Connector)* <br> Remove-PowerAppConnector *(ранее Remove-Connector)*
| Чтение, обновление и удаление пользовательских разрешений соединителей | Get-PowerAppConnectorRoleAssignment *(ранее Get-ConnectorRoleAssignment)* <br> Set-PowerAppConnectorRoleAssignment *(ранее Set-ConnectorRoleAssignment)* <br> Remove-PowerAppConnectorRoleAssignment *(ранее Remove-ConnectorRoleAssignment)*


> [!NOTE]
> Следующие команды позволяют понять синтаксис и просмотреть примеры каждого из командлетов:
>```
>Get-Help Get-PowerAppEnvironment
>Get-Help Get-PowerAppEnvironment -Examples
>Get-Help Get-PowerAppEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>Командлеты PowerApps для администраторов (предварительная версия)

### <a name="prerequisite"></a>Необходимое условие
Чтобы выполнить операции администрирования в командлетах администратора, понадобится следующее:

* Платная лицензия PowerApps (план 2) или лицензия на пробную версию PowerApps (план 2). Вы можете зарегистрироваться для бесплатного использования 30-дневной пробной лицензии здесь: [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Лицензии на пробную версию можно продлить по истечении их срока действия.

* Права [глобального администратора Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) или [глобального администратора Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), если вам нужно выполнить поиск по ресурсам другого пользователя. (Помните, что администраторы среды имеют доступ только к тем средам и ресурсам среды, на которые у них есть разрешения.)

### <a name="cmdlet-list"></a>Список командлетов
> [!NOTE]
> В последнем выпуске мы обновили некоторые из имен функций командлетов, добавив подходящие префиксы для предотвращения конфликтов. Обзор изменений см. в таблице ниже.

| Цель | Командлеты
| --- | ---
| Чтение, обновление и удаление сред и баз данных службы Common Data Service for Apps | New-AdminPowerAppEnvironment **\*Новый\*** <br> Set-AdminPowerAppEnvironmentDisplayName **\*Новый\*** <br> Get-AdminPowerAppEnvironment *(ранее Get-AdminEnvironment)* <br> Remove-AdminPowerAppEnvironment *(ранее Remove-AdminEnvironment)* <br> New-AdminPowerAppCdsDatabase **\*Новый\*** <br> Get-AdminPowerAppCdsDatabaseLanguages **\*Новый\*** <br> Get-AdminPowerAppCdsDatabaseCurrencies **\*Новый\*** <br> Get-AdminPowerAppEnvironmentLocations **\*Новый\***
| Чтение, обновление и удаление разрешений среды <br><br> *Эти командлеты сейчас работают только в средах без базы данных Common Data Service (CDS) for Apps.* | Get-AdminPowerAppEnvironmentRoleAssignment *(ранее Get-AdminEnvironmentRoleAssignment)* <br> Set-AdminPowerAppEnvironmentRoleAssignment *(ранее Set-AdminEnvironmentRoleAssignment)* <br> Remove-AdminPowerAppEnvironmentRoleAssignment *(ранее Remove-AdminEnvironmentRoleAssignment)*
| Чтение, обновление и удаление приложений на основе холста | Get-AdminPowerApp *(ранее Get-AdminApp)* <br> Remove-AdminPowerApp *(ранее Remove-AdminApp)* <br> Get-AdminPowerAppConnectionReferences **\*Новый\*** <br> Set-AdminPowerAppAsFeatured **\*Новый\*** <br> Clear-AdminPowerAppAsFeatured **\*Новый\*** <br> Set-AdminPowerAppAsHero **\*Новый\*** <br> Clear-AdminPowerAppAsHero **\*Новый\*** <br> Set-AdminPowerAppApisToBypassConsent **\*Новый\*** <br> Clear-AdminPowerAppApisToBypassConsent **\*Новый\***
| Чтение, обновление и удаление разрешений приложений на основе холста | Get-AdminPowerAppRoleAssignment *(ранее Get-AdminAppRoleAssignment)* <br> Remove-AdminPowerAppRoleAssignment *(ранее Remove-AdminAppRoleAssignment)* <br> Set-AdminPowerAppRoleAssignment *(ранее Set-AdminAppRoleAssignment)* <br> Set-AdminPowerAppOwner *(ранее Set-AdminAppOwner)*
| Чтение, обновление и удаление потоков | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow <br> Remove-AdminFlowApprovals **\*Новый\***
| Чтение, обновление и удаление разрешений потоков | Get-AdminFlowOwnerRole <br> Set-AdminFlowOwnerRole <br> Remove-AdminFlowOwnerRole
| Чтение и удаление соединений | Get-AdminPowerAppConnection *(ранее Get-AdminConnection)* <br> Remove-AdminPowerAppConnection *(ранее Remove-AdminConnection)*
| Чтение, обновление и удаление разрешений соединений | Get-AdminPowerAppConnectionRoleAssignment *(ранее Get-AdminConnectionRoleAssignment)* <br> Set-AdminPowerAppEnvironmentConnectionRoleAssignment *(ранее Set-AdminConnectionRoleAssignment)* <br> Remove-AdminPowerAppConnectionRoleAssignment *(ранее Remove-AdminConnectionRoleAssignment)*
| Получение и удаление пользовательских соединителей | Get-AdminPowerAppConnector *(ранее Get-AdminConnector)* <br> Remove-AdminPowerAppConnector *(ранее Remove-AdminConnector)*
| Чтение, обновление и удаление пользовательских разрешений соединителей | Get-AdminPowerAppConnectorRoleAssignment *(ранее Get-AdminConnectorRoleAssignment)*<br> Set-AdminPowerAppConnectorRoleAssignment *(ранее Set-AdminConnectorRoleAssignment)* <br> Remove-AdminPowerAppConnectorRoleAssignment *(ранее Remove-AdminConnectorRoleAssignment)*
| Чтение параметров пользователя, параметров приложения пользователя и уведомлений PowerApps | Get-AdminPowerAppsUserDetails
| Чтение и удаление параметров Microsoft Flow пользователя, которые не видны ему, но поддерживают выполнение потока | Get-AdminFlowUserDetails <br> Remove-AdminFlowUserDetails
| Создание, чтение, обновление и удаление политик защиты от потери данных для вашей организации | Get-AdminDlpPolicy *(ранее Get-AdminApiPolicy)* <br> Add-AdminDlpPolicy *(ранее Add-AdminApiPolicy)* <br> Remove-AdminDlpPolicy *(ранее Remove-AdminApiPolicy)* <br> Set-AdminDlpPolicy *(ранее Set-AdminApiPolicy)* <br> Add-ConnectorToBusinessDataGroup <br>  Remove-ConnectorFromBusinessDataGroup

> [!NOTE]
> Следующие команды позволяют понять синтаксис и просмотреть примеры каждого из командлетов:
>```
>Get-Help Get-AdminPowerAppEnvironment
>Get-Help Get-AdminPowerAppEnvironment -Examples
>Get-Help Get-AdminPowerAppEnvironment -Detailed
>```

## <a name="version-history"></a>Журнал версий
| Версия | Дата | Обновления |
| --- | --- | --- |
| 1.0 | 23.04.2018 | <ol> <li> Начальный запуск командлетов PowerApps для создателей приложений (предварительная версия), включая командлеты управления для сред, приложений, потоков, утверждения потоков, соединений и настраиваемых соединителей </li> <li> Начальный запуск командлетов PowerApps для администраторов (предварительная версия), включая командлеты администрирования для сред, приложений и потоков </li></ol>|
| 2.0 | 24.05.2018 | <ol> <li> Исправления незначительных ошибок в командлетах для создателей и администраторов приложений </li> <li> Добавлены следующие новые командлеты администрирования: <br> Get-AdminConnection <br> Remove-AdminConnection <br> Get-AdminConnectionRoleAssignment <br> Set-AdminConnectionRoleAssignment <br>Remove-AdminConnectionRoleAssignment <br>Get-AdminConnector  <br>Remove-AdminConnector <br>Set-AdminConnectorRoleAssignment  <br>Get-AdminConnectorRoleAssignment  <br>Remove-AdminConnectorRoleAssignment <br>Get-AdminPowerAppsUserDetails <br>Get-AdminFlowUserDetails <br>Remove-AdminFlowUserDetails <br>Get-AdminApiPolicy  <br>Add-AdminApiPolicy <br>Remove-AdminApiPolicy <br>Set-AdminApiPolicy <br>Add-ConnectorToBusinessDataGroup  <br>Remove-ConnectorFromBusinessDataGroup </li> </ol>
| 3.0 | 30.07.2018 | <ol> <li> Добавлена возможность передачи учетных данных в Add-PowerAppsAccount (для включения повторяющихся скриптов) </li> <li>  Исправления незначительных ошибок в командлетах для создателей и администраторов приложений </li> <li> Добавлен префикс "PowerApp" или "Flow" в каждый командлет для создателей приложений </li> <li>  Добавлен префикс "AdminPowerApp" или "AdminFlow" в каждый командлет для администраторов </li> <li> Добавлены следующие новые командлеты администрирования: <br> New-AdminPowerAppEnvironment <br> Set-AdminPowerAppEnvironmentDisplayName <br> New-AdminPowerAppCdsDatabase <br> Get-AdminPowerAppCdsDatabaseLanguages <br> Get-AdminPowerAppCdsDatabaseCurrencies <br> Get-AdminPowerAppEnvironmentLocations <br> Get-AdminPowerAppConnectionReferences <br> Set-AdminPowerAppAsFeatured <br> Clear-AdminPowerAppAsFeatured <br> Set-AdminPowerAppAsHero <br> Clear-AdminPowerAppAsHero <br> Set-AdminPowerAppApisToBypassConsent <br> Clear-AdminPowerAppApisToBypassConsent <br> Remove-AdminFlowApprovals </li></ol>
| 4.0 | 15.08.2018 | Добавлен необязательный параметр в New-AdminPowerAppCdsDatabase для синхронизации функции по умолчанию (т. е. она не вернется до успешной подготовки базы данных)
| 5.0 | 24.08.2018 | Исправлена проблема, при которой командлеты для администраторов потока не возвращали данные по использованию в зависимости от параметры безопасности

## <a name="questions"></a>Вопросы?

Если у вас есть какие-либо комментарии, предложения или вопросы, опубликуйте их на [доске сообщества администрирования PowerApps](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
