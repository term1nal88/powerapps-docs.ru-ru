---
title: Устранение неполадок в Power Query | Документы Microsoft
description: Устранение проблем при использовании Power Query для создания настраиваемой сущности в Common Data Service для приложений
services: ''
suite: powerapps
documentationcenter: na
author: mllopis
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/18/2017
ms.author: millopis
ms.openlocfilehash: dafed76565a4bd3fb3e2822319d344f49376b4fc
ms.sourcegitcommit: aa2d0166dccb38100183c093f293233b46f3669d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2018
---
# <a name="troubleshooting-power-query"></a>Устранение неполадок в Power Query
При использовании Power Query для создания настраиваемой сущности, содержащей данные из внешних источников, может возникать следующая ошибка.

`Your Azure Active Directory administrator has set a policy that prevents you from using this feature. Please contact your administrator, who can grant permissions for this feature on your behalf.`

Ошибка возникает в случае, когда Power Query не может получить доступ к данным организации в PowerApps или Common Data Service. Эта ситуация возникает в одном из двух случаев.

* Администратор клиента Azure Active Directory (AAD) запретил пользователям предоставлять разрешение приложениям, которые обращаются к данным компании от своего имени.
* Использование неуправляемого клиента Active Directory. Неуправляемый клиент представляет собой каталог без глобального администратора, который был создан для самостоятельной регистрации. Чтобы предотвратить такое развитие событий, пользователи должны сначала преобразовать каталог в управляемый клиент, а затем применить одно из двух решений этой проблемы, описанных в следующем разделе.

Чтобы устранить эту проблему, администратор AAD должен выполнить действия одной из процедур, описанных ниже в этом разделе.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>Разрешить пользователям давать разрешения приложениям на доступ к данным компании
Возможно, это самый простой способ, но он предоставляет более широкие права.

1. На портале [https://portal.azure.com](https://portal.azure.com)откройте колонку **Azure Active Directory** и выберите **Параметры пользователя**.
1. Выберите значение **Да** рядом с параметром **Пользователи могут разрешать приложениям доступ к корпоративным данным от своего имени**, а затем нажмите кнопку **Сохранить**.

## <a name="allow-power-query-to-access-company-data"></a>Предоставление Power Query доступа к данным компании
В качестве альтернативного решения администратор клиента может дать Power Query разрешение на доступ без изменения разрешений на уровне клиента.

1. Установить [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps).
2. Выполнить следующие команды PowerShell:
   * Login-AzureRmAccount (а затем войти как администратор клиента);
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128.

Этот подход по сравнению с изменением разрешений в масштабах клиента является более целенаправленным. Он подготавливает только субъект-службу **Power Query**, но не изменяет другие разрешения в клиенте.

