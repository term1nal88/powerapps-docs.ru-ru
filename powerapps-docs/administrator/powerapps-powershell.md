---
title: Поддержка PowerShell (предварительная версия) | Документация Майкрософт
description: Описание различных командлетов PowerShell и пошаговое руководство по их установке и запуску.
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: reference
ms.date: 04/23/2018
ms.author: jamesol
ms.openlocfilehash: 953efbabcdce55ac58376f927d5e399e69a40974
ms.sourcegitcommit: b3b6118790d6b7b4285dbcb5736e55f6e450125c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2018
---
# <a name="powershell-support-for-powerapps-preview"></a>Поддержка PowerShell в PowerApps (предварительная версия)
С помощью предварительной версии командлетов PowerShell для создателей и администраторов приложений вы можете автоматизировать многие задачи мониторинга и управления, которые раньше выполнялись только вручную в [PowerApps](https://web.powerapps.com) или [центре администрирования PowerApps](https://admin.powerapps.com).

## <a name="installation"></a>Установка
Прежде чем выполнять командлеты PowerShell для создателей приложений, сделайте следующее:

1. Скачайте [файл сценариев PowerShell](https://go.microsoft.com/fwlink/?linkid=872358).

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

6. Прежде чем обращаться к любой из команд, укажите свои учетные данные, используя команду ниже. Эти учетные данные обновляются максимум за 8 часов, прежде чем вам потребуется снова войти в систему, чтобы продолжить использование командлетов.

    ```
    Add-PowerAppsAccount
    ```

7.  Существует [известная проблема](https://powerusers.microsoft.com/t5/Administering-PowerApps/Getting-errors-when-I-try-to-import-the-preview-powerapps/td-p/109036), из-за которой может потребоваться ручная разблокировка файлов PowerShell с помощью следующей команды:

    ```
    dir . | Unblock-File
    ```

## <a name="powerapps-cmdlets-for-app-makers-preview"></a>Командлеты PowerApps для разработчиков приложений (предварительная версия)

### <a name="prerequisite"></a>Необходимое условие
Пользователи с действующей лицензией PowerApps могут выполнять операции в этих командлетах. При этом они будут иметь доступ только к ресурсам (например, приложениям, потокам и т. д.), которые были созданы или предоставлены им для общего доступа.

### <a name="cmdlet-list"></a>Список командлетов
| Цель | Командлет |
| --- | --- |
| Чтение сред | Get-PowerAppsEnvironment <br> Get-FlowEnvironment
| Чтение, обновление и удаление приложения на основе холста | Get-App <br> Remove-App <br> Publish-App <br> Set-AppDisplayName <br> Get-AppVersion <br> Restore-AppVersion
| Чтение, обновление и удаление разрешений приложений на основе холста | Get-AppRoleAssignment <br> Set-AppRoleAssignment <br> Remove-AppRoleAssignment
| Read, update, and delete a flow | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow
| Чтение, обновление и удаление разрешений потоков | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole
| Чтение и ответ на утверждения потоков | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest
| Чтение и удаление соединений | Get-Connection <br> Remove-Connection
| Чтение, обновление и удаление разрешений соединений | Get-ConnectionRoleAssignment <br> Set-ConnectionRoleAssignment <br> Remove-ConnectionRoleAssignment
| Чтение и удаление соединителей | Get-Connector <br> Remove-Connector
| Чтение, обновление и удаление пользовательских разрешений соединителей | Get-ConnectorRoleAssignment <br> Set-ConnectorRoleAssignment <br> Remove-ConnectorRoleAssignment

> [!NOTE]
> Следующие команды позволяют понять синтаксис и просмотреть примеры каждого из командлетов:
>```
>Get-Help Get-PowerAppsEnvironment
>Get-Help Get-PowerAppsEnvironment -Examples
>Get-Help Get-PowerAppsEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>Командлеты PowerApps для администраторов (предварительная версия)

### <a name="prerequisite"></a>Необходимое условие
Чтобы выполнить операции администрирования в командлетах администратора, понадобится следующее:

* Платная лицензия PowerApps (план 2) или лицензия на пробную версию PowerApps (план 2). Вы можете зарегистрироваться для бесплатного использования 30-дневной пробной лицензии здесь: [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Лицензии на пробную версию можно продлить по истечении их срока действия.

* Права [глобального администратора Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) или [глобального администратора Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), если вам нужно выполнить поиск по ресурсам другого пользователя. (Помните, что администраторы среды имеют доступ только к тем средам и ресурсам среды, на которые у них есть разрешения.)

### <a name="cmdlet-list"></a>Список командлетов
| Цель | Командлеты
| --- | ---
| Чтение и удаление сред | Get-AdminEnvironment <br> Remove-AdminEnvironment
| Чтение, обновление и удаление разрешений среды <br><br> *Эти командлеты работают только в средах, в которых нет базы данных Common Data Service (CDS) для приложений.* | Get-AdminEnvironmentRoleAssignment <br> Set-AdminEnvironmentRoleAssignment <br> Remove-AdminEnvironmentRoleAssignment
| Чтение и удаление приложений на основе холста | Get-AdminApp <br> Remove-AdminApp
| Чтение, обновление и удаление разрешений приложений на основе холста | Get-AdminAppRoleAssignment <br> Remove-AdminAppRoleAssignment <br> Set-AdminAppRoleAssignment <br> Set-AdminAppOwner
| Чтение, обновление и удаление потоков | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow  <br> Remove-AdminFlowOwnerRole

> [!NOTE]
> Следующие команды позволяют понять синтаксис и просмотреть примеры каждого из командлетов:
>```
>Get-Help Get-AdminEnvironment
>Get-Help Get-AdminEnvironment -Examples
>Get-Help Get-AdminEnvironment -Detailed
>```

## <a name="questions"></a>Вопросы?

Если у вас есть какие-либо комментарии, предложения или вопросы, опубликуйте их на [доске сообщества администрирования PowerApps](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
