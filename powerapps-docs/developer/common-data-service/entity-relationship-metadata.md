---
title: Метаданные отношений элементов | Документы Майкрософт
description: Сведения об использовании метаданных отношений элементов в Common Data Service for Apps.
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
ms.date: 03/12/2018
ms.author: jdaly
ms.openlocfilehash: da8899151fdb40713d19ca1cb82444a486526549
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="entity-relationship-metadata"></a>Метаданные отношений элементов

Просматривая обозреватель решений или коллекции связей `EntityMetadata`, может показаться, что существует три типа отношений элементов. На самом деле их всего два, как показано в следующей таблице.

|Тип отношения|Описание|
|--|--|
|Один ко многим<br />[OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata)|Отношение элементов, где одну запись сущности для **основной сущности** можно связать с несколькими другими записями **связанной сущности** с помощью поля подстановки в связанной сущности.<br />При просмотре записи основной сущности можно просмотреть список связанных с ней записей связанной сущности.|
|Многие ко многим<br />[ManyToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.manytomanyrelationshipmetadata)|Отношение элементов, которое зависит от специальной *сущности отношения*, которую иногда называют *пересекающейся* сущностью, так как она позволяет связать множество записей одной сущности с множеством записей другой сущности.<br />При просмотре записей любой из сущностей в связи "многие ко многим" можно просмотреть список любых связанных с ней записей другой сущности.|

Коллекция `EntityMetadata` `ManyToOneRelationships` содержит типы [OneToManyRelationshipMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.onetomanyrelationshipmetadata). Связи "один ко многим" существуют между сущностями и ссылаются на каждую из них как на *основную сущность* или *связанную сущность*. Связанная сущность, которую иногда называют *дочерней*, имеет атрибут поиска, который позволяет хранить ссылку на запись из основной сущности, которая иногда называется *родительской сущностью*. Связь "многие к одному" является просто связью "один ко многим", просматриваемой из связанной сущности.

> [!NOTE]
> Хотя связанные сущности иногда называют *дочерними*, не следует путать их с [дочерними сущностями](entity-metadata.md#child-entities), указывающими порядок применения мер безопасности к связанным сущностям.

Дополнительные сведения:
- [Руководство по настройке Dynamics 365 Customer Engagement. Создание и изменение отношений между элементами](/dynamics365/customer-engagement/customize/create-edit-entity-relationships)
- [Руководство по Dynamics 365 Customer Engagement для разработчика. Настройка метаданных отношений элементов](/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

## <a name="cascade-configuration"></a>Конфигурация каскада

Когда существует отношение элементов "один ко многим", доступны режимы каскадирования, которые можно настроить для обеспечения целостности данных и автоматизации бизнес-процессов.

Дополнительные сведения:

- [Руководство по настройке Dynamics 365 Customer Engagement. Создание связей 1:N (один ко многим) или N:1 (многие к одному) > поведение отношения](/dynamics365/customer-engagement/customize/create-and-edit-1n-relationships#relationship-behavior)
- [Руководство по Dynamics 365 Customer Engagement для разработчика. Поведение отношения элементов](/dynamics365/customer-engagement/developer/entity-relationship-behavior)


## <a name="create-a-hierarchy-of-entities"></a>Создание иерархии сущностей

В рамках ссылающейся на себя связи "один ко многим" можно установить иерархию, задав для свойства `IsHierarchical` значение `true`.

Благодаря приложениям на основе модели можно просмотреть эту иерархию и взаимодействовать с ней. 

Разработчикам это позволяет использовать новые типы запросов, основанные на иерархии, с помощью операторов `Under` и `Not Under`.

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Запрос и визуализация данных, связанных по иерархии](/dynamics365/customer-engagement/customize/query-visualize-hierarchical-data).

### <a name="see-also"></a>См. также

[Сущности в Common Data Service for Apps](entities.md)