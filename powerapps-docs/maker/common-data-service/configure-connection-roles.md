---
title: Настройка ролей подключения | MicrosoftDocs
ms.custom: ''
ms.date: 05/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-connection-roles"></a>Настройка ролей подключения

В Common Data Service для приложений можно определить **подключения** между записями сущностей, не создавая отношение сущностей. В управляемых моделью приложениях пользователи могут установить связь с именем между записями для создания менее формального отношения, которое не оправдывает создание фактического отношения сущностей. К некоторым примерам относятся *друг*, *брат/сестра*, *супруг(а)*, *участник* и *заинтересованное лицо*. Некоторые подключения также могут быть двусторонними, например *ребенок* и *родитель*, *муж* и *жена* или *доктор* и *пациент*.

Когда пользователь создает подключение между двумя записями, он также может добавить описание и дополнительные сведения, такие как даты начала и окончания отношения. Дополнительные сведения: [Создание подключений для определения и просмотра отношений между записями](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records).

Любой пользователь с правами на запись для сущности **Роль подключения** может установить, какие подключения будут доступны для использования пользователями.

## <a name="view-connection-roles"></a>Просмотр ролей подключения

В CDS для приложений уже настроено несколько стандартных ролей подключения. Для их просмотра необходимо перейти в область параметров. 

### <a name="navigate-to-the-settings-area"></a>Переход в область параметров

1. Во время просмотра управляемого моделью приложения измените URL-адрес для удаления всего, что следует после `dynamics.com`, и обновите страницу.
1. Перейдите в раздел **Параметры** > **Бизнес** > **Управление бизнесом** и выберите **Роли подключения**.

![Роли подключения в параметрах "Управление бизнесом"](media/navigate-settings-connection-roles.png)

В этом представлении можно просмотреть все роли подключения, доступные для этой среды, и изменить их.

