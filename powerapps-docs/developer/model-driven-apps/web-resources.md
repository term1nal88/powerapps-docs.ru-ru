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
ms.openlocfilehash: 56e994929036cc713e7bf7dfc04f46bf991a3530
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="use-web-resources"></a>Использование веб-ресурсов

В каждом экземпляре Common Data Service for Apps присутствует виртуальная папка `webresources`, где можно запросить файлы HTML, JS, CSS, изображений и другие файлы по имени и получить к ним доступ в браузере. Вы можете отправить эти файлы с помощью приложения или программно добавить их в виде записей [сущности WebResource](../common-data-service/reference/entities/webresource.md). [XrmToolBox WebResources Manager](https://www.xrmtoolbox.com/plugins/MsCrmTools.WebResourcesManager/) — это средство сообщества, упрощающее работу с этими записями.

Эти записи могут ссылаться друг на друга с помощью имен относительных путей в их содержимом. Эта возможность отправлять файлы и запрашивать их по имени предоставляет все стандартные блоки, которые нужны для создания веб-приложений, использующих файлы, которые обрабатываются в прошедшем проверку подлинности сеансе браузера. Используя лишь код на стороне клиента с помощью методик AJAX, вы можете создавать многофункциональные приложения, способные выполняться в окне браузера или в плавающем фрейме на форме или панели мониторинга. 

Чаще всего JavaScript вы будете использовать веб-ресурсы JavaScript для добавления функций обработчика событий на формы и в команды.

Дополнительные сведения:
- [Клиентские сценарии с использованием приложений на основе модели](client-scripting.md)
- [Руководство по Dynamics 365 Customer Engagement для разработчика: веб-ресурсы](/dynamics365/customer-engagement/developer/web-resources)
