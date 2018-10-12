---
title: Рекомендации по созданию приложений с помощью службы Common Data Service для приложений | Документация Майкрософт
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e9810433-224b-4bde-851a-e581cf5fb8a4
caps.latest.revision: 21
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1eda4b591a3296001ffa62b16e185b421a197e75
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865048"
---
# <a name="common-data-service-for-apps-supported-and-unsupported-app-building-practices"></a>Поддерживаемые и неподдерживаемые методы создания приложений с помощью службы Common Data Service для приложений

<!--
The way your organization works is unique. Some organizations have well-defined business processes that they apply using PowerApps apps. Others aren’t happy with their current business processes and use PowerApps to apply new data and processes to their business. Whatever situation you find yourself in, you’ll find a lot of customization capabilities in PowerApps so that it can work for your organization.  
  
 Of course you’re eager to get started, but please take a few minutes to read the content in this section. This will introduce you to important terms, give you some background about why things are done a certain way, and help you avoid potential problems in the future.  

## What is metadata and why should you care?  
 In the past, you may have customized business applications by editing the source code. This created complications because each organization had unique changes and it was very difficult, or extremely expensive, to upgrade. Then application developers started exposing application programming interfaces (APIs) so that other developers could interact with the application and add their own logic without touching the source code. This was moderately better because it means developers can extend the application without changing it. But it still requires a developer to write code.  -->
  
 В современных бизнес-приложениях используется архитектура на основе метаданных, чтобы пользователи могли создавать приложения без написания кода. Метаданные — это "данные о данных". Они определяют структуру хранимых данных в службе Common Data Service для приложений. Благодаря метаданным приложение получает информацию об изменениях в структуре данных и это позволяет ему адаптироваться к этим изменениям. Теперь, когда метаданные известны, можно добавлять дополнительные возможности, которые будут привязаны к метаданным.  

Внесение изменений в компоненты службы Common Data Service для приложений (например, сущности, представления, поля, диаграммы и панели мониторинга, используемые для создания приложений, направленные на то, чтобы организовать их работу должным образом) называется *настройка*.  
 
При создании и настройке приложений с помощью средств PowerApps происходит добавление или обновление метаданных или данных, используемых функциями, зависящими от метаданных. Поскольку мы знаем, какие типы данных используются для создания приложений, мы можем учитывать эти данные при добавлении новых функций в среду службы Common Data Service для приложений без нарушения работы приложений. <!-- This way you should always be able to apply an update rollup or upgrade to the latest version and enjoy the best new features.  -->

<!--  
> **Customize or Configure?**   
> Most people say they want to customize the application, so we use the word “customize” to describe changing the system to make it work the way you want. Some people prefer to use the word “configure” because it suggests that no code was required to make changes. Call it whatever you like, we just want to make it clear that you don’t need to be a developer to customize or create PowerApps apps.  -->
  
Для создания и настройки приложений PowerApps не нужно быть разработчиком. Тем не менее, среда PowerApps предоставляет набор веб-служб и интерфейсов API, которые позволяют разработчикам создавать код. При создании кода с помощью поддерживаемых методов можно ожидать, что он будет продолжать работать после обновлений среды службы Common Data Service для приложений.  
  
<a name="BKMK_SupportedCust"></a>   
## <a name="what-kinds-of-customizations-are-supported"></a>Какие виды настройки поддерживаются?  
 Предполагается, что большую часть работы по созданию и настройке приложений можно выполнить с помощью имеющихся средств PowerApps. Если средств настройки будет недостаточно для получения желаемого результата, можно установить решения, предоставляемые сторонними разработчиками, или нанять разработчика для написания кода приложения. Если вы хотите инвестировать в решение, для которого требуется код, следует убедиться, что этот код написан с использованием только поддерживаемых интерфейсов API. Это поможет защитить ваши вложения в приложения и во все решения, которые будут получены.  
  
 Разработчики, которые расширяют возможности приложений PowerApps, обязаны следовать правилам и практическим рекомендациям, описанным в пакете SDK: [Best practices for developing with Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/developer/best-practices-sdk) (Рекомендации по разработке с помощью Dynamics 365 Customer Engagement). В пакете SDK описаны интерфейсы API, доступные разработчикам, а также содержатся рекомендации по лучшему их использованию. Корпорация Майкрософт поддерживает только те интерфейсы API и рекомендации, которые описаны в пакете SDK. Вы можете обнаружить в Интернете описания решения своих задач, но если они не будут использовать интерфейсы API, описанные в пакете SDK, они не будут поддерживаться корпорацией Майкрософт. Перед тем, как разрешить разработчику внести изменение, следует проверить, использует ли разработчик поддерживаемые методы.  
  
 Если разработчики используют интерфейсы API и рекомендации, описанные в пакете SDK, мы можем проверить, не нарушают ли вносимые в службу Common Data Service для приложений изменения существующие настройки. Наша цель — обеспечить правильную работу написанного с использованием поддерживаемых методов кода после выхода новых версий или обновлений службы Common Data Service для приложений. В этом случае вы выигрываете, так как сможете устанавливать новые версии с улучшенными возможностями без необходимости доработки каждый раз своего кода.  
  
 Если мы обнаружим, что изменения в новой версии службы Common Data Service для приложений приведут к нарушению работы поддерживаемой настройки, мы выпустим описание возникающих последствий этих изменений с рекомендациями по соответствующим доработкам кода.  
  
