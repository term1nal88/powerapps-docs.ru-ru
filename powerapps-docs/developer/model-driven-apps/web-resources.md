---
title: Использование веб-ресурсов | Документы Майкрософт
description: Сведения о том, как разработчики могут использовать веб-ресурсы в приложениях на основе модели.
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
ms.openlocfilehash: 88e51e4547732bed2d3e7ef3290bc8d933afded3
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849918"
---
# <a name="use-web-resources"></a>Использование веб-ресурсов

В каждом экземпляре Common Data Service for Apps присутствует виртуальная папка `webresources`, где можно запросить файлы HTML, JS, CSS, изображений и другие файлы по имени и получить к ним доступ в браузере. Вы можете отправить эти файлы с помощью приложения или программно добавить их в виде записей [сущности WebResource](../common-data-service/reference/entities/webresource.md). [XrmToolBox WebResources Manager](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/) — это средство сообщества, упрощающее работу с этими записями.

Эти записи могут ссылаться друг на друга с помощью имен относительных путей в их содержимом. Эта возможность отправлять файлы и запрашивать их по имени предоставляет все стандартные блоки, которые нужны для создания веб-приложений, использующих файлы, которые обрабатываются в прошедшем проверку подлинности сеансе браузера. Используя лишь код на стороне клиента с помощью методик AJAX, вы можете создавать многофункциональные приложения, способные выполняться в окне браузера или в плавающем фрейме на форме или панели мониторинга. 

Чаще всего JavaScript вы будете использовать веб-ресурсы JavaScript для добавления функций обработчика событий на формы и в команды.

Дополнительные сведения:
- [Клиентские сценарии с использованием приложений на основе модели](client-scripting.md)
- [Руководство по Dynamics 365 Customer Engagement для разработчика: веб-ресурсы](/dynamics365/customer-engagement/developer/web-resources)
