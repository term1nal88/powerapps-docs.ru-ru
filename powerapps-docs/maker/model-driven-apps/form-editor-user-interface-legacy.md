---
title: Обзор пользовательского интерфейса редактора форм управляемого моделью приложения для PowerApps | MicrosoftDocs
description: Познакомьтесь с пользовательским интерфейсом редактора форм для редактирования форм в PowerApps
keywords: Формы; Основная форма; приложения единого интерфейса; Dynamics 365 for Customer Engagement
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.assetid: 146f8035-4fcd-4572-8e71-4270cd150495
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="overview-of-the-model-driven-app-form-editor-user-interface"></a>Обзор пользовательского интерфейса редактора форм управляемого моделью приложения

В редакторе форм команды отображаются на трех вкладках: **Файл**, **Домашняя страница** и **Вставка**.  

- [Вкладка "Файл"](#file-tab)
- [Вкладка "Домашняя страница"](#home-tab)
- [Вкладка "Вставка"](#insert-tab)
  
Редактор форм разделен на три области: **Навигация**, **Текст** и **Обозреватель**.  

> [!div class="mx-imgBorder"] 
> ![Пользовательский интерфейс редактора форм](media/form-user-interface.png)
  
**Переходы**  
Область навигации находится с левой стороны и используется для управления доступом к связанным сущностям или для добавления ссылок на URL-адреса, которые должны отображаться в основной области формы. Чтобы изменить навигацию, сначала необходимо выбрать команду **Навигация** в группе **Выбрать** на вкладке **Домашняя страница**.

Параметры навигации в основных формах представлены на панели навигации, но при этом для управления доступными параметрами навигации в панели навигации используются те же данные. Дополнительные сведения: [Изменение навигации](use-the-form-editor-legacy.md)  


**Текст** <br>
Область текста находится в центре и используется для управления макетом формы. Элементы формы можно выбирать и перетаскивать, чтобы менять их положение. Дважды щелкните элемент, чтобы открыть свойства элемента. 

По умолчанию в основных формах "Обращение", "Контакт" и "Организация" в первом разделе под вкладкой **Сводка** отображается форма карточки организации или контакта, имеющая тип **Экспресс-форма**. Для настраиваемых сущностей этот раздел недоступен по умолчанию. Можно вставить новый раздел и добавить в него экспресс-форму. В форме карточки отображается максимум пять полей. Помимо полей, отобразить какие-либо другие элементы управления на синей плитке невозможно, даже если экспресс-форма их содержит. 
 
>[!NOTE] 
> Чтобы сохранить формат карточки (как показано на следующем рисунке) рекомендуется не перемещать экспресс-форму в какой-либо другой раздел формы.

> [!div class="mx-imgBorder"] 
> ![Формат карточки](media/card-format.png)
   
Дополнительные сведения: [Создание и изменение экспресс-форм](create-edit-quick-view-forms.md)  
 
-   Чтобы добавить поле, выберите его в **обозревателе полей** и перетащите в раздел.  
  
    -   Чтобы добавить элемент, который не является полем, выберите требуемую позицию для этого элемента и добавьте его с помощью соответствующей команды на вкладке **Вставка**.  
  
    -   Чтобы удалить элемент, выберите его и используйте команду **Удалить** в группе **Правка** на вкладке **Домашняя страница**.  
  
    -   Чтобы изменить значение **Заголовок** или **Нижний колонтитул** формы, необходимо сначала выбрать соответствующую команду в группе **Выбрать** на вкладке **Домашняя страница**.  
  
**Обозреватель**  
Область обозревателя находится с правой стороны, и содержимое области зависит от контекста.  
  
При выборе **Текст**, **Заголовок** или **Нижний колонтитул** в группе **Выбрать** на вкладке **Домашняя страница** отобразится **Обозреватель полей**. Используйте **Обозреватель полей**, чтобы перетащить поля, которые требуется отобразить в разделе в форме или в заголовке либо нижнем колонтитуле. Можно включить одни и те же поля в форму несколько раз. Используйте кнопку **Создать поле**, чтобы быстро создать новое поле.  
  
При выборе **Навигация** в группе **Выбрать** вкладки **Домашняя страница** отобразится **Обозреватель отношений**. Перетащите все отношения в одну из групп в области навигации. Невозможно добавить одно и то же отношение дважды. Отношения доступны на основе их настроек. Если в настройках указано, что отношение не должно отображаться, оно не будет отображаться в разделе **Обозреватель отношений**. Сведения о том, как настраивать параметры отображения по умолчанию для отношений, см. в разделе [Элемент области переходов для основной сущности](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity).
  
Можно использовать кнопки **Создать 1:N** и **Создать N:N**, чтобы быстро добавить новые отношения сущностей.  

## <a name="file-tab"></a>Вкладка "Файл"

Выберите вкладку **Файл**, чтобы добавить или просмотреть следующие параметры:

- **Новое действие** Добавить новое действие
- **Новая запись** Добавить новую запись
- **Средства** Использовать такие параметры, как импорт данных, поиск повторяющихся данных и мастер массового удаления
- **Параметры** Изменить параметры отображения по умолчанию в целях персонализации решения по умолчанию и управления шаблонами электронной почты
    - Общие сведения
    - Синхронизация
    - Действия
    - Список типов
    - Шаблоны электронной почты
    - Подписи электронной почты
    - Электронная почта
    - Конфиденциальность
    - Языки
- Справка
- Закрыть


## <a name="home-tab"></a>Вкладка "Домашняя страница"  
 На вкладке **Домашняя страница** отображаются команды, перечисленные в следующей таблице:

> [!div class="mx-imgBorder"] 
> ![Вкладка "Домашняя страница"](media/home-tab.png)

|Группа|Команда|Описание|
|-----------|-------------|-----------------| 
|**Сохранить**|**Сохранить** **(Ctrl+S)**|Сохранение формы.|
||**Сохранить как**|Создание копии данной формы с другим именем.|
||**Сохранить и закрыть**|Сохранение формы и закрытие редактора форм.|
||**Опубликовать**|Публикация формы. Дополнительные сведения: "Публикация настроек"|
|**Изменить**|**Изменить свойства**|Изменение свойств выбранного элемента в тексте.<br /><br /> См. следующие разделы в зависимости от выбранного элемента:<br /><br /> -   [Свойства вкладки](tab-properties-legacy.md)<br />-   [Свойства раздела](section-properties-legacy.md)<br />-   [Общие свойства поля](common-field-properties-legacy.md)<br />-   [Специальные свойства поля](special-field-properties-legacy.md)<br />-  [Свойства вложенной сетки](sub-grid-properties-legacy.md)<br />-   [Свойства элемента управления экспресс-формы](quick-view-control-properties-legacy.md)|
||**Удалить**|Удалить выбранный элемент.|
||**Отменить** **(CTRL+Z)**|Отменить предыдущее действие.|
||**Вернуть** **(CTRL+Y)**|Повтор предыдущего действия.|
|**Выбрать**|**Текст**|Изменение основной части формы.|
||**Верхний колонтитул**|Изменить заголовок формы.|
||**Нижний колонтитул**|Изменить нижнюю часть формы.|
||**Переходы**|Изменить навигацию по форме.<br /><br /> Дополнительные сведения: [Изменение навигации](use-the-form-editor-legacy.md)
|**Форма**|**Бизнес-правила**|Просмотр, изменение или создание новых бизнес-правил в обозревателе бизнес-правил. **Примечание.** Для интерактивных форм поддерживается только область "Сущность" и "Все формы".<br /><br /> Дополнительные сведения: [Создание и изменение бизнес-правил](create-business-rules-recommendations-apply-logic-form.md)|
||**Свойства формы**| Дополнительные сведения: [Свойства формы](form-properties-legacy.md)|  
||**Предварительная версия**|Используйте для просмотра, как выглядит форма после ее публикации. Можно также использовать предварительный просмотр, чтобы проверить скрипты, связанные с событиями из.|         
||**Включить роли безопасности**|Используется этот параметр для настройки ролей безопасности, которые будут иметь доступ к формам. Дополнительные сведения: [Управление доступом к формам](control-access-forms.md) **Важно.** При создании новой формы только роли безопасности "Системный администратор" и "Специалист по настройке систем" будут иметь доступ к форме. Необходимо разрешить доступ другим ролям безопасности, прежде чем пользователи смогут использовать ее.|  
||**Показать зависимости**|Просмотр компонентов решения, которые зависят от этой формы, и компонентов решения, которые необходимы для ее использования. |  
||**Управляемые свойства**|Команда управляемых свойств имеет два свойства, **Настраиваемый** и **Можно удалить**. Если для этих свойств установить значение false, форму будет невозможно настроить или удалить после включения формы в решение, экспорта решения как управляемого решения и импорта управляемого решения в другую среду. Дополнительные сведения: [Управляемые свойства](../common-data-service/solutions-overview.md#managed-properties)| 
|**Восстановить**|**Объединить формы**|Если это применимо, этот параметр позволяет объединить эту форму с формой из предыдущей версии формы Dynamics 365|
  

## <a name="insert-tab"></a>Вкладка "Вставка"  
> [!div class="mx-imgBorder"] 
> ![Вкладка "Вставка"](media/insert-tab.png)
 
На вкладке Вставка отображаются команды, представленные в следующей таблице.

|Группа|Команда|Описание|
|-----------|-------------|-----------------| 
||**Раздел**|Добавление раздела на выбранную вкладку. Можно добавить раздел числом столбцов от одного до четырех.<br /><br /> В интерактивные формы также можно вставить справочную панель. Справочная панель также добавляется в качестве раздела в форму "Основная — интерактивное взаимодействие". По умолчанию раздел "Справочная панель" добавляется в формы "Обращение", "Организация", "Контакт", а также формы настраиваемых сущностей.<br /><br /> Дополнительные сведения: [Свойства раздела](section-properties-legacy.md)|  
|**3 вкладки**|**Три столбца**|Вставка вкладки из трех столбцов равной ширины.<br /><br /> Дополнительные сведения: [Свойства вкладки](tab-properties-legacy.md)|  
||**Три столбца**|Вставка вкладки из трех столбцов с более широким средним столбцом.|  
|**2 вкладки**|**Два столбца**|Вставка вкладки из двух столбцов с более широким правым столбцом.|  
||**Два столбца**|Вставка вкладки из двух столбцов с более широким левым столбцом.|  
||**Два столбца**|Вставка вкладки из двух столбцов равной ширины.|  
|**1 вкладка**|**Один столбец**|Вставка вкладки из одного столбца.|  
|**Элемент управления**|**Вложенная сетка**|Форматирование вложенной сетки и вставка ее в форму.<br /><br /> Дополнительные сведения: [Свойства вложенной сетки](sub-grid-properties-legacy.md)|  
||**Разделитель**|Вставить пустую строку.|  
||**Экспресс-форма**|Вставка экспресс-формы.<br /><br /> Дополнительные сведения: [Свойства элемента управления экспресс-формы](quick-view-control-properties-legacy.md)|  
||**Веб-ресурс**|Вставка веб-ресурса для встраивания содержимого из других местоположений в одну страницу.<br /><br /> Дополнительные сведения: [Свойства веб-ресурсов](web-resource-properties-legacy.md)|  
||**Интернет-кадр**|Можно добавить интернет-кадр в форму для интеграции содержимого из другого веб-сайта в форму.| 
||**Временная шкала**|Вставка элемента управления временной шкалы в форму. В этом элементе управления отображается хронология действий, связанных с сущностью в форме.|  
||**Ссылка навигации**|С помощью этого параметра можно вставить ссылку в навигацию формы.|  
||**Таймер**|Вставка элемента управления "Таймер" в форму сущности для отслеживания времени по SLA. Дополнительные сведения: [Добавление элемента управления "Таймер"](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-timer-control-case-form-track-time-against-sla)|
||**Поиск в базе знаний**|Вставка элемента управления "Поиск", с помощью которого пользователи смогут выполнять поиск статей базы знаний. Дополнительные сведения: [Элемент управления поиска в базе знаний](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-knowledge-base-search-control-forms)|  
||**Помощник по отношениям**|С помощью этого параметра можно вставить элемент управления помощника по отношениям в форму.|

>[!Note] 
>Следующие компоненты не поддерживаются в основных формах:<br> <ul> <li>Карты Bing <br><li>Yammer <br><li>Ленты новостей <br> </li> </ul>


## <a name="next-steps"></a>Дальнейшие действия

[Использование основной формы и ее компонентов](use-main-form-and-components.md)  