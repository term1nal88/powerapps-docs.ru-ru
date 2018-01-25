---
title: "Создание приложения с нуля с помощью базы данных Common Data Service | Документация Майкрософт"
description: "Узнайте, как создать приложение для добавления, обновления и удаления записей."
services: powerapps
documentationcenter: na
author: kfend
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: kfend
ms.openlocfilehash: 214b11c4f23db29d097b2d97052473d8f436d533
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
# <a name="create-an-app-from-scratch-using-a-common-data-service-database"></a>Создание приложения с нуля с помощью базы данных Common Data Service
Вы можете создать приложение для управления данными в службе Common Data Service с использованием стандартных (встроенных) или настраиваемых сущностей, а также сочетания тех и других.

При создании приложения на основе службы Common Data Service не требуется создавать подключение из Microsoft PowerApps, как в случае с источниками данных, например SharePoint, Dynamics 365 и Salesforce. Требуется только указать сущности, которые нужно показать или которыми вы собираетесь управлять в приложении.




1. Создание базы данных Common Data Service. Дополнительные сведения см. в разделе [Create a Common Data Service database](create-database.md) (Создание базы данных Common Data Service).
2. На сайте [powerapps.com](https://web.powerapps.com) на панели навигации слева щелкните или нажмите **New app** (Создать приложение).
3. В появившемся диалоговом окне щелкните или нажмите **PowerApps Studio для Web**. (Вы также можете выбрать вариант **PowerApps Studio for Windows**, а затем установить PowerApps Studio для Windows с помощью указаний. Приведенные ниже инструкции относится к веб-версии PowerApps Studio, однако инструкции для Microsoft Windows аналогичны.)
4. В разделе **Start with a blank canvas or template** (Начать с пустого холста или шаблона) щелкните или нажмите **Phone layout** (Макет для телефона) на плитке **Blank app** (Пустое приложение).
5. Если будет предложено, щелкните или нажмите **Skip** (Пропустить), чтобы пропустить учебные инструкции.
6. Откройте вкладку **Content** (Содержание).
7. Щелкните или нажмите **Data sources** (Источники данных).
8. На крайней правой панели щелкните или нажмите **Add data source** (Добавить источник данных).
9. Выберите службу Common Data Service, которую вы хотите использовать.
10. В списке сущностей установите флажок для одной или нескольких сущностей, которые вы хотите использовать, и щелкните или нажмите **Connect** (Подключиться).

Указанные вами сущности появятся в списке источников данных, и вы сможете приступить к созданию приложения, как описано в разделе [Создание приложения с нуля](get-started-create-from-blank.md).

