---
title: Требования к лицензии для сущностей | Microsoft Docs
description: Пояснение требований к лицензии для сущностей в Common Data Service (CDS) для приложений.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/01/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="license-requirements-for-entities"></a>Требования к лицензии для сущностей
Создатели приложений могут использовать большую часть сущностей, доступных в Common Data Service (CDS) для приложений (включая настраиваемые приложения и приложения, являющиеся частью Common Data Model) для создания приложений и потоков для пользователей, у которых имеется лицензия PowerApps, план 1, или Microsoft Flow, план 1. В некоторых случаях сущности содержат сложную бизнес-логику или связаны с приложениями Dynamics 365, для которых требуется, чтобы пользователи приложения имели конкретную лицензию. 


|Сущность    |Описание    |Требование    |
|---------|---------|---------|
|Сущности со сложной бизнес-логикой   | Существуют сущности, использующие сложную серверную бизнес-логику. Например, каждая сущность, использующая бизнес-процесс в реальном времени или подключаемый модуль кода.       |  [PowerApps, план 2](https://powerapps.microsoft.com/pricing/) или [Flow, план 2](https://flow.microsoft.com/pricing/)        |
|Ограниченные сущности  |  Это сущности, которые не стандартны с Common Data Service для приложений, но включаются в приложения Dynamics 365 Customer Engagement или решения сторонних производителей. Например, статья базы знаний, цель и сущности объема обслуживания.     |  [План Dynamics 365](https://dynamics.microsoft.com/pricing/)      | 


> [!NOTE]
> Приложение и потоки, которые используют эти сущности, требуют, чтобы у пользователя приложения или потока была соответствующая лицензия — но не у создателя или разработчика приложения или потока.

## <a name="entities-with-complex-business-logic"></a>Сущности со сложной бизнес-логикой
Сущности, которые включают следующую сложную логику на стороне сервера, требуют, чтобы у пользователей приложения или потока, которые используют эти сущности, имелась лицензия PowerApps, план 2, или лицензия Microsoft Flow, план 2:

* Подключаемые модули кода (дополнительные сведения см. в разделе [Разработка подключаемых модулей](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development))
* Бизнес-процессы в реальном времени (дополнительные сведения см. в разделе [Бизнес-процессы](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes))

    > [!NOTE]
    >  Только бизнес-процессы, преобразованные в бизнес-процесс в реальном времени, рассматриваются как процессы реального времени и синхронные. Бизнес-процессы, которые выполняются в фоновом режиме, по-прежнему могут использоваться с соответствующим планом PowerApps и не требуют дополнительных лицензий.

Чтобы узнать, добавили ли вы сложную бизнес-логику в свои сущности, проверьте список сборок подключаемых модулей и бизнес-процессов, настроенных в рабочей среде. Список сущностей, которые могут содержать логику на стороне сервера после установки приложения Dynamics 365, см. в разделе [Сложные сущности, требующие лицензии PowerApps плана 2](data-platform-complex-entities.md)  

### <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>Влияние на требования к лицензии при добавлении сложной бизнес-логики
Создатели приложений могут добавить подключаемые модули кода и бизнес-процессы в реальном времени к сущностям в CDS для приложений, однако это может изменить требования к уже лицензиям для пользователей уже развернутых приложений. Создатели приложений должны быть осторожны при добавлении сложной бизнес-логики в сущность и сначала должны проверить, какие приложения используют эту сущность и обладают ли пользователи этих приложений соответствующими лицензиями.

## <a name="restricted-entities"></a>Ограниченные сущности
Некоторые сущности, связанные в функциями приложений Dynamics 365, требуют, чтобы пользователи приложения имели соответствующую лицензию для данного приложения, если они хотят создавать, обновлять или удалять записи в этих сущностях. Полный список ограниченных сущностей см. в разделе [Ограниченные сущности, требующие лицензии Dynamics 365](data-platform-restricted-entities.md).

## <a name="licensing-examples"></a>Примеры лицензирования
Валентина и Игорь создают приложения в PowerApps с помощью CDS для приложений для хранения их данных.

Валентина создает два приложения холста:

* Приложение 1 &ndash; использует сущность "Контакт" вместе с настраиваемым объектом, в котором хранится связанная информация
* Приложение 2 &ndash; использует сущность "Контакт" вместе с сущностью "Инцидент", которая является ограниченной сущностью.

Игорь создает два приложения, управляемых моделью:

* Приложение 3 &ndash; использует сущность "Контакт" вместе с настраиваемым объектом, в котором хранится связанная информация
* Приложение 4 &ndash; использует сущность "Контакт" вместе с сущностью "Инцидент", которая является ограниченной сущностью.

Валентине и Игорю нужны следующие лицензии:
* Валентине нужна лицензия PowerApps, план 1, для создания приложений холста с помощью CDS для приложений. Если ей необходимо создать базу данных или создать настраиваемую сущность, ей будет нужна лицензия PowerApps, план 2.

* Игорю нужна лицензия PowerApps, план 2, для создания приложений, управляемых моделью.

Пользователям приложений нужны следующие лицензии:
* Пользователям приложения 1 только нужна лицензия PowerApps план 1 или план 2, так как приложение не содержит никаких записей со сложной бизнес-логикой или ограниченными сущностями.

* Пользователям приложения 2 требуется лицензия Dynamics 365 for Customer Service, Enterprise edition (план Dynamics 365 или Dynamics 365 Customer Engagement), так как приложение включает ограниченную сущность.

* Пользователям приложения 3 нужна лицензия PowerApps, план 2, так как это приложение, управляемое моделью.

* Пользователям приложения 4 требуется лицензия Dynamics 365 for Customer Service, Enterprise edition (план Dynamics 365 или Dynamics 365 Customer Engagement), так как приложение включает ограниченную сущность.

    План Dynamics 365 for Customer Service включает лицензию PowerApps, план 2, что позволит пользователям использовать приложения, управляемые моделью.

Теперь рассмотрим, что произойдет, если Игорь добавит бизнес-процесс реального времени в настраиваемую сущность, которую Валентина и Игорь используют в своих приложениях.

Валентине и Игорю нужны следующие лицензии:
* Валентине по прежнему нужна лицензия PowerApps, план 1, для создания приложений холста с помощью CDS для приложений.

* Игорю по прежнему нужна лицензия PowerApps, план 2, для создания приложений, управляемых моделью.

Пользователям приложений нужны следующие лицензии:
* Теперь пользователям приложения 1 нужна лицензия PowerApps, план 2, так как приложение содержит сущность с бизнес-процессами в реальном времени.

* Пользователям приложения 2 по прежнему требуется лицензия Dynamics 365 for Customer Service, Enterprise edition (план Dynamics 365 или Dynamics 365 Customer Engagement), так как приложение включает ограниченную сущность. 

* Пользователям приложения 3 по прежнему нужна лицензия PowerApps, план 2, так как это приложение, управляемое моделью.

* Пользователям приложения 4 по прежнему требуется лицензия Dynamics 365 for Customer Service, Enterprise edition (план Dynamics 365 или Dynamics 365 Customer Engagement), так как приложение включает ограниченную сущность.

    План Dynamics 365 for Customer Service включает лицензию PowerApps, план 2, что позволит пользователям использовать приложения, управляемые моделью.

Единственное приложение, затронутое этим изменением, это приложение 1, которое ранее требовало лицензии PowerApps, план 1, а теперь требуется лицензия PowerApps, план 2, так как оно содержит сущность со сложной бизнес-логикой. 

## <a name="more-about-licensing"></a>Дополнительные сведения о лицензировании
Дополнительные сведения о лицензиях PowerApps и Dynamics 365 см. в разделе [Обзор лицензирования](../../administrator/pricing-billing-skus.md).