<a name="BKMK_Unsupported"></a>   
## <a name="what-kinds-of-customizations-arent-supported"></a>Какие виды настройки не поддерживаются?  
 Некоторые интерфейсы API и приемы программирования не поддерживаются Майкрософт, но это не значит, что они не будут работать. <!--  “Unsupported by Microsoft” means exactly what it says: you can’t get support about these APIs or programming practices from Microsoft. We don’t test them and we don’t know if something we change will break them. We can’t predict what will happen if someone changes code in our application.  --> Разработчик, который использует неподдерживаемые интерфейсы API и приемы программирования, берет на себя ответственность по поддержке этого кода. Этот код необходимо тестировать, чтобы убедиться в том, что он работает.  
  
 Если вы решили использовать неподдерживаемые настройки в среде службы Common Data Service для приложений, следует обязательно задокументировать все, что было сделано, и не забывать удалять эти настройки прежде, чем обращаться в службу технической поддержки Майкрософт. Если вам требуется помощь по работе с неподдерживаемой настройкой, обратитесь к разработчику или организации, которые подготовили эти настройки.  
  
<a name="BKMK_CommonUnsupportedCustomizations"></a>   
### <a name="common-unsupported-customization-practices"></a>Распространенные методы настройки, которые не поддерживается  
 Ниже приведен список распространенных методов настройки, которые не поддерживаются. Это не полный список. Дополнительные сведения см. в разделе [Supported extensions.for Dynamics 365 Unsupported customizations](https://docs.microsoft.com/dynamics365/customer-engagement/developer/supported-extensions#Unsupported) (Поддерживаемые расширения. Неподдерживаемые настройки). 
 
**Взаимодействие с веб-элементами объектной модели документа (DOM) приложения с помощью JavaScript**  
 Все библиотеки JavaScript, используемые в приложении, должны взаимодействовать только с документированными интерфейсами API. Когда разработчики JavaScript работают с приложениями, они часто обращаются к элементам модели DOM, используя специфические имена. Поскольку приложения PowerApps являются веб-приложениями, эти способы работают, но они могут привести к ошибкам во время обновления, так как имена элементов, на которые они ссылаются, могут быть изменены в любое время. Мы оставляем за собой право вносить любые изменения, необходимые в приложении, а это часто означает, что изменяются правила компоновки страницы. Добавление изменений, зависящих от текущей структуры страницы, означает, что вам потребуется нести затраты на тестирование и возможные изменения пользовательского кода в этих сценариях при каждом обновлении приложения.  
  
 Разработчики JavaScript очень часто используют библиотеку jQuery. Основным преимуществом библиотеки jQuery является упрощение доступа к элементам модели DOM и создание таких элементов. Это как раз то, что мы не поддерживаем на страницах приложений, которые используют службу Common Data Service для приложений. Использововать библиотеку jQuery рекомендуется при разработке пользовательских интерфейсов с веб-ресурсами HTML. На страницах приложений PowerApps поддерживаемые интерфейсы API не требуют jQuery.  
  
 **Использование любых недокументированных внутренних объектов и методов на языке JavaScript**  
Служба Common Data Service для приложений использует на страницах много объектов JavaScript. Разработчик JavaScript может обнаружить такие объекты при отладке страниц, а затем обращаться к ним и повторно их использовать. Мы оставляем за собой право вносить в эти объекты любые необходимые изменения, можем удалить их или изменить имена методов. Если сценарий обращается к этим объектам и если они не будут найдены, то работа сценария будет нарушена.  <a name="BKMK_Metadata"></a>   
 
<a name="BKMK_CombineCustomizations"></a>   
## <a name="combine-customization-capabilities"></a>Объединение возможностей настроек  
 Возможности отдельных настроек уже достаточно подробно описаны. Но важно помнить, что в решениях для реальных бизнес-задач часто используются разные настройки в сочетании одна с другой.  
  
<a name="BKMK_ChooseTheRightCustomization"></a>   
### <a name="choose-the-right-customization-capability-for-the-job"></a>Выбор подходящих настроек для работы  
 В PowerApps имеется много различных настроек. Самый легкий путь — это, ознакомившись с одной из них, попытаться использовать ее для решения всех задач. При оценке бизнес-задачи, которую требуется решить, подумайте о конечном результате и проработайте весь путь от начала до конца прежде, чем выберете метод решения.  
 
<a name="BKMK_changesinperformance"></a>   
## <a name="changes-that-affect-common-data-service-for-apps-environment-performance"></a>Изменения, влияющие на производительность службы Common Data Service для приложений  
 Импорт решений и применение пользовательских настроек, которые изменяют метаданные, могут повлиять на производительность среды службы Common Data Service для приложений. Нормальной работе системы могут помешать следующие действия.  
  
-   Добавление, удаление и изменение сущностей, альтернативных ключей, атрибутов и связей.   
-   Импорт решений
  
-   Публикации настроек 
  
Если вы применяете изменения в рабочей системе, рекомендуется запланировать эти операции на такое время, когда это менее всего помешает работе пользователей.   
  
  
## <a name="next-steps"></a>Следующие шаги  
[Общие сведения о создании приложения на основе модели](../../maker/model-driven-apps/model-driven-app-overview.md)

