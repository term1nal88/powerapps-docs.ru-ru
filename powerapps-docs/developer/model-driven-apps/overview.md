---
title: 'Приложения на основе модели: общие сведения для разработчиков | Документы Майкрософт'
description: Сведения о том, как разработчики могут повышать ценность приложений на основе модели.
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
ms.openlocfilehash: 4e8a935dbef2c46478f99ecbf82a7fc837feb284
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="model-driven-apps-developer-overview"></a>Приложения на основе модели: общие сведения для разработчиков

PowerApps предоставляет пользователям, организациям, партнерам, независимым поставщикам программного обеспечения и системным интеграторам эффективную платформу для создания бизнес-приложений. Новым дополнением к PowerApps в этом выпуске стали приложения на основе модели, создаваемые с помощью новой Common Data Service for Apps. Теперь Common Data Service for Apps содержит основные функциональные возможности приложений Dynamics 365 Customer Engagement. Благодаря поддержке приложений на основе модели можно создавать приложения, использующие те же возможности расширяемости, что и эти приложения.

По сути, приложения на основе модели представляют собой это бескодовый или малокодовый и ориентированный на компоненты подход к разработке приложений. Разработчики могут добиться повышения ценности решения за счет расширения приложения. Прежде чем приступить к написанию кода, изучите, как происходит создание приложения на основе модели и какие функции можно применить без кода. 

## <a name="get-started"></a>Начало работы
Если у вас уже есть опыт работы с приложениями Dynamics 365 Customer Engagement, он пригодится и при создании приложений на основе модели. Появились некоторые новые конструкторы, но общие концепции остались прежними.

> [!NOTE]
> Приложения на основе модели подключаются к службе Common Data Service for Apps. Сведения о том, как разработчики могут повышать ценность на уровне обслуживания, см. в разделе [Common Data Service for Apps: общие сведения для разработчиков](../common-data-service/overview.md).
> Материал этого раздела касается только расширений, которые могут создать разработчики и которые влияют на работу пользователей в приложениях на основе модели. 

Если вы впервые сталкиваетесь с приложениями Dynamics 365 Customer Engagement, в этом разделе вы сможете кратко познакомиться с основными понятиями, помогающие разработчикам приступить к работе с приложениями на основе модели. 

> [!NOTE]
> Так как Common Data Service for Apps и Dynamics 365 Customer Engagement используют одну платформу, более полные сведения для разработчиков можно найти в [руководстве по Dynamics 365 Customer Engagement для разработчиков](/dynamics365/customer-engagement/developer/developer-guide). Эти разделы содержат ссылки на руководство для разработчиков и другие руководства.


## <a name="community-tools-for-model-driven-apps"></a>Средства сообщества для приложений на основе модели

Сообщество Dynamics 365 создает средства. Многие из самых популярных распространяются посредством [XrmToolBox](https://www.xrmtoolbox.com/). XrmToolBox — это приложение Windows, который подключается к Common Data Service for Apps и предоставляет средства, упрощающие настройку, конфигурацию и работу. Оно поставляется вместе с более чем 30 подключаемыми модулями, которые облегчают и ускоряют администрирование, настройку и конфигурацию.

Ниже приведен список отобранных средств сообщества, распространяемых посредством XrmToolBox, которые можно использовать при работе с приложениями на основе модели.

|Средство  |Описание  |
|---------|---------|
|[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/)|Экспортирует и импортирует переводы с контекстной информацией.|
|[Export to Excel](https://www.xrmtoolbox.com/plugins/Ryr.XrmToolBox.ExportToExcel/)|Позволяет легко экспортировать записи из выбранного представления/FetchXML в Excel.|
|[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)|Позволяет управлять значками настраиваемых сущностей на одном экране.|
|[Ribbon Workbench 2016](https://www.xrmtoolbox.com/plugins/RibbonWorkbench2016/)|Позволяет изменять ленту Dynamics CRM или панель команд из XrmToolbox.|
|[View Designer](https://www.xrmtoolbox.com/plugins/Cinteros.XrmToolBox.ViewDesigner/)|Удобный пользовательский интерфейс для разработки макетов представлений и изменения запросов с помощью FetchXML Builder.|
|[View Layout Replicator](https://www.xrmtoolbox.com/plugins/MsCrmTools.ViewLayoutReplicator/)|Позволяет применить один макет к нескольким представлениям одной сущности в отдельной операции.|
|[WebResources Manager](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/)|Упрощает управление веб-ресурсами.|

Еще одним средством, не распространяемым посредством XrmToolBox, является [CRM REST Builder](https://github.com/jlattimer/CRMRESTBuilder) от Джейсона Латтимера (Jason Lattimer). Это средство создает код JavaScript для использования с веб-API.

> [!NOTE]
> Средства, созданные сообществом, не поддерживаются корпорацией Майкрософт. Если у вас появились проблемы или вопросы, связанные со средствами сообщества, обратитесь к издателю средства.




