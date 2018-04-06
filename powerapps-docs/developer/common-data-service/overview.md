---
title: 'Common Data Service for Apps: общие сведения для разработчиков | Документы Майкрософт'
description: Сведения о том, как разработчики могут использовать Common Data Service for Apps.
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
ms.date: 03/19/2018
ms.author: jdaly
ms.openlocfilehash: 5ed61c77cc0cea3cf25e48b347f8a524cf62dfd5
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="common-data-service-for-apps-developer-overview"></a>Common Data Service for Apps: общие сведения для разработчиков
PowerApps предоставляет пользователям, организациям, партнерам, независимым поставщикам программного обеспечения и системным интеграторам эффективную платформу для создания бизнес-приложений. Новым дополнением к PowerApps в этом выпуске стала служба Common Data Service for Apps. Теперь Common Data Service for Apps содержит основные функциональные возможности платформы Dynamics 365 Customer Engagement.


## <a name="get-started"></a>Начало работы
Если у вас уже есть опыт работы с приложениями Dynamics 365 Customer Engagement, он пригодится и при настройке и расширении Common Data Service for Apps.

Если вы впервые сталкиваетесь с приложениями Dynamics 365 Customer Engagement, в следующих подразделах вы сможете кратко познакомиться с основными понятиями, помогающие приступить к работе с Common Data Service for Apps.

> [!NOTE]
> - Приложения на основе модели подключаются к службе Common Data Service for Apps. Сведения о том, как разработчики могут повышать ценность на уровне приложения, см. в разделе [Приложения на основе модели: общие сведения для разработчиков](../model-driven-apps/overview.md). Материал этого раздела касается только расширений, которые разработчики могут создать на уровне обслуживания. 
> - Так как Common Data Service for Apps и Dynamics 365 Customer Engagement используют одну платформу, более полные сведения для разработчиков можно найти в [руководстве по Dynamics 365 Customer Engagement для разработчиков](/dynamics365/customer-engagement/developer/developer-guide). Эти разделы содержат ссылки на руководство для разработчиков и другие руководства.


## <a name="tools-and-resources-for-developers"></a>Средства и ресурсы для разработчиков

При работе с решениями, использующими Common Data Service for Apps, разработчики будут пользоваться указанными ниже средствами и ресурсами.

### <a name="tools-available-for-download-from-nuget"></a>Средства, доступные для скачивания с сайта NuGet

Приведенные ниже средства распространяются в пакетах NuGet. В разделе [Руководство для разработчика. Скачивание средств с сайта NuGet](/dynamics365/customer-engagement/developer/download-tools-nuget) описан сценарий PowerShell, который можно использовать для скачивания и извлечения последних версий этих средств.

