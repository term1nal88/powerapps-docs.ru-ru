---
title: 'Создание отношений сущностей N:N (многие-ко-многим) в Common Data Service для приложений с помощью обозревателя решений | MicrosoftDocs'
description: 'Узнайте, как создавать отношения многие-ко-многим'
ms.custom: ''
ms.date: 05/29/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-nn-many-to-many-entity-relationships-in-common-data-service-for-apps-using-solution-explorer"></a>Создание отношений сущностей N:N (многие-ко-многим) в Common Data Service для приложений с помощью обозревателя решений

Обозреватель решений предоставляет один способ создания и изменения отношений N:N (многие-ко-многим) для Common Data Service для приложений.

[Портал PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) позволяет настроить самые распространенные параметры, но некоторые параметры можно задать только с помощью обозревателя решений. Дополнительные сведения:
- [Создание отношений сущностей N:N (многие-ко-многим)](create-edit-nn-relationships.md)
- [Создание отношений сущностей "многие-ко-многим" в Common Data Service для приложений с помощью портала PowerApps](create-edit-nn-relationships-portal.md)

  
## <a name="open-solution-explorer"></a>Откройте обозреватель решений

Часть имени любого настраиваемого отношения — это префикс настройки. Это настраивается с использованием издателя решений для решения, в котором выполняется работа. Если важен префикс настройки, убедитесь, что вы работаете с неуправляемым решением, префикс настройки в котором — тот, который нужен для данной сущности. Дополнительные сведения: [Изменение префикса издателя решения](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entity-relationships"></a>Просмотр отношений сущностей

В обозревателе решений разверните раздел **Сущности** и выберите сущность. В данной сущности выберите **Отношения N:N**.

![Просмотр отношений сущностей N:N](media/view-nn-entity-relationships-solution-explorer.png)

## <a name="create-relationships"></a>Создание отношений

Во время [просмотра отношений сущности](#view-entity-relationships) выберите **Создать отношение "многие ко многим"** на панели команд.

> [!NOTE]
> Если эта команда недоступна, сущность не имеет право создавать настраиваемое отношение.

![Форма создания отношения "многие ко многим"](media/new-nn-entity-relationship-form-solution-explorer.png)

В группе **Другая сущность** в поле **Имя сущности** выберите сущность, с которой требуется создать отношение. При этом будут заполнены поля **Имя** и **Имя сущности** отношения в группе **Определение отношения**.

Можно нажать ![кнопку "Сохранить отношение сущностей](media/save-entity-icon-solution-explorer.png), чтобы сущность и продолжить редактирование. Дополнительные сведения: [Редактирование отношений](#edit-relationships)

> [!NOTE]
> Если значение **Имя** или **Имя сущности отношения** уже существует в системе, при сохранении отобразится сообщение об ошибке. Измените значения, чтобы они стали уникальными, и повторите попытку.

## <a name="edit-relationships"></a>Редактирование отношений

Во время [просмотра отношений сущности](#view-entity-relationships) выберите сущность, которую следует изменить. 

> [!NOTE]
> Издатель управляемого решения поможет предотвратить настройки отношений, являющиеся частью его решения.

После создания отношения можно изменить следующие свойства отношений сущностей.

> [!IMPORTANT]
> После того как вы изменяете эти свойства, необходимо опубликовать настройки, прежде чем они вступят в силу в управляемых моделью приложениях.

### <a name="edit-display-options"></a>Изменение параметров отображения

Как для **Текущая сущность**, так и для **Другая сущность**, можно изменять поля параметра отображения, которые определяют, как связанные сущности отображаются для управляемых моделью приложений.

|Поле|Описание|
|--|--|
|**Параметры отображения**|Способ отображения списка связанных сущностей. Дополнительные сведения: [Параметры отображения](#display-options)|
|**Пользовательская метка**|Укажите локализуемый текст, который будет использоваться вместо имени во множественном числе при выборе значения **Использовать специальные метки** для параметра **Параметр отображения**.|
|**Область отображения**|Выберите один из доступных вариантов группирования для отображения этого списка. Возможные варианты: **Сведения** (для группы *Общее*), **Маркетинг**, **Продажи** и **Сервис**. |
|**Порядок отображения**|Управление тем, будет ли элемент навигации включен в выбранную область отображения. Диапазон доступных номеров начинается с 10 000. Элементы области навигации с меньшим значением будут стоять в списке выше других отношений.|

<!-- TODO: Not sure whether Display Area or Display Order are still used anymore. Might only be used in the Outlook client?-->

#### <a name="display-options"></a>Параметры отображения

Доступны следующие параметры отображения:

|Параметр|Описание|
|--|--|
|**Не отображать**|Не отображать связанные сущности для этого отношения.|
|**Использовать специальные метки**|Если этот параметр выбран, поле **Пользовательская метка** включено, и вы можете указать локализуемый текст, который необходимо использовать вместо имени во множественном числе.|
|**Использовать имя во множественном числе**|Использование отображаемого имени во множественном числе, определенного для связанной сущности.|

### <a name="searchable"></a>Для поиска

Можно скрыть отношение от операции **Расширенный поиск** в управляемых моделью приложениях, задав в поле **Для поиска** значение **Нет**.

## <a name="delete-relationships"></a>Удаление отношений

Во время [просмотра отношений](#view-entity-relationships) выберите отношение сущностей, которое требуется удалить, и выберите команду ![Команда "Удалить"](media/delete.gif).

При удалении отношения будет удалена созданная сущность отношения. Все данные, соединяющие сущности с помощью отношения, будут утрачены.

### <a name="see-also"></a>См. также

[Создание отношений сущностей N:N (многие-ко-многим)](create-edit-nn-relationships.md)<br />
[Создание отношений сущностей "многие-ко-многим" в Common Data Service для приложений с помощью портала PowerApps](create-edit-nn-relationships-portal.md)<br />
[Создание и изменение отношений сущностей 1:N ("один-ко-многим") или N:1 ("многие-к-одному")](create-edit-1n-relationships.md)