---
title: 'Предварительная версия: использование поставщика данных Azure Cosmos DB для API SQL с помощью Common Data Service for Apps | Документы Майкрософт'
description: Сведения о настройке поставщика данных Azure Cosmos DB для API SQL для работы с виртуальными сущностями.
keywords: API SQL
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: d0031ffc-8754-4a12-b8c1-e08edc49ff73
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: ''
topic-status: Drafting
ms.openlocfilehash: fa45376dff85205a0dfbf28334c678293528d00e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39704632"
---
# <a name="preview-feature-azure-cosmos-db-sql-api-data-provider-requirements"></a>Предварительная версия: требования к поставщику данных Azure Cosmos DB для API SQL

В этом разделе описываются требования к поставщику данных Azure Cosmos DB для API SQL, а также процедура настройки и рекомендации по использованию поставщика данных Azure Cosmos DB для API SQL с виртуальными сущностями. 

> [!IMPORTANT]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-no-ms-support.md)]


## <a name="what-is-azure-cosmos-db"></a>Что такое Azure Cosmos DB?

Azure Cosmos DB — это глобально распределенная многомодельная служба базы данных Майкрософт для критически важных приложений. Она предоставляет знакомые и обширные возможности запросов SQL и обеспечивает стабильную низкую задержку по сравнению с данными JSON без схемы. Дополнительные сведения см. в статье [Общие сведения об Azure Cosmos DB: API SQL](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction).

## <a name="requirements"></a>Требования

- Подписка Azure, которая включает Azure Cosmos DB.
- Коллекция API SQL Azure Cosmos DB.
- В качестве типа базы данных Azure Cosmos DB должен использоваться тип SQL. 

## <a name="data-type-mapping"></a>Сопоставление типов данных

Предположим, что у вас есть документ Azure Cosmos DB в коллекции с именем *Заказы*, и этот документ имеет следующую структуру JSON.

![Пример кода JSON для документа API SQL.](media/documentdbexample.png)

В этой таблице показаны сопоставления типов данных для документа API SQL в коллекции *Заказы* с использованием Common Data Service for Apps.

|Данные API SQL|CDS for Apps|
|--|--|
|`id`|Первичный ключ|
|`name`|Однострочный текст|
|`quantity`|целое число;|
|`orderid`|Однострочный текст|
|`ordertype`|набор параметров;|
|`amount`|Десятичное число или валюта|
|`delivered`|два варианта;|
|`datetimeoffset`|Дата и время|

> [!NOTE]
> - Атрибуты с префиксом в виде символа подчеркивания (_) создаются API SQL.
> - Атрибуты, которые настроены как необязательные в документе API SQL и сопоставлены как **Требуется для бизнеса** в CDS for Apps, вызовут ошибку среды выполнения.
> - В качестве значений атрибута идентификатора должны использоваться идентификаторы GUID.
> - Дополнительные сведения об использовании дат в API SQL см. в разделе [Работа с датами в Azure Cosmos DB](https://azure.microsoft.com/blog/working-with-dates-in-azure-documentdb-4/).

## <a name="supported-sql-query-filtering"></a>Поддерживается фильтрация запросов SQL

Фильтрация запросов SQL поддерживает следующие операторы. 

- Операторы сравнения: `<`, `>`, `<=`, `>=`, `!=`
- Логические операторы: `and`, `or` 
- Операторы для работы с множествами: `in`, `not in`
- Строковые операторы: `like`, `contains`, b`egins with`, `ends with`

> [!NOTE]
> Оператор like преобразуется в аналогичные операторы `contains`/`begins with`/`ends with`. API SQL не поддерживает аргументы шаблона, как описано в разделе [Like (Transact-SQL)](/sql/t-sql/language-elements/like-transact-sql). Поставщик данных Azure Cosmos DB для API SQL может легко преобразовать один особый случай `Like('[aA]%')` в `BeginsWith('a')` или `BeginsWith('A')`. Обратите внимание, что сравнение строк в API SQL выполняется с учетом регистра.

## <a name="add-a-data-source-using-the-azure-cosmos-db-for-sql-api-data-provider"></a>Добавление источника данных с использованием поставщика данных Azure Cosmos DB для API SQL

1. Перейдите к [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.documentdb_data_provider?tab=Overview), выберите **УСТАНОВИТЬ СЕЙЧАС** и следуйте инструкциям по добавлению приложения в вашу среду (для версии 9.x или более поздней версии).
2. После установки решения войдите в среду и выберите **Параметры** > **Администрирование** > **Источники данных виртуальных сущностей**.
3. На панели "Действия" выберите **СОЗДАТЬ**, в диалоговом окне **Выбор поставщика данных** выберите **Поставщик данных Azure Cosmos DB для API SQL** и нажмите кнопку **OK**.
![Выберите поставщика данных Azure Cosmos DB для API SQL.](media/createdatasource.png)
1. Введите следующие сведения, а затем нажмите кнопку **СОХРАНИТЬ И ЗАКРЫТЬ**.

    |Поле|Описание|
    |--|--|
    |**Name** (Наименование)|Введите имя, которое описывает источник данных.|
    |**Имя коллекции**|Идентификатор коллекции базы данных Azure Cosmos DB, содержащей данные, которые должны быть отражены в этой виртуальной сущности.  |
    |**Ключ авторизации**|Первичный или вторичный ключ для учетной записи Azure Cosmos DB. Ключ портала администрирования Azure можно найти в разделе **Ключи** вашей учетной записи Azure Cosmos DB.|
    |**URI**|URI группы ресурсов, в которой находится коллекция Azure Cosmos DB. Формат URI аналогичен `https://contoso/documents.azure.com:443`. URI портала администрирования Azure можно найти в разделе **Ключи** вашей учетной записи Azure Cosmos DB. |
    |**Время ожидания в секундах**|Введите количество секунд времени ожидания ответа от службы Azure Cosmos DB, прежде чем время ожидания запроса к данным истечет. Например, введите значение 30, чтобы перед тем, как время ожидания ответа истечет, проходило не более 30 секунд. Время ожидания по умолчанию составляет 120 секунд.|

    ![Создайте источник данных с использованием поставщика данных API SQL.](media/cosmosdb-datasource.png)

## <a name="best-practices-and-limitations"></a>Рекомендации и ограничения

- При использовании Azure Cosmos DB в качестве источника данных обратите внимание на следующие:
   - Каждый источник данных Azure Cosmos DB может быть связан только с одной виртуальной сущностью.
   - К одной и той же коллекции в Azure Cosmos DB могут быть подключены несколько источников данных.
- Вы не можете сегментировать данные в коллекции по сущностям.
- Для баз данных Azure Cosmos DB не требуется схема, однако необходимо структурировать данные в Azure Cosmos DB с использованием предсказуемой схемы. 
- Несмотря на то, что поставщик Azure Cosmos DB для API SQL реализует преобразование запросов для операторов проекции, фильтрации и сортировки, он не поддерживает операции объединения.
- При использовании API SQL фильтрацию можно выполнять только по одному столбцу.

## <a name="see-also"></a>См. также

[Создание и изменение виртуальных сущностей, содержащих данные из внешнего источника данных](create-edit-virtual-entities.md)