|Средство  |Описание  |
|---------|---------|
|Средство создания кода `CrmSvcUtil.exe`|Средство формирования кода командной строки, создающее классы .NET Framework с упреждающей привязкой, которые представляют модель EDM, используемую службой организации. <br />Дополнительные сведения: <br />[Служба организации](use-web-services.md#organization-service)<br />[Руководство по Dynamics 365 Customer Engagement для разработчика. Создание классов сущностей с упреждающей привязкой с помощью средства формирования кода ](/dynamics365/customer-engagement/developer/org-service/create-early-bound-entity-classes-code-generation-tool)|
|Средство переноса конфигурации `DataMigrationUtility.exe`|Используется для перемещения данных конфигурации между средами. Данные конфигурации используются для определения пользовательских функций и обычно хранятся в настраиваемых сущностях. Это средство не предназначено для перемещения бизнес-данных. <br /> Дополнительные сведения: [Руководство по Dynamics 365 Customer Engagement для администраторов. Перемещение данных конфигурации между экземплярами и организациями с помощью средства переноса конфигурации](/dynamics365/customer-engagement/admin/manage-configuration-data)|
|Package Deployer `PackageDeployer.exe`|Используется для развертывания пакетов в экземплярах Common Data Service for Apps. Пакет — это устанавливаемая единица, включающая в себя решения. <br /> Дополнительные сведения: <br />[Развертывание пакетов решений](introduction-solutions.md#deploy-solution-packages)<br />[Руководство по Dynamics 365 Customer Engagement для разработчика. Создание пакетов для Dynamics 365 Package Deployer](/dynamics365/customer-engagement/developer/create-packages-package-deployer).|
|Средство регистрации подключаемых модулей `PluginRegistration.exe`|Средство, используемое для подписки классов подключаемых модулей сборки .NET на события сервера. <br />Дополнительные сведения: <br />[Создание подключаемого модуля](apply-business-logic-with-code.md#create-a-plug-in)<br />[Руководство по Dynamics 365 Customer Engagement для разработчика. Пошаговое руководство: регистрация подключаемого модуля с помощью средства регистрации подключаемых модулей](/dynamics365/customer-engagement/developer/walkthrough-register-plugin-using-plugin-registration-tool)|
|Средство SolutionPackager `SolutionPackager.exe`|Средство, обеспечивающее обратимое разложение сжатого файла решения Common Data Service for Apps на несколько XML-файлов и других файлов, которыми можно легко управлять с помощью системы управления версиями.<br /> Дополнительные сведения: <br />[Коллективная разработка решений](introduction-solutions.md#team-development-of-solutions)<br />[Руководство по Dynamics 365 Customer Engagement для разработчика. Использование средства SolutionPackager для сжатия и извлечения файла решения](/dynamics365/customer-engagement/developer/compress-extract-solution-file-solutionpackager)|

### <a name="net-sdk-assemblies"></a>Сборки пакета SDK для .NET 

Ниже приведены сборки, которые могут использовать разработчики .NET. Последние версии доступны для скачивания в соответствующих пакетах NuGet.

#### <a name="work-with-data"></a>Работа с данными

Используйте эти сборки для взаимодействия со службой организации и службами обнаружения.

Дополнительные сведения см. в статье [Руководство по Dynamics 365 Customer Engagement для разработчика. Использование службы организации Dynamics 365](/dynamics365/customer-engagement/developer/use-microsoft-dynamics-365-organization-service).

**Пакет NuGet**: [Microsoft.CrmSdk.CoreAssemblies](https://www.nuget.org/packages/Microsoft.CrmSdk.CoreAssemblies/)

|Сборка  |Пространства имен  |
|---------|---------|
|Microsoft.Crm.Sdk.Proxy.dll|[Microsoft.Crm.Sdk](/dotnet/api/microsoft.crm.sdk)<br />[Microsoft.Crm.Sdk.Messages](/dotnet/api/microsoft.crm.sdk.messages)|
|Microsoft.Xrm.Sdk.dll|[Microsoft.Xrm.Sdk](/dotnet/api/microsoft.xrm.sdk)<br />[Microsoft.Xrm.Sdk.Client](/dotnet/api/microsoft.xrm.sdk.client)<br />[Microsoft.Xrm.Sdk.Discovery](/dotnet/api/microsoft.xrm.sdk.discovery)<br />[Microsoft.Xrm.Sdk.Messages](/dotnet/api/microsoft.xrm.sdk.messages)<br />[Microsoft.Xrm.Sdk.Metadata](/dotnet/api/microsoft.xrm.sdk.metadata)<br />[Microsoft.Xrm.Sdk.Metadata.Query](/dotnet/api/microsoft.xrm.sdk.metadata.query)<br />[Microsoft.Xrm.Sdk.Organization](/dotnet/api/microsoft.xrm.sdk.organization)<br />[Microsoft.Xrm.Sdk.Query](/dotnet/api/microsoft.xrm.sdk.query)<br />[Microsoft.Xrm.Sdk.WebServiceClient](/dotnet/api/microsoft.xrm.sdk.webserviceclient)|

#### <a name="create-process-designer-workflow-extensions"></a>Создание расширений конструктора процессов (рабочий процесс)

Используйте эту сборку, чтобы добавить настраиваемые действия в конструктор процессов. 

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Настраиваемые действия рабочих процессов (сборки рабочих процессов)](/dynamics365/customer-engagement/developer/custom-workflow-activities-workflow-assemblies).

**Пакет NuGet**: [Microsoft.CrmSdk.Workflow](https://www.nuget.org/packages/Microsoft.CrmSdk.Workflow/) 

|Сборка|Пространства имен|
|---------|---------|
|Microsoft.Xrm.Sdk.Workflow.dll|[Microsoft.Xrm.Sdk.Workflow](/dotnet/api/microsoft.xrm.sdk.workflow)<br />[Microsoft.Xrm.Sdk.Workflow.Activities](/dotnet/api/microsoft.xrm.sdk.workflow.activities)<br />[Microsoft.Xrm.Sdk.Workflow.Designers](/dotnet/api/microsoft.xrm.sdk.workflow.designers)|

#### <a name="build-windows-client-applications"></a>Создание клиентских приложений Windows

Используйте эти сборки, чтобы упростить подключение к службе организации и создавать клиентские приложения Windows. 

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Создание клиентских приложений Windows с помощью средств xRM](/dynamics365/customer-engagement/developer/build-windows-client-applications-xrm-tools).

**Пакеты NuGet**:
- [Microsoft.CrmSdk.XrmTooling.CoreAssembly](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.CoreAssembly/) (Microsoft.Xrm.Tooling.Connector.dll)
- [Microsoft.CrmSdk.XrmTooling.WpfControls](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.WpfControls/) 

|Сборка|Пространства имен  |
|---------|---------|
|Microsoft.Xrm.Tooling.Connector.dll|[Microsoft.Xrm.Tooling.Connector](/dotnet/api/microsoft.xrm.tooling.connector)<br />[Microsoft.Xrm.Tooling.Connector.Model](/dotnet/api/microsoft.xrm.tooling.connector.model)|
|Microsoft.Xrm.Tooling.CrmConnectControl.dll|[Microsoft.Xrm.Tooling.CrmConnectControl](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Model](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.model)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Properties](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.properties)<br />[Microsoft.Xrm.Tooling.CrmConnectControl.Utility](/dotnet/api/microsoft.xrm.tooling.crmconnectcontrol.utility)|
|Microsoft.Xrm.Tooling.WebResourceUtility.dll|[Microsoft.Xrm.Tooling.WebResourceUtility](/dotnet/api/microsoft.xrm.tooling.webresourceutility)|

#### <a name="create-packages"></a>Создание пакетов

Используйте эти сборки, чтобы создать пакеты для Package Deployer.

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Создание пакетов для Dynamics 365 Package Deployer](/dynamics365/customer-engagement/developer/create-packages-package-deployer).

**Пакет NuGet**: [Microsoft.CrmSdk.XrmTooling.PackageDeployment](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment/)

|Сборка|Пространство имен  |
|---------|---------|
|Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.dll|[Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase](/dotnet/api/microsoft.xrm.tooling.packagedeployment.crmpackageextentionbase)|

#### <a name="create-custom-virtual-entity-data-providers"></a>Создание поставщиков данных для настраиваемой виртуальной сущности

Используйте эту сборку, чтобы создать поставщики данных для настраиваемой виртуальной сущности. 

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Начало работы с виртуальными сущностями](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve).

**Пакет NuGet**: [Microsoft.CrmSdk.Data](https://www.nuget.org/packages/Microsoft.CrmSdk.Data/)

|Сборка  |Пространства имен  |
|---------|---------|
|Microsoft.Xrm.Sdk.Data.dll|[Microsoft.Xrm.Sdk.Data](/dotnet/api/microsoft.xrm.sdk.data)<br />[Microsoft.Xrm.Sdk.Data.CodeGen](/api/microsoft.xrm.sdk.data.codegen)<br />[Microsoft.Xrm.Sdk.Data.Converters](/dotnet/api/microsoft.xrm.sdk.data.converters)<br />[Microsoft.Xrm.Sdk.Data.Exceptions](/dotnet/api/microsoft.xrm.sdk.data.exceptions)<br />[Microsoft.Xrm.Sdk.Data.Expressions](/dotnet/api/microsoft.xrm.sdk.data.expressions)<br />[Microsoft.Xrm.Sdk.Data.Infra](/dotnet/api/microsoft.xrm.sdk.data.infra)<br />[Microsoft.Xrm.Sdk.Data.Mappings](/dotnet/api/microsoft.xrm.sdk.data.mappings)|

#### <a name="extend-outlook-client"></a>Расширение клиента Outlook

Используйте эту сборку, чтобы взаимодействовать с Microsoft Dynamics 365 для Outlook и Microsoft Dynamics 365 для Microsoft Office Outlook с доступом вне сети. 

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Расширение Dynamics 365 Customer Engagement для Outlook](/dynamics365/customer-engagement/developer/extend-customer-engagement-outlook).

**Пакет NuGet**: [Microsoft.CrmSdk.Outlook](https://www.nuget.org/packages/Microsoft.CrmSdk.Outlook/)

|Сборка|Пространство имен|
|---------|---------|
|Microsoft.Crm.Outlook.Sdk.dll|[Microsoft.Crm.Outlook.Sdk](/dotnet/api/microsoft.crm.outlook.sdk)|



### <a name="community-tools-for-common-data-service-for-apps"></a>Средства сообщества для Common Data Service for Apps

Сообщество Dynamics 365 создает средства. Многие из самых популярных распространяются посредством [XrmToolBox](https://www.xrmtoolbox.com/). XrmToolBox — это приложение Windows, который подключается к Common Data Service for Apps и предоставляет средства, упрощающие настройку, конфигурацию и работу. Оно поставляется вместе с более чем 30 подключаемыми модулями, которые облегчают и ускоряют администрирование, настройку и конфигурацию.

Ниже приведен список отобранных средств сообщества, распространяемых посредством XrmToolBox, которые можно использовать с Common Data Service for Apps.

|Средство  |Описание  |
|---------|---------|
|[Attribute Manager](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.AttributeManager/)|Используется для переименования, удаления или изменения типа атрибута.|
|[Early Bound Generator](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.EarlyBoundGenerator/)|Создает сущности, наборы параметров или действия с упреждающей привязкой. Использует CrmSvcUtil из пакета SDK и отображает командную строку, используемую для создания классов.|
|[Export to Excel](https://www.xrmtoolbox.com/plugins/Ryr.XrmToolBox.ExportToExcel/)|Позволяет легко экспортировать записи из выбранного представления/FetchXML в Excel.|
|[FetchXML Builder](https://www.xrmtoolbox.com/plugins/Cinteros.Xrm.FetchXmlBuilder/)|Позволяет создавать и тестировать запросы FetchXml.|
|[Metadata Browser](https://www.xrmtoolbox.com/plugins/MsCrmTools.MetadataBrowser/)|Позволяет просматривать метаданные из вашей организации Dynamics CRM.|
|[Plugin Trace Viewer](https://www.xrmtoolbox.com/plugins/Cinteros.XrmToolBox.PluginTraceViewer/)|Позволяет изучить журнал трассировки подключаемых модулей и предоставляет удобные функции фильтрации и просмотра.|
|[User Settings Utility](https://www.xrmtoolbox.com/plugins/MsCrmTools.UserSettingsUtility/)|Позволяет массово управлять личными параметрами пользователей.|

> [!NOTE]
> Средства, созданные сообществом, не поддерживаются корпорацией Майкрософт. Если у вас появились проблемы или вопросы, связанные со средствами сообщества, обратитесь к издателю средства.