> [!NOTE]
> Если необходимо распространить роли подключения с решением, убедитесь, что они включены в решение, которое требуется распространить. Дополнительные сведения: [Добавление ролей подключения в решение](#add-connection-roles-to-a-solution)

## <a name="view-connection-roles-in-the-solution-explorer"></a>Просмотрите роли подключения в обозревателе решений.

Поскольку роли подключения *поддерживают решения*, то есть их можно включить в решение, роли подключения также можно добавить в распространяемое решение.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Большинство ролей подключения, которые отображаются в области **Параметры**, определены во *внутреннем* **решении по умолчанию** (не путать с **решением по умолчанию служб Common Data Service**). Это внутренне **Решение по умолчанию** содержит все настройки в системе. Чтобы просмотреть **Решение по умолчанию**, выберите представление **Все решения — внутренние**.

## <a name="add-connection-roles-to-a-solution"></a>Добавление ролей подключения в решение

Обычно не рекомендуется добавлять компоненты во внутреннее **Решение по умолчанию**. В **решении по умолчанию служб Common Data Service** или любом решении, созданном для работы, можно использовать команду **Добавить существующий**, чтобы добавить любую роль подключения по умолчанию в решение.

![Добавление существующей роли подключения](media/add-existing-connection-role.png)

После добавления роли подключения в решение ее можно изменить там, где она отображается.

## <a name="create-or-edit-connection-roles"></a>Создайте или измените роли подключения.

> [!IMPORTANT]
> Если вы планируете распространить решение, включающее новые роли подключения или изменения в существующих ролях подключения, необходимо добавить их в распространяемое решение. Изменение или добавление новых ролей подключения с помощью области **Параметры** приведет к добавлению этих ролей подключения во внутреннее **Решение по умолчанию**, и они не будут включены в распространяемое решение, пока вы сначала не добавите их в свое решение. Дополнительные сведения: [Добавление ролей подключения в решение](#add-connection-roles-to-a-solution)

В списке **Роли подключения** выберите одну из ролей подключения, чтобы изменить ее.
Существует три шага для определения роли подключения, которые четко вызываются в форме.

![Форма "Создание роли подключения"](media/create-connection-role-form.png)

### <a name="describe-the-connection-role"></a>Описание роли подключения

Задайте следующие поля:

|Поле|Описание|
|--|--|
|**Название**|(Обязательно) Текст, описывающий подключение.|
|**Категория роли подключения**|Группа, описывающая категорию подключения. Дополнительные сведения: [Значения категории роли подключения](#connection-role-category-values)|
|**Описание**|Предоставьте определение для роли.|

#### <a name="connection-role-category-values"></a>Значения категории роли подключения

Значения **Категория роли подключения** по умолчанию могут быть следующими:
- Бизнес
- Семья
- Соцсети
- Sales
- Прочее
- Заинтересованное лицо
- Группа продаж
- Сервис

Можно добавлять новые или изменять существующие категории, изменяя глобальный набор параметров **Категория**. Дополнительные сведения: [Создание и изменение глобального набора параметров для Common Data Service для приложений (списки выбора)](create-edit-global-option-sets.md)

### <a name="select-record-types"></a>Выбор типов записей

Выберите, какие типы записей должны быть доступны для подключения.

> [!NOTE]
> Хотя значение **Все** выбрано по умолчанию, убедитесь, что вы знаете, какие типы являются подходящими для добавляемой роли подключения.

### <a name="matching-connection-roles"></a>Сопоставление ролей подключения

На данном дополнительном шаге можно определить роли, которые будут применяться взаимно. Это не обязательно, но подключения имеют больше смысла, если это определить.

Например, пользователь может установить, что Glen имеет отношение *Друг* для Mary, но значит ли это, что Mary имеет отношение *Friend* для Glen? Мы надеемся на это. Но если Glen имеет отношение *Отец* для Mary, это не значит, что Mary имеет отношение *Отец* для Glen. Для установки правильной взаимозависимости требуется выполнить этот дополнительный шаг.

Когда пользователь задает роль подключения, у которой нет соответствующей роли подключения, роль будет отображаться только при просмотре подключения из записи, к которой применено подключение. При просмотре из связанной записи эта роль будет пуста, если не задать соответствующую роль.

Для определений ролей, таких как *Друг*, *Партнер*, *Коллега* или *Брат/сестра*, рекомендуется назначить соответствующую роль самой себе. Если настроена одна соответствующая роль подключения, одна соответствующая роль подключения будет применена в обоих направлениях.

> [!IMPORTANT]
> Необходимо сохранить новую роль подключения без соответствующей роли подключение, прежде чем можно будет задать соответствующую роль подключения самой себе.

Некоторые роли подключения уже настроены с соответствующими ролями подключения. Роль *Бывший сотрудник* соответствует роли *Бывший работодатель* и наоборот. Этот тип соответствующей роли подключения "один-к-одному" самый распространенный.

Можно настроить несколько соответствующих ролей подключения для описания сложных отношений. Если вы создаете роль подключения, например *Отец*, вы можете настроить еще две роли, такие как *Дочь* и *Сын*, и применить обе роли как соответствующие роли подключения к роли *Отец*. В свою очередь, роли подключения *Дочь* и *Сын* следует сопоставить с ролью *Отец*. Конечно же, затем необходимо настроить эквивалентную роль для роли *Мать*, которая аналогично будет сопоставлена с ролями *Дочь* и *Сын*.

> [!TIP]
> Прежде чем создавать сложный набор ролей подключения, подумайте о создании более простого набора ролей. Например, вместо создания сложного набора ролей подключения, таких как *Отец*, *Мать*, *Сын* и *Дочь*, используйте просто роли *Родитель* и *Ребенок*.

Если настроено несколько соответствующих ролей подключения, эти роли подключения представляют собой единственные допустимые взаимные роли. Первая роль будет применена автоматически как роль по умолчанию. Если значение по умолчанию неправильное, пользователи должны вручную отредактировать подключение и выбрать между допустимыми параметрами, определенными в конфигурации.

### <a name="see-also"></a>См. также
<!-- This is in the basics guide. It needs to be migrated -->
[Создание соединений для определения и просмотра отношений между записями](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)<br />
[Создание и изменение глобального набора параметров для Common Data Service для приложений (списки выбора)](create-edit-global-option-sets.md)<br />
[Создание и изменение отношений между сущностями](create-edit-entity-relationships.md)

