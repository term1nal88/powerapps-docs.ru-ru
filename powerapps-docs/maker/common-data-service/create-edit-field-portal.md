---
title: Создание и изменение полей для Common Data Service для приложений с помощью портала PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 05/18/2018
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
# <a name="create-and-edit-fields-for-common-data-service-for-apps-using-powerapps-portal"></a>Создание и изменение полей для Common Data Service для приложений с помощью портала PowerApps

[Портал PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) обеспечивает простой способ создания и изменения полей сущностей в Common Data Service для приложений.

Портал позволяет настроить самые распространенные параметры, но некоторые параметры можно задать только с помощью обозревателя решений. <br />Дополнительные сведения: 
- [Создание и изменение полей для Common Data Service для приложений](create-edit-fields.md)
- [Создание и изменение полей для Common Data Service для приложений с помощью обозревателя решений PowerApps](create-edit-field-solution-explorer.md)

## <a name="view-fields"></a>Просмотр полей

1. На [портале PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) выберите режим конструирования **Управляемые моделью** или **Холст**.
2. Выберите **Данные** > **Сущности** и выберите сущность с полями, которые необходимо просмотреть.
3. На вкладке **Поля** можно выбрать следующие представления. 

 |Представление|Описание|
 |--|--|
 |**Все**| Отображаются все поля для сущности|
 |**Настраиваемый**|Отображаются все только настраиваемые поля для сущности|
 |**По умолчанию**|Отображаются только стандартные поля для сущности|
<!-- TODO: What is the actual difference between All and Default? -->

## <a name="create-a-field"></a>Создание поля

Во время просмотра полей на панели команд щелкните **Добавить поле**, чтобы отобразить панель **Свойства полей**.

![Свойства поля](media/field-properties.png)


Изначально доступно только три свойства поля:

 |Свойство|Описание|
 |--|--|
 |**Отображаемое имя**|Текст, отображаемый для поля в пользовательском интерфейсе.|
 |**Название**|Уникальное имя в среде. Имя будет создано на основе введенного отображаемого имени, но его можно изменить перед сохранением. После создания поля его имя невозможно изменить, поскольку на него могут существовать ссылки в приложениях или коде. Имя будет иметь префикс настройки для параметра **Издатель CDS по умолчанию**.|
 |**Тип данных**|Указывает, как хранятся значения, а также как они форматируются в некоторых приложениях. После сохранения поля тип данных невозможно изменить, поскольку это может повлиять на данные в сущности.|

Можно настроить дополнительные параметры в зависимости от выбора значения **Тип данных**.

## <a name="field-data-types"></a>Типы данных поля

Существует множество разных типов полей, но можно создать только некоторые из них. Дополнительные сведения обо всех типах полей см. в разделе [Типы полей и типы данных полей](types-of-fields.md).

При создании поля можно выбрать следующие значения **Тип данных**:

### <a name="text"></a>Текст 

