---
title: Использование клиентских скриптов с приложениями на основе модели | Документы Майкрософт
description: Узнайте, как разработчики могут использовать JavaScript в скриптах на стороне клиента и приложениях на основе модели.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/13/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 38a1a5371cbaf5d10c59a291127c13a1d00a3056
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42829406"
---
# <a name="client-scripting-with-model-driven-apps"></a>Клиентские сценарии с использованием приложений на основе модели

Скрипты на стороне клиента с использованием JavaScript — один из способов применения пользовательской логики бизнес-процессов для отображения данных в форме в приложении на основе модели, однако ему не следует отдавать предпочтение в первую очередь. *Бизнес-правила* дают возможность применять логику бизнес-процессов в форме пользователям, не знающим JavaScript и не являющимся разработчиками. Дополнительные сведения см. в статье [Dynamics 365: создание бизнес-правил и рекомендаций для применения логики в форме](/dynamics365/customer-engagement/customize/create-business-rules-recommendations-apply-logic-form).

> [!TIP]
> Конструктор бизнес-правил находится в области **Common Data Service** на сайте [powerapps.com](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Открыв сущность для просмотра, перейдите на вкладку **Бизнес-правила**.

Если бизнес-требование невозможно выполнить с помощью бизнес-правила, клиентские скрипты на основе объектной модели клиентского API могут предоставить эффективные возможности для расширения поведения приложения и обеспечения автоматизации в клиенте.

## <a name="resources"></a>Ресурсы

В руководстве по Dynamics 365 Customer Engagement для разработчиков доступны следующие ресурсы по написанию клиентских скриптов:

- [Клиентские скрипты с использованием JavaScript](/dynamics365/customer-engagement/developer/clientapi/client-scripting)
- [События в формах и сетках](/dynamics365/customer-engagement/developer/clientapi/events-forms-grids)
- [Сведения об объектной модели API клиента](/dynamics365/customer-engagement/developer/clientapi/understand-clientapi-object-model)
- [Пошаговое руководство. Написание первого клиентского сценария](/dynamics365/customer-engagement/developer/clientapi/walkthrough-write-your-first-client-script)
- [Отладка кода JavaScript](/dynamics365/customer-engagement/developer/clientapi/debug-javascript-code)
- [Рекомендации по написанию клиентских скриптов](/dynamics365/customer-engagement/developer/clientapi/client-scripting-best-practices)
- [Справочник по API клиента](/dynamics365/customer-engagement/developer/clientapi/reference)

