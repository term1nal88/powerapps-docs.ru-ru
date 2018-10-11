---
title: Метаданные атрибутов | Документы Майкрософт
description: Сведения об использовании метаданных атрибутов в Common Data Service for Apps.
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
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: f6fcf3ba1e8e9773df65ac566a9d5c798f4d13a9
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42859168"
---
# <a name="attribute-metadata"></a>Метаданные атрибутов

Сущности содержат коллекцию атрибутов, представляющих данные, которые можно включить в каждую запись. Разработчики должны понимать особенности различных типов атрибутов и уметь работать с ними. 

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Общие сведения об атрибутах сущностей](/dynamics365/customer-engagement/developer/introduction-entity-attributes).

## <a name="attribute-names"></a>Имена атрибутов

Как и в случае с сущностями, каждый атрибут имеет уникальное имя, определенное при его создании. Это имя указывается несколькими способами:


|Имя |Описание  |
|---------|---------|
|`SchemaName`|Обычно версия логического имени в регистре Pascal. Например, `AccountNumber`.|
|`LogicalName`|Имя, состоящее только из строчных букв. Например, `accountnumber`.|

При создании настраиваемого атрибута в начало выбранного вами имени будет добавлено значение префикса настройки для издателя, связанного с решением, где был создан атрибут.

Вы уже не сможете изменить имена для атрибута после его создания.

Каждый атрибут также имеет два свойства, которые могут отображать локализованные значения. Это значения, используемые для ссылки на атрибуты в приложении.

|Имя |Описание  |
|---------|---------|
|`DisplayName`|Обычно совпадает с именем схемы, но может содержать пробелы. Например, **Код организации**.|
|`Description`|Короткое предложение, описывающее атрибут или содержащее указания для пользователя. Например, *Введите идентификационный номер или код счета для быстрого поиска организации в системных представлениях*.<br />В приложениях на основе моделей эти сведения отображаются при наведении указателя мыши на поле этого атрибута в форме.|


Это локализуемые значения, используемые для ссылки на атрибуты в приложении. Эти значения можно изменить в любое время. Сведения о том, как добавить или изменить локализованные значения, см. в разделе [Руководство по настройке Dynamics 365 Customer Engagement. Перевод настроенного теста поля и сущности на другие языки](/dynamics365/customer-engagement/customize/export-customized-entity-field-text-translation).

## <a name="attribute-types"></a>Типы атрибутов

Свойство `AttributeTypeName` описывает тип атрибута. Это свойство содержит значение типа `AttributeTypeDisplayName`, предоставляющее метку для каждого из существующих различных типов атрибутов. 

> [!NOTE]
> Не следует путать со свойством `AttributeType`. Значения в этом старом свойстве почти аналогичны `AttributeTypeName`, за исключением того, чтобы атрибуты `ImageType` отображаются как `Virtual`. Вам следует обращаться к свойству `AttributeTypeName`, а не `AttributeType`.

Замечания к приведенной ниже таблице:

- Эти типы сгруппированы по категориям для сравнения.
- Для каждого значения `AttributeTypeDisplayName` включается соответствующий производный класс [AttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.attributemetadata) сборки .NET при его наличии. Между этими типами и меткой `AttributeTypeDisplayName` отсутствует связь 1:1.
- Те типы атрибутов, которые можно создать как настраиваемые атрибуты, включают в себя соответствующую метку, отображаемую в пользовательском интерфейсе.


