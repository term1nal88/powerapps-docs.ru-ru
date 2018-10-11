---
title: Просмотр и скачивание ресурсов для разработчиков | Документы Майкрософт
description: Поиск ресурсов для разработчиков и URL-адресов конечных точек службы
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e200d242-ff3f-48e5-af32-aed050e02441
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.openlocfilehash: ae93b57d9ead3a62fb538ae986eb524367259545
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39704123"
---
<!-- TODO: The Developer Resources page have to be updated to match this page -->

# <a name="view-or-download-developer-resources"></a>Просмотр и скачивание ресурсов для разработчиков

На этой странице приведены ресурсы для разработчиков и сведения о конкретном экземпляре, с которым вы работаете. 

## <a name="view-the-developer-resources-page-for-your-environment"></a>Просмотр страницы "Ресурсы для разработчиков" для вашей среды

1. На портале PowerApps нажмите кнопку ![Параметры](../../administrator/media/settings-button-nav-bar.png) и выберите **Дополнительные настройки**.

    ![Дополнительные настройки](media/advanced-customizations-menu.png)

1. На панели **Дополнительные настройки** щелкните ссылку **Ресурсы для разработчиков**:<br />![Ссылка "Ресурсы для разработчиков"](media/developer-resources-link.png)

## <a name="getting-started"></a>Начало работы 

Этот раздел содержит ссылки на ресурсы для разработчиков. Доступны следующие ресурсы:


|Ссылка |Описание|
|---------|---------|
|[Центр разработчиков](https://go.microsoft.com/fwlink/?LinkId=551006)|Основной ресурс с документацией для разработчиков.|
|[Форумы разработчиков](https://go.microsoft.com/fwlink/?LinkId=550993)|Задавайте вопросы другим разработчикам и отвечайте на их вопросы.|
|[Пакеты NuGet](https://go.microsoft.com/fwlink/?LinkId=550994)|Используйте пакеты NuGet, чтобы добавлять сборки пакетов SDK в свои проекты.|
|[Инструменты для скачивания](https://go.microsoft.com/fwlink/?LinkID=512122)|Необходимые инструменты доступны для скачивания в пакетах NuGet. Для скачивания последних версий используйте сценарий PowerShell на этой странице.|
|[Пример кода](https://go.microsoft.com/fwlink/?LinkId=553007)|Список доступных примеров.|
|[Обзор для разработчиков](https://go.microsoft.com/fwlink/?LinkId=550995)|Ссылку на раздел, предоставляющий обзор для разработчиков.|

<!-- TODO update 512122 to go to https://docs.microsoft.com/dynamics365/customer-engagement/developer/download-tools-nuget -->


## <a name="connect-your-apps-to-this-instance-of-common-data-service-for-apps"></a>Подключите свои приложения к этому экземпляру службы Common Data Service for Apps.

Этот раздел содержит сведения, необходимые для подключения к вашему экземпляру Common Data Service for Apps.

### <a name="instance-web-api"></a>Веб-API экземпляра

URL-адрес веб-API вашего экземпляра. Веб-API представляет собой API OData версии 4 с поддержкой REST. Вы также можете скачать сервисный документ с описанием метаданных и операций, которые доступны в вашем экземпляре. Дополнительные сведения см. в разделе [Документация для разработчиков. Использование веб-API Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api).

### <a name="organization-service"></a>Служба организации

Это URL-адрес для конечной точки SOAP службы организации для вашего экземпляра.
Здесь вы можете скачать WSDL для этой службы, но для создания классов сущностей для проектов .NET используется средство создания кода CrmSvcUtil.exe. Дополнительные сведения: 
- [Документация для разработчиков. Создание классов сущностей с упреждающей привязкой с помощью средства создания кода (CrmSvcUtil.exe)](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)
- [Документация для разработчиков. Использование службы организации для чтения и записи данных или метаданных](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)

### <a name="instance-reference-information"></a>Справочные сведения об экземплярах

Эта информация однозначно описывает ваш экземпляр. Она содержит **идентификатор GUID** и **уникальное имя**.
Эти сведения необходимы при использовании расширений Azure для вашего экземпляра.
Дополнительные сведения см. в разделе [Документация для разработчиков. Расширения Azure для Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions).

## <a name="connect-your-apps-to-the-common-data-service-for-apps-discovery-service"></a>Подключите свои приложения к службе обнаружения Common Data Service for Apps

Так как у пользователей может быть доступ к нескольким средам CDS for Apps, службы обнаружения позволяют получить доступные среды, к которым есть доступ у пользователя, на основе учетных данных пользователя.

### <a name="discovery-web-api"></a>Веб-API обнаружения

Это адрес конечной точки OData версии 4 с поддержкой REST службы обнаружения для вашего экземпляра. Вы также можете скачать сервисный документ здесь.
Дополнительные сведения см. в разделе [Документация для разработчиков. Обнаружение URL-адреса вашей организации с помощью веб-API](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api).


### <a name="discovery-service"></a>Служба обнаружения

Это адрес конечной точки версии SOAP службы обнаружения, используемой для вашего экземпляра. Вы также можете скачать сервисный документ здесь.
Дополнительные сведения см. в разделе [Документация для разработчиков. Обнаружение URL-адреса вашей организации с помощью службы обнаружения](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service).
  
### <a name="more-information"></a>Дополнительные сведения

[Документация для разработчиков. Страница "Ресурсы для разработчиков"](/dynamics365/customer-engagement/developer/developer-resources-page)<br />
[Документация для разработчиков. Использование веб-API Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-web-api)<br />
[Документация для разработчиков. Использование службы организации для чтения и записи данных или метаданных](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata)<br />
[Документация для разработчиков. Расширения Azure для Dynamics 365 Customer Engagement](/dynamics365/customer-engagement/developer/azure-extensions)<br />
[Документация для разработчиков. Обнаружение URL-адреса вашей организации с помощью веб-API](/dynamics365/customer-engagement/developer/webapi/discover-url-organization-web-api)<br />
[Документация для разработчиков. Обнаружение URL-адреса вашей организации с помощью службы обнаружения](/dynamics365/customer-engagement/developer/org-service/discover-url-organization-organization-service)
  

