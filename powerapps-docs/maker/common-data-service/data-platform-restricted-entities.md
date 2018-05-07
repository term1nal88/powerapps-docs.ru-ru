---
title: Ограниченные сущности, для которых требуются лицензии Dynamics 365 | Документы Майкрософт
description: Список ограниченных сущностей в Common Data Service for Apps, для которых требуются лицензии Dynamics 365.
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: cds
ms.date: 05/01/2018
ms.author: clwesene
ms.openlocfilehash: 508f58b48f2dd51bf25f23905cc3513db90ed1ce
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="restricted-entities-requiring-dynamics-365-licenses"></a>Ограниченные сущности, для которых требуются лицензии Dynamics 365
Создатели приложений могут использовать большую часть сущностей, доступных в службе Common Data Service (CDS) for Apps, для создания приложений и потоков для пользователей, имеющих только лицензию PowerApps (план 1). Однако некоторые сущности содержат сложную бизнес-логику, для реализации которой пользователям приложений необходима лицензия PowerApps (план 2) или лицензия Microsoft Flow (план 2) (дополнительные сведения см. в статье о [требованиях к лицензиям для сущностей](data-platform-entity-licenses.md)). Даже для работы с небольшим набором сущностей, привязанных к продуктам Dynamics 365, пользователи приложений на основе холста и на основе моделей должны иметь лицензию на соответствующий продукт Dynamics 365, если они собираются создавать, обновлять или удалять записи в сущностях. Такие сущности называются *ограниченными*.

Сущности могут быть ограничены лицензиями Dynamics 365 по следующим причинам.

* Сущность используется для хранения и поддержки данных конфигурации конкретного продукта, которые обычно не используются вне приложения.
* Сущность имеет расширенную логику, которая при использовании в составе продукта Dynamics 365 определенным образом создает и поддерживает данные.

Если приложение или поток только считывает данные из сущности, лицензия Dynamics 365 не требуется — нужна только соответствующая лицензия PowerApps или Microsoft Flow. 

## <a name="restricted-entities-for-create-update-and-delete-operations"></a>Ограниченные сущности для операций создания, обновления и удаления
В следующей таблице перечислены ограниченные сущности и связанные требования к лицензиям Dynamics 365 для пользователей приложений PowerApps и Microsoft Flow, которые создают, обновляют или удаляют данные, хранящиеся в сущностях. 

|Учреждение  |Логическое имя  |Необходимая лицензия  |
|---------|---------|---------|
Фактическая |msdyn_actual |Dynamics 365 for Field Service <br> **или** Dynamics 365 for Project Service Automation,<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Бизнес-процесс "Договор" |msdyn_bpf_baa0a411a239410cb8bded8b5fdd88e3 |Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Журнал резервирования | msdyn_bookingjournal|Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Метаданные настройки резервирования | msdyn_bookingsetupmetadata|Dynamics 365 for Field Service <br> **или** Dynamics 365 for Project Service Automation,<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Метка времени резервирования | msdyn_bookingtimestamp|Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Бизнес-процесс "Обращение по заказу на работу " |msdyn_bpf_989e9b1857e24af18787d5143b67523b |Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Настройка |msdyn_configuration |Dynamics 365 for Field Service <br> **или** Dynamics 365 for Project Service Automation,<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Объем обслуживания | entitlement | Dynamics 365 for Customer Service (корпоративный выпуск); <br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Строка оценки|msdyn_estimateline|Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Оценка|msdyn_estimate |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Факт|msdyn_fact |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Настройка обслуживания |msdyn_fieldservicesetting |Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Системное задание "Обслуживание" |msdyn_fieldservicesystemjob |Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Цель | goal | Dynamics 365 for Sales Professional <br>**или**  Dynamics 365 for Sales (корпоративный выпуск), <br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Инцидент | incident | Dynamics 365 for Customer Service (корпоративный выпуск); <br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Журнал запасов |msdyn_inventoryjournal |Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Процесс обработки счета |msdyn_bpf_d8f9dc7f099f44db9d641dd81fbd470d |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Взаимодействие | journey | Dynamics 365 for Marketing <br> **или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Статья базы знаний | knowledgearticle | Dynamics 365 for Customer Service (корпоративный выпуск); <br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Подразделение |msdyn_organizationalunit |Dynamics 365 for Field Service <br> **или** Dynamics 365 for Project Service Automation,<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Запасы продуктов |msdyn_productinventory |Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Параметр проекта|msdyn_projectparameter |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Стадии проекта| msdyn_bpf_665e73aa18c247d886bfc50499c73b82|Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Зависимость задач проекта|msdyn_projecttaskdependency |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Задача проекта|msdyn_projecttask |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Участник проектной группы|msdyn_projecteam |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Бизнес-процесс "Заказ на покупку" | msdyn_bpf_2c5fe86acc8b414b8322ae571000c799|Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Сведения о назначении ресурса (устарело)|msdyn_resourceassignmentdetail |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Назначение ресурса|msdyn_resourceassignment |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Ограничения ресурса (устарело) |msdyn_workorderresourcerestriction | Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Набор правил маршрутизации | routingrule | Dynamics 365 for Customer Service (корпоративный выпуск); <br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Настройка таблицы расписаний |msdyn_scheduleboardsetting |Dynamics 365 for Field Service <br> **или** Dynamics 365 for Project Service Automation,<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Параметр планирования |msdyn_schedulingparameter |Dynamics 365 for Field Service <br> **или** Dynamics 365 for Project Service Automation,<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Соглашение об уровне обслуживания| sla | Dynamics 365 for Customer Service (корпоративный выпуск); <br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Настройка планировщика системного пользователя |msdyn_systemuserschedulersetting|Dynamics 365 for Field Service <br> **или** Dynamics 365 for Project Service Automation,<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Подключение проводки|msdyn_transactionconnection |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Происхождение проводки|msdyn_transactionorigin |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Тип проводки|msdyn_transactiontype |Dynamics 365 for Project Service Automation<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Уникальный номер|msdyn_uniquenumber |Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Бизнес-процесс "Заказ на работу" |msdyn_bpf_d3d97bac8c294105840e99e37a9d1c39 |Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365
Очередь создания сведений о заказе на работу (устарело)|msdyn_workorderdetailsgenerationqueue |Dynamics 365 for Field Service<br>**или** план Dynamics 365 Customer Engagement, <br> **или** план Dynamics 365

## <a name="licensing"></a>Лицензирование
Дополнительные сведения о лицензиях PowerApps и Dynamics 365 см. на странице [Общие сведения о лицензировании](../../administrator/pricing-billing-skus.md).