|Категория|Тип AttributeTypeDisplayName/<br />AttributeMetadata|Возможность создания/<br />Метка|Описание  |
|---------|---------|---------|---------|
|Классификация|`BooleanType`<br />[BooleanAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.booleanattributemetadata)|Да<br />**Два параметра**|Содержит выбранное значение параметра из двух (обычно true или false).<br />Дополнительные сведения см. в разделе [Наборы параметров](#option-sets).|
|Классификация|`EntityNameType`<br />[EntityNameAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.entitynameattributemetadata)|Нет|Содержит значение параметра, соответствующее сущности в системе. Только для внутреннего использования.|
|Классификация|`MultiSelectPicklistType`<br />[MultiSelectPicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.multiselectpicklistattributemetadata)|Да<br />**Набор параметров для множественного выбора**|Содержит несколько выбранных значений параметра, когда разрешен множественный выбор.<br />Дополнительные сведения: <br />[Наборы параметров](#option-sets)<br />[Руководство по Dynamics 365 Customer Engagement для разработчика. Атрибуты списка множественного выбора](/dynamics365/customer-engagement/developer/multi-select-picklist)|
|Классификация|`PicklistType`<br />[PicklistAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.picklistattributemetadata)|Да<br />**Набор параметров**|Содержит выбранное значение параметра, когда разрешен выбор одного значения.<br />Дополнительные сведения см. в разделе [Наборы параметров](#option-sets).|
|Классификация|`StateType`<br />[StateAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stateattributemetadata)|Нет|Содержит значение параметра, описывающее состояние для записи сущности.<br />Дополнительные сведения см. в разделе [Наборы параметров](#option-sets).|
|Классификация|`StatusType`<br />[StatusAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.statusattributemetadata)|Нет|Содержит значение параметра, описывающее причину состояния для записи сущности.<br />Дополнительные сведения см. в разделе [Наборы параметров](#option-sets).|
|Коллекция|`CalendarRulesType`|Нет|Содержит коллекцию записей сущностей `CalendarRules`.<br />Атрибуты, использующие этот тип, отсутствуют. При создании прокси средство формирования кода создаст два имитируемых атрибута, отсутствующие в метаданных. Эти атрибуты отражают представление записей правил календаря, имеющих связь "один ко многим" с записью сущности.|
|Коллекция|`PartyListType`|Нет|Содержит коллекцию записей сущностей `ActivityParty`.<br />Дополнительные сведения см. в разделе [Сущность ActivityParty](#activityparty-entity).|
|Дата и время|`DateTimeType`<br />[DateTimeAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.datetimeattributemetadata)|Да<br />**Дата и время**|Содержит значения даты и времени.<br />Все атрибуты даты и времени поддерживают значения, начиная с 00:00 01.01.1753.|
|Изображение|`ImageType`<br />[ImageAttributeMetadata]()|Да<br />**Изображение**|Содержит сведения, помогающие извлечь данные изображения для записи сущности.<br />Дополнительные сведения см. в разделе [Изображения сущностей](entity-metadata.md#entity-images).|
|Управляемое свойство|`ManagedPropertyType`<br />[ManagedPropertyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.imageattributemetadata)|Нет|Содержит данные, описывающие, можно ли настроить компонент решения, хранящийся в записи сущности, при включении в управляемое решение.<br />Дополнительные сведения см. в разделе [Управляемые свойства](introduction-solutions.md#managed-properties).|
|Количество|`BigIntType`<br />[BigIntAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.bigintattributemetadata)|Нет|Содержит значение `BigInt`. Только для внутреннего использования.|
|Количество|`DecimalType`<br />[DecimalAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.decimalattributemetadata)|Да<br />**Десятичное число**|Содержит значение `Decimal`. Свойство `Precision` задает уровень точности.|
|Количество|`DoubleType`<br />[DoubleAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.doubleattributemetadata)|Да<br />**Число с плавающей запятой**|Содержит значение `Double`. Свойство `Precision` задает уровень точности.|
|Количество|`IntegerType`<br />[IntegerAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.integerattributemetadata)|Да<br />**Целое число**|Содержит значение `Int`.|
|Количество|`MoneyType`<br />[MoneyAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.moneyattributemetadata)|Да<br />**Валюта**|Содержит значение `Decimal`. Свойство `PrecisionSource` указывает, где задан уровень точности.<br />0: свойство `Precision`<br />1: атрибут `Organization.PricingDecimalPrecision`<br />2: атрибут `TransactionCurrency.CurrencyPrecision` в записи сущности|
|Справочные материалы|`CustomerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Да<br />**Клиент**|Содержит ссылку на учетную запись или запись сущности контакта.|
|Справочные материалы|`LookupType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Да<br />**Поиск**|Содержит ссылку на запись сущности. Логические имена допустимых записей обычно хранятся в свойстве `Targets` атрибута.|
|Справочные материалы|`OwnerType`<br />[LookupAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.lookupattributemetadata)|Нет|Содержит ссылку на запись сущности группы или пользователя.|
|Строка|`MemoType`<br />[MemoAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.memoattributemetadata)|Да<br />**Многострочный текст**|Содержит строковое значение, предназначенное для отображения в многострочном текстовом поле.|
|Строка|`StringType`<br />[StringAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.stringattributemetadata)|Да<br />**Однострочный текст**|Содержит строковое значение, предназначенное для отображения в однострочном текстовом поле.|
|Уникальный идентификатор|`UniqueidentifierType`<br />[UniqueIdentifierAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.uniqueidentifierattributemetadata)|Нет|Содержит значение уникального идентификатора GUID.|
|Виртуальный|`VirtualType`|Нет|Эти атрибуты запрещено использовать в коде и в общем случае можно игнорировать.|


## <a name="supported-operations-and-form-usage-for-attributes"></a>Поддерживаемые операции и использование формы для атрибутов

Каждый атрибут содержит логические свойства, описывающие типы операций, в которых его можно использовать, а также способ его применения на форме.

|Свойство|Описание|
|--|--|
|`IsRequiredForForm`|Указывает, нужно ли указать атрибут на форме в качестве поля.|
|`IsValidForCreate`|Указывает, можно ли задать значение атрибута в операции создания.|
|`IsValidForForm`|Указывает, можно ли указать атрибут на форме в качестве поля.|
|`IsValidForRead`|Указывает, можно ли извлечь значение атрибута.|
|`IsValidForUpdate`|Указывает, можно ли задать значение атрибута в операции обновления.|

Если попытаться задать значение для атрибута в рамках операции создания или обновления, для которой он не является допустимым, это значение игнорируется.
При попытке извлечь недопустимый для чтения атрибут возвращается значение Null.


## <a name="attribute-requirement-level"></a>Уровень потребности в атрибуте

`RequiredLevel` является логическим управляемым свойством, указывающим потребность в значении атрибута.

Это свойство может принимать следующие значения:

|Имя|Значение|Метка пользовательского интерфейса|Описание|
|--|--|--|--|
|`None`|0|**Необязательно**|Требования не указаны.|
|`SystemRequired`|1|**Обязательно для системы**|Атрибут должен иметь значение.|
|`ApplicationRequired`|2|**Бизнес-требование**|Бизнесу необходимо, чтобы атрибут имел значение.|
|`Recommended`|3|**Бизнес-рекомендация**|Рекомендуется, чтобы атрибут имел значение.|

Common Data Service for Apps применяет параметр `SystemRequired` только для атрибутов, созданных системой. Пользовательские атрибуты не могут использовать параметр `SystemRequired`. 

Приложения на основе моделей применяют параметр `ApplicationRequired` и используют другое представление для параметра `Recommended`. Разработчики настраиваемых клиентов могут воспользоваться этой информацией, чтобы запросить аналогичные варианты проверки или представления.

Это свойство является управляемым. Поэтому вы, как издатель управляемого решения, можете разрешить или запретить его пользователям изменять эти параметры для атрибутов.

Дополнительные сведения см. в разделе [Управляемые свойства](introduction-solutions.md#managed-properties).


## <a name="rollup-and-calculated-attributes"></a>Атрибуты свертки и вычисляемые атрибуты

Атрибуты свертки и вычисляемые атрибуты избавляют пользователя от необходимости вручную выполнять вычисления, что помогает ему сконцентрироваться на своей работе. Системные администраторы могут определить поле, содержащее значение многих общих вычислений, без привлечения разработчика. Разработчики также могут выполнять эти вычисления с помощью возможностей платформы, а не внутри своего кода.

Дополнительные сведения: 
- [Руководство по настройке Dynamics 365 Customer Engagement. Определение полей свертки, вычисляющих значения](/dynamics365/customer-engagement/customize/define-rollup-fields)
- [Руководство по настройке Dynamics 365 Customer Engagement. Вычисляемые атрибуты и атрибуты свертки](/dynamics365/customer-engagement/customize/define-calculated-fields)
- [Руководство по Dynamics 365 Customer Engagement для разработчика. Вычисляемые атрибуты и атрибуты свертки](/dynamics365/customer-engagement/developer/calculated-rollup-attributes)

## <a name="attribute-format"></a>Формат атрибутов

Значения формата для атрибутов определяют их отображение в приложениях на основе моделей. Разработчик пользовательских приложений может использовать эти сведения для реализации аналогичных возможностей.

### <a name="integer-formats"></a>Форматы целых чисел

Используйте свойство `Format` с целочисленными атрибутами, чтобы отобразить альтернативный вариант интерфейса для этого типа.

|Вариант|Описание|
|--|--|
|`None`|Отображает текстовое поле для изменения числового значения.|
|`Duration`|Отображает раскрывающийся список с интервалами времени. Пользователь может выбрать значение в списке или ввести целое число, обозначающее количество минут.|
|`TimeZone`|Отображает раскрывающийся список с часовыми поясами.|
|`Language`|Отображает раскрывающийся список с языками, включенными для данной организации. Если никакие другие языки не включены, отображается только базовый язык. Сохраненное значение является кодом данного языка.|

### <a name="string-formats"></a>Форматы строк

Используйте свойство `FormatName` со строковыми атрибутами для задания значений из [класса StringFormatName](/dotnet/api/microsoft.xrm.sdk.metadata.stringformatname), чтобы управлять форматированием строкового атрибута.

|Имя|Описание|
|--|--|
|`Email`|Это поле формы проверяет текстовое значение в качестве адреса электронной почты и создает в поле ссылку mailto.|
|`PhoneNumber`|Это поле формы содержит ссылку для запуска телефонного звонка с помощью Skype.|
|`PhoneticGuide`|Только для внутреннего использования.|
|`Text`|Эта форма отображает текстовое поле.|
|`TextArea`|Эта форма отображает поле с текстовой областью.|
|`TickerSymbol`|Эта форма отображает ссылку, которая при открытии отображает котировку для финансового символа.|
|`URL`|Эта форма отображает ссылку для открытия URL-адреса.|
|`VersionNumber`|Только для внутреннего использования.|

### <a name="date-and-time-formats"></a>Форматы даты и времени

Свойство `DateTimeBehavior` управляет поведением для атрибутов даты и времени.
Доступно три параметра:

|Вариант|Краткое описание|
|--|--|
|`UserLocal`|Сохраняет значение даты и времени в формате UTC в системе.|
|`DateOnly`|Сохраняет фактическое значение даты со значением времени 00:00:00 в системе.|
|`TimeZoneIndependent`|Сохраняет фактические значения даты и времени в системе независимо от часового пояса пользователя.|

Используйте свойство `Format` для управления отображением значения в приложении на основе моделей независимо от значения `DateTimeBehavior`.

|Вариант|Описание|
|--|--|
|DateAndTime|Дата и время отображаются полностью.|
|DateOnly|Отображается только дата.|

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Поведение и формат атрибута даты и времени](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute).

## <a name="auto-number-attributes"></a>Атрибуты автонумерации

Вы можете добавить атрибут автонумерации для любой сущности. Сейчас этот атрибут можно добавить программным способом. Пользовательский интерфейс для его добавления отсутствует.
Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Создание атрибутов автонумерации](/dynamics365/customer-engagement/developer/create-auto-number-attributes).

## <a name="option-sets"></a>Наборы параметров

Атрибуты, отображающие набор параметров, могут ссылаться на набор параметров, определенных атрибутом, или на отдельный набор параметров, который может совместно использоваться несколькими атрибутами. Это особенно удобно в тех случаях, когда значения в одном атрибуте применяются и для других атрибутов. Ссылаясь на общий набор параметров, можно работать с параметрами в одном месте. Наборы параметров, которые можно использовать совместно, называются *глобальными*. Наборы, определенные внутри атрибута, называются *локальными*.

### <a name="retrieve-options-data"></a>Извлечение данных о параметрах
Служба организации предоставляет классы запросов, которые можно использовать для получения параметров, используемых атрибутом.

#### <a name="use-the-organization-service-to-retrieve-options"></a>Использование службы организации для извлечения параметров

Каждый из атрибутов с параметрами наследует [EnumAttributeMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata) и включает в себя [свойство OptionSet](/dotnet/api/microsoft.xrm.sdk.metadata.enumattributemetadata.optionset). Это свойство содержит [OptionSetMetadata](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata), включающий в себя параметры со [свойством Options](/dotnet/api/microsoft.xrm.sdk.metadata.optionsetmetadata.options). 

Служба организации позволяет использовать следующие сообщения для получения сведений о наборах данных:

|Класс запроса|Описание|
|--|--|
|[RetrieveAllOptionSetsRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievealloptionsetsrequest) |Получает данные обо всех *глобальных* наборах данных.|
|[RetrieveAttributeRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveattributerequest) |Получает данные об атрибуте, включая все *локальные* наборы данных.|
|[RetrieveMetadataChangesRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrievemetadatachangesrequest) |Получает метаданные на основе запроса, который может включать *локальные* наборы данных.<br />Дополнительные сведения см. в разделе [Извлечение и обнаружение изменений в метаданных](/dynamics365/customer-engagement/developer/retrieve-detect-changes-metadata).|
|[RetrieveOptionSetRequest](/dotnet/api/microsoft.xrm.sdk.messages.retrieveoptionsetrequest) |Получает данные о *глобальном* наборе данных.|

Дополнительные сведения: 
- [Пример: внесение метаданных для списка выбора атрибута в файл дампа](/dynamics365/customer-engagement/developer/org-service/sample-dump-attribute-picklist-metadata-file)
- [Руководство по Dynamics 365 Customer Engagement для разработчика. Настройка глобальных наборов параметров](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)

#### <a name="use-the-web-api-to-retrieve-options"></a>Использование веб-API для извлечения параметров

Веб-API предоставляет стиль RESTful для запроса значений параметров. Вы можете извлечь локальные или глобальные параметры, получив атрибуты в сущности. Следующий пример возвращает [OptionSetMetadata](/dynamics365/customer-engagement/web-api/optionsetmetadata) для параметров, включенных в свойство [Account](reference/entities/account.md).[AccountCategoryCode](reference/entities/account.md#BKMK_AccountCategoryCode).

`GET <organization url>/api/data/v9.0/EntityDefinitions(LogicalName='account')/Attributes(LogicalName='accountcategorycode')/Microsoft.Dynamics.CRM.PicklistAttributeMetadata?$select=LogicalName&$expand=OptionSet`

Кроме того, веб-API позволяет использовать [функцию RetrieveMetadataChanges](/dynamics365/customer-engagement/web-api/retrievemetadatachanges).

Дополнительные сведения см. в разделе [Руководство по Dynamics 365 Customer Engagement для разработчика. Веб-API > запрос атрибутов EntityMetadata](/dynamics365/customer-engagement/developer/webapi/query-metadata-web-api#querying-entitymetadata-attributes).



## <a name="attribute-mapping"></a>Сопоставление атрибутов

При создании записи сущности в контексте существующей записи сущности можно автоматически перенести определенные значения из существующей записи, чтобы использовать их по умолчанию для новой записи. Это ускорит ввод данных пользователям, работающим с приложениями на основе моделей. Пользователи приложения видят сопоставленные значения и могут изменить их перед сохранением сущности.

Разработчики настраиваемых клиентов могут реализовать аналогичное поведение с помощью сообщения `InitializeFrom` ([класс InitializeFromRequest](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest) службы организации или [функция InitializeFrom](/dynamics365/customer-engagement/web-api/initializefrom) веб-API), чтобы получить данные сущности с настроенным набором значений по умолчанию.

Дополнительные сведения 
- [Руководство по Dynamics 365 Customer Engagement для разработчика. Сопоставление полей сущности](/dynamics365/customer-engagement/customize/map-entity-fields#BKMK_mappingEntityFields)
- [Руководство по Dynamics 365 Customer Engagement для разработчика. Настройка сопоставлений атрибутов и сущностей](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)

### <a name="see-also"></a>См. также

[Сущности в Common Data Service for Apps](entities.md)
