---
title: Настройка команд с помощью приложений на основе модели | Документы Майкрософт
description: Сведения о настройке команд с помощью приложений на основе модели.
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
ms.date: 03/17/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 4721ba49fe227d31f539eabd863b50842e7515b6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42836261"
---
# <a name="customize-commands-with-model-driven-apps"></a>Настройка команд с помощью приложений на основе модели 

Команды, отображаемые на панели команд формы или списка, можно настроить. Команды основаны на схемах XML, используемых на лентах Office, поэтому термин *лента* по-прежнему используется. При создании команды можно определить три элемента:

- *Правила отображения* вычисляются при загрузке формы или списка и определяют, отображается ли команда или группа команд.
- *Правила включения* определяют, включена ли команда, с учетом различных условий, таких как выбранный элемент в пользовательском интерфейсе.
- *Действие* для каждой команды, сообщающее о том, что нужно сделать при ее выборе. Команда может открывать URL-адрес или выполнять функцию, определенную в веб-ресурсе JavaScript.

Настраиваемые команды задаются на основе уже существующих. Нужно составить *настраиваемое действие*, определяющее, какие изменения применяются для существующего набора команд. 

Конструктор для команд отсутствует. К счастью, необходимые средства предоставлены сообществом. [Ribbon Workbench](http://www.develop1.net/public/rwb/ribbonworkbench.aspx) имеет графический интерфейс и чаще всего используется для настройки команд.

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Настройка команд и ленты](/dynamics365/customer-engagement/developer/customize-dev/customize-commands-ribbon).


