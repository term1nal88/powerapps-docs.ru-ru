---
title: "Делегируемые источники данных | Документация Майкрософт"
description: "Список всех поддерживаемых делегируемых источников данных"
services: 
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/15/2017
ms.author: archanan
ms.openlocfilehash: 94e4eaa5209bbcaf6cd191ed2dfdf27d9eab1d5f
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="delegable-data-sources"></a>Делегируемые источники данных
Как подробно описано в статье с [основными сведениями о делегировании](delegation-overview.md), делегирование — это передача службой PowerApps обязанностей по обработке данных источнику вместо переноса данных в приложение для локальной обработки.

Делегирование поддерживается только для табличных источников данных. В этом списке перечислены табличные источники данных и указано, поддерживают ли они делегирование. Подробные сведения приведены в следующем разделе.

* Common Data Service — **да**
* SharePoint — **да**
* SQL Server — **да**
* Dynamics 365 — **да**
* Salesforce — **да**
* Excel — **ожидается в ближайшее время**
* Dynamics 365 for Operations — пока нет
* Dynamics 365 for Financials — пока нет
* Dynamics NAV — пока нет
* Google Таблицы — пока нет

Мы постоянно добавляем новые табличные источники данных и расширяем поддержку делегирования.

В этом документе указан текущий статус поддержки делегирования для каждого источника.

**Предварительные требования**

* Ознакомьтесь со статьей с [основными сведениями о делегировании](delegation-overview.md).

## <a name="list-of-data-sources-and-supported-delegation"></a>Список источников данных и сведения о поддержке делегирования
Этот список источников данных, делегируемых функций и предикатов периодически обновляется с учетом изменений в поддержке делегирования в PowerApps.

### <a name="top-level-delegable-functions"></a>Делегируемые функции верхнего уровня
| &nbsp; | Common Data Service | SharePoint | SQL Server | Dynamics 365. | Salesforce |
| --- | --- | --- | --- | --- | --- |
| Average |Нет |Нет |Да |Нет |Нет |
| Фильтр |Да |Да |Да |Да |Да |
| LookUp |Да |Да |Да |Да |Да |
| Максимальное количество |Нет |Нет |Да |Нет |Нет |
| Min |Нет |Нет |Да |Нет |Нет |
| Поиск |Да <sup>1</sup> |Нет |Да |Да |Да |
| Сортировать |Да |Да |Да |Да |Да |
| SortByColumns |Да |Да |Да |Да |Да |
| Sum |Нет |Нет |Да |Нет |Нет |

<sup>1</sup> Только для строковых полей

### <a name="filter-and-lookup-delegable-predicates"></a>Делегируемые предикаты Filter и LookUp
| &nbsp; | Common Data Service | SharePoint | SQL Server | Dynamics 365. | Salesforce |
| --- | --- | --- | --- | --- | --- |
| Not |Да |Нет |Да |Да |Да |
| IsBlank |Нет |Нет |Да |Да |Нет |
| TrimEnds |Нет |Нет |Да |Нет |Нет |
| Len |Нет |Нет |Да |Нет |Нет |
| +, - |Нет |Нет |Да |Нет |Нет |
| <, <=, =, <>, >, >= |Да |Да (только =) |Да |Да |Да |
| And (&&), Or (&#124;&#124;), Not (!) |Да <sup>2</sup> |Да (кроме Not(!)) |Да |Да |Да |
| in |Нет |Нет |Да |Нет |Да |
| StartsWith |Нет |Да |Нет |Нет |Нет |

<sup>2</sup> Только для операторов. Функции And/Or/Not не делегируются.