Стандартные текстовые поля могут содержать до 4000 символов. Для параметра [Максимальная длина](#max-length) по умолчанию задано низкое значение, которое можно изменить.

|Тип данных|Описание|
|--|--|
|**Текст**|Текстовое значение, которое будет отображаться в текстовом поле с одной строкой.|
|**Область текста**|Текстовое значение, которое будет отображаться в текстовом поле с несколькими строками. Если вам требуется более 4000 символов, используйте тип данных [Многострочный текст](#multi-line-field).|
|**Электронная почта**|Текстовое значение, утвержденное как адрес электронной почты и отображаемое как ссылка mailto в поле. |
|**URL-адрес**|Текстовое значение, утвержденное как URL-адрес и отображаемое как ссылка для открытия URL-адреса.|
|**Символ ценных бумаг**|Текстовое значение тикера, которое будет отображать ссылку для открытия предложения с расценками для тикера. |
|**Телефон**|Текстовое значение, утвержденное как номер телефона и отображаемое как ссылка для начала звонка с помощью Skype. |

#### <a name="max-length"></a>Максимальная длина

Поля, содержащие абсолютное максимальное число символов в зависимости от типа. Параметр **Максимальная длина** задает значение ниже максимального значения, характерного для вашей среды. Вы можете увеличить эту максимальную длину, но вы не должны понижать ее, если в системе имеются данные, которые превышают более низкое значение.

### <a name="whole-number"></a>Целое число

Эти поля содержат данные как число, но включают различные параметры представления и проверки.

|Тип данных|Описание|
|--|--|
|**Целое число**|Числовое значение, представленное в текстовом поле.|
|**Длительность**|Числовое значение, представленное как раскрывающийся список, содержащий интервалы времени. Пользователь может выбрать значение в списке или ввести целое число, представляющее количество минут.|
|**Часовой пояс**|Числовое значение, представленное как раскрывающийся список, содержащий список часовых поясов.|
|**Язык**|Числовое значение, представленное как раскрывающийся список, содержащий список языков, которые были включены в среде. Если не включены другие языки, базовый язык будет единственным вариантом для выбора. Сохраненное значение является локальным идентификатором (LCID) для языка.|


### <a name="date-time"></a>Дата и время

Используйте эти поля для хранения значений времени. Можно хранить значения, начиная с 12:00 01.01.1753.

|Тип данных|Описание|
|--|--|
|**Дата и время**|Значение даты и времени.|
|**Только дата**|Значение даты и времени, которое отображает только дату. Значение времени хранится как 12:00 (00:00:00) в системе.|

Можно также задать определенное **Поведение** для полей даты и времени в разделе **Дополнительные параметры**.

- **Часовой пояс пользователя**: отображаются значения, преобразованные в местный часовой пояс текущего пользователя. Это значение по умолчанию для новых полей.
- **Только дата**: это поведение доступно для типа **Только дата**. Отображаются значения без преобразования часового пояса. Используйте этот параметр для данных, таких как дни рождения и юбилеи.
- **Независимо от часового пояса**: отображаются значения без преобразования часового пояса.

Дополнительные сведения: [Поведение и формат поля "Дата и время"](behavior-format-date-time-field.md)

### <a name="other-data-types"></a>Другие типы данных

|Тип данных|Описание|
|--|--|
|**Валюта**|Денежное значение для всех валют, настроенных в среде. Можно установить уровень точности, указать, чтобы уровень точности зависел от определенной валюты, или использовать единую стандартную точность в организации. Дополнительные сведения: [Использование полей валюты](types-of-fields.md#using-currency-fields)|
|**Десятичное число**| Десятичное значение, содержащие до 10 знаков после запятой. Дополнительные сведения: [Использование правильного типа числового поля](types-of-fields.md#using-the-right-type-of-number)|
|**Число с плавающей запятой**|Число с плавающей запятой, содержащие до 5 знаков после запятой. Дополнительные сведения: [Использование правильного типа числового поля](types-of-fields.md#using-the-right-type-of-number)|
|**Изображение**|Отображается одно изображение в каждой записи в приложении. У каждой сущности может быть одно поле изображения. Значение **Имя**, вводимое при создании поля изображения, игнорируется. Поля изображения всегда называются EntityImage.|
|**Набор параметров с выбором нескольких вариантов**|Отображается список параметров, где можно выбрать несколько вариантов.|
|<a name="multi-line-field"></a> **Многострочный текст**|Текстовое значение, которое будет отображаться в текстовом поле с несколькими строками. Имеет ограничение не более 1 048 576 символов. Можно также указать меньшее значение [Максимальная длина](#max-length). |
|**Набор параметров**|Отображается список параметров, где можно выбрать только один вариант.|
|**Два параметра**|Отображается два параметра, где можно выбрать только один вариант. Вы выбираете, какие подписи будут отображаться для каждого параметра. Значения по умолчанию — **Да** и **Нет**.|

## <a name="save-new-field"></a>Сохранить новое поле

После настройки свойств **Отображаемое имя**, **Имя** и **Тип данных** можно нажать **Готово**, чтобы закрыть панель **Свойства поля**. 

Вы можете продолжить изменять сущность и добавить дополнительные поля или вернуться и продолжить редактирование этого поля. Поля не будут созданы, пока вы не нажмете **Сохранить сущность** для сохранения всех изменений сущности.

![Кнопка "Сохранить сущность"](media/save-entity-button.png)

Можно также нажать **Отменить**, чтобы отменить внесенные изменения.
 
## <a name="edit-a-field"></a>Изменение поля

При просмотре полей выберите поле, которое требуется изменить. Можно изменить **Отображаемое имя**, но невозможно изменить значения **Имя** и **Тип данных**, если вы сохранили изменения сущности для добавления поля.

### <a name="general-properties"></a>Общие свойства
Каждое поле имеет следующие свойства, которые можно изменить.

|Свойство|Описание|
|--|--|
|**Требуется**|Когда выбран этот параметр, запись невозможно сохранить без данных в этом поле.|
|**Для поиска**|Снимите этот флажок для полей для сущности, которые не используются.  Если поле доступно для поиска, оно отображается в окне **Расширенный поиск** и доступно при настройке представлений. Если снять этот флажок, уменьшится количество результатов, отображаемых пользователям при расширенном поиске.|
|**Описание**|Находится в разделе **Дополнительные параметры**. Введите инструкции для пользователя о назначении поля. Эти описания отображаются как подсказки для пользователя в управляемых моделью приложениях при наведении указателя мыши на метку поля.|

> [!NOTE]
> **Сделать поля обязательными**: соблюдайте осторожность при задании полей как обязательных. Пользователи не будут использовать приложение, если они не смогут сохранять записи, поскольку у них нет правильных сведений для ввода в обязательное поле. Пользователи могут вводить неправильные данные, просто чтобы сохранить запись и продолжить работу.
>
>**Задать требование динамически**: в управляемых моделью приложениях можно использовать бизнес-правила или скрипты для изменения уровня требований при изменении данных в записи в ходе работы с ней. Дополнительные сведения: [Создание бизнес-правил и рекомендаций для применения логики в форме](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)
>
>**Доступность расширенного поиска**: в настоящее время расширенный поиск доступен только для управляемых моделью приложений, использующих веб-клиент. В настоящее время расширенный поиск недоступен в клиентах единого интерфейса.

## <a name="calculated-or-rollup"></a>Вычисляемое или свертка

Можно задать настраиваемое поле как **Вычисляемое** или **Свертка**. Невычисляемые поля или поля свертки иногда называются *простыми* полями.

### <a name="calculated"></a>Вычисляемое

В вычисляемое поле можно ввести формулу для назначения значения полю. Для вычисляемого поля можно задать следующие типы данных: **Валюта**, **Дата и время**, **Только дата**, **Десятичное число**, **Длительность**, **Электронная почта**, **Язык**, **Набор параметров с выбором нескольких вариантов**, **Набор параметров**, **Текст**, **Область текста**, **Тикер**, **Часовой пояс**, **Два параметра**, **URL-адрес** и **Целое число**.

Дополнительные сведения: [Определение вычисляемых полей для автоматизации ручных расчетов](define-calculated-fields.md)

### <a name="rollup"></a>Свертка

В поле свертки можно задать функции агрегирования, которые будут выполняться периодически, чтобы задать числовое значение для поля. Для вычисляемых полей можно задать следующие типы данных: **Валюта**, **Дата и время**, **Только дата**, **Десятичное число**, **Длительность**, **Язык**, **Часовой пояс** и **Целое число**.

Дополнительные сведения: [Определение полей свертки, которые агрегируют значения](define-rollup-fields.md)

## <a name="number-field-options"></a>Параметры числового поля

Каждый тип числового поля имеет абсолютные минимальное и максимальное значения. В пределах этих абсолютных значений можно задать соответствующие значения **Минимальное значение** и **Максимальное значение**. Это необходимо для того, чтобы решение CDS для приложений проверяло значения для данных, которые должны храниться в поле.

Для типов данных **Число с плавающей запятой** и **Десятичное число** можно указать значение **Знаки после запятой**.


## <a name="option-set-field-options"></a>Параметры поля "Набор параметров"

Поля, предоставляющие набор параметров, могут включать собственный набор *локальных* параметров или ссылаться на общий набор *глобальных* параметров, которые могут использоваться в нескольких полях.

Глобальный набор параметров рекомендуется использовать при создании одного и того же набора параметров для нескольких полей. С помощью глобального набора параметров необходимо вести набор параметров только в одном месте. 

При выборе типа данных **Набор параметров с выбором нескольких вариантов** или **Набор параметров** конструктор предоставит список доступных глобальных наборов параметров на выбор, а также возможность создать **Новый набор параметров**.

![Выбор типа набора параметров](media/option-set-options.png)

Если выбрать **Новый набор параметров** по умолчанию будет создан новый глобальный набор параметров.

> [!NOTE]
> При редактировании параметров для нового глобального набора параметров значения **Отображаемое имя** и **Имя** задаются для глобального набора параметров, а не для поля. Значения по умолчанию совпадают со значениями полей, но их можно изменять при редактировании глобального набора параметров, чтобы они отличались от поля, создаваемого в данный момент.

Если требуется создать локальный набор параметров, необходимо нажать **Показать еще** и выбрать **Локальный набор параметров**.

![Локальный набор параметров](media/local-option-set.png)

> [!NOTE]
> Если вы определяете каждый набор параметров как глобальный набор параметров, список глобальных наборов параметров будет расти, и станет трудно им управлять. Если известно, что набор параметров будет использоваться только в одном месте, используйте локальный набор параметров.

[!INCLUDE [cc_remove-option-warning](../../includes/cc_remove-option-warning.md)]

## <a name="delete-a-field"></a>Удаление поля

Пользователь с ролью безопасности "Системный администратор" может удалить любые настраиваемые поля, которые не являются частью управляемого решения. При удалении поля все данные, хранящиеся в этом поле, теряются. Единственным способом восстановить данные удаленного поля — восстановить базу данных в момент времени до удаления поля.

> [!NOTE]
> Прежде чем удалить настраиваемое поле, необходимо удалить все зависимости, которые могут существовать в других компонентах решения. 

Если выбрать настраиваемое поле, которое можно удалить из списка, во время [просмотра полей](#view-fields), отобразится и включится команда **Удалить поле**.

![Удаление поля с помощью портала](media/delete-field-portal.png)

Используйте команду **Удалить поле** для удаления поля. После удаления поля необходимо сохранить изменения в сущности.

![Сохранение сущности после удаления поля](media/delete-field-portal-save-entity.png)

> [!NOTE]
> Если вы получили ошибку, связанную с зависимостями, необходимо использовать обозреватель решений для обнаружения зависимостей. Дополнительные сведения: [Проверка зависимостей полей](create-edit-field-solution-explorer.md#check-field-dependencies)

## <a name="ime-mode"></a>Режим IME

Все поля, в которые текст вводится напрямую, имеют Режим IME. Редактор методов ввода (IME) используется для восточно-азиатских языков, таких как японский. Редакторы методов ввода позволяют пользователям вводить тысячи различных символов, используемых в восточно-азиатских письменных языках, с помощью стандартной клавиатуры со 101 клавишей.



### <a name="see-also"></a>См. также  
[Создание и изменение полей для Common Data Service для приложений](create-edit-fields.md)<br />
[Создание и изменение полей для Common Data Service для приложений с помощью обозревателя решений PowerApps](create-edit-field-solution-explorer.md)<br />
[Типы полей и типы данных полей](types-of-fields.md)<br />
[Определение вычисляемых полей для автоматизации ручных расчетов](define-calculated-fields.md)<br />
[Определение полей свертки, которые агрегируют значения](define-rollup-fields.md)<br />
[Поведение и формат поля "Дата и время"](behavior-format-date-time-field.md)
