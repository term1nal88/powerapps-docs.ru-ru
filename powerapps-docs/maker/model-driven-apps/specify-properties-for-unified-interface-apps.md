---
title: Указание свойств для управляемых моделью приложений единого интерфейса в PowerApps | MicrosoftDocs
description: 'Узнайте, как настраивать элемент управления сетки для приложения'
keywords: ''
ms.date: 06/06/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 3ecea4a7-0d18-4ccd-9609-3a62179e9e1b
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 0
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="specify-properties-for-model-driven-unified-interface-apps"></a>Указание свойств для управляемых моделью приложений единого интерфейса

В платформе единого интерфейса используются принципы гибкого веб-дизайна для оптимального просмотра и взаимодействия на экранах любых размеров и любой ориентации. С приложениями, управляемыми моделью, которые используют платформу единого интерфейса элемент управления сетки (представления) является отзывчивым. Как размер контейнера уменьшается, — например, на телефонах и окнах просмотра меньшего размера, — сетка преобразуется в список. 

Элемент управления "Сетка только для чтения" указывает, как должна перегруппировываться сетка на экранах различных размеров. Если вы как создатель приложения работаете с приложением единого интерфейса, вы можете настроить элемент управления "Сетка только для чтения" и его свойства для настраиваемых сеток и списков.
- Свойство **Форма карточки**. Используйте форму карточки для списков вместо шаблона списка по умолчанию. Формы карточки предоставляют больше сведений для элементов списка, чем шаблон списка по умолчанию.
- Свойство **Поведение перегруппировки**. Этот параметр используется для указания, требуется ли перегруппировывать сетку в список или нет.

## <a name="allow-grid-to-reflow-into-list"></a>Разрешить перегруппировку сетки в список

Добавление элемента управления "Сетка только для чтения" в ваш список элементов управления позволяет настроить следующие возможности: 
- Разрешение перегруппировку сетки в список на небольших экранах, таких как мобильные устройства.
- Указание режима отображения как только сетка или только список.  

1. Откройте [обозреватель решений](advanced-navigation.md#solution-explorer).
2. В области навигации разверните **Сущности**, выберите соответствующую сущность (такую как **Организация** или **Контакт**), затем на вкладке **Элементы управления** выберите **Добавить элемент управления**.

    ![Открытие окна добавления элемента управления](media/UnifiedInterface_ReadOnlyGrid_AddControl.png "Открытие окна добавления элемента управления")

3. Выберите **Сетка только для чтения** в списке элементов управления, затем выберите **Добавить**.

    Элемент управления добавляется в список доступных элементов управления.
   
    ![Выбор элемента управления](media/UnifiedInterface_ReadOnlyGrid_SelectControl.png "Выбор элемента управления")
    
4. Выберите устройства (**Интернет**, **Телефон** или **Планшет**), для которых необходимо сделать сетку доступной только для чтения.

    ![Выбор типа устройства](media/UnifiedInterface_ReadOnlyGrid_SelectDevice.png "Выбор типа устройства")

5. Настройте свойство **Форма карточки**.

    Свойство формы карточки можно использовать для отображения элементов списка вместо шаблона списка по умолчанию. Формы карточки предоставляют больше сведений для элементов списка, чем шаблон списка по умолчанию.    

    a. Выберите значок карандаша рядом с пунктом **Форма карточки**.

    ![Изменение формы карточки](media/UnifiedInterface_ReadOnlyGrid_CardForm.png "Изменение формы карточки")

    b.  Выберите типы **Сущность** и **Форма карточки**.

    ![Свойства формы карточки](media/UnifiedInterface_ReadOnlyGrid_CardFormProperties.png "Свойства формы карточки")

    c. Выберите **OK**.
6. Настройка свойства **Поведение перегруппировки**. 
    
    a. Выберите значок карандаша рядом с пунктом **Поведение перегруппировки**.

    ![Изменение поведения перегруппировки](media/UnifiedInterface_ReadOnlyGrid_EditReflow.png "Изменение поведения перегруппировки")

    b. Выберите тип перегруппировки сетки в раскрывающемся списке **Связать со статическими параметрами**.
    |Тип перегруппировки|Описание|
    |--------------|--------------------|
    |**Перегруппировка**|Позволяет отображать сетку в режиме списка в зависимости от наличия места на экране.|
    |**Только сетка**|Ограничивает перегруппировку сетки в список, даже если на экране недостаточно места.|
    |**Только список**|Отображается только в виде списка, даже если на экране достаточно места для отображения в виде сетки.|
    
     ![Свойства поведения перегруппировки](media/UnifiedInterface_ReadOnlyGrid_ReflowProperties.png "Свойства поведения перегруппировки")

    c. Выберите **OK**.


7.  Сохраните и опубликуйте изменения. 


## <a name="conditional-image"></a>Условное изображение
Можно отображать настраиваемый значок вместо значения в списке и установить логику, используемую для их выбора на основе значений в столбцах, используя JavaScript. Дополнительные сведения об условных изображениях см. в разделе [Отображение настраиваемых значков вместо значений в представлениях списка](../common-data-service/display-custom-icons-instead.md).

## <a name="next-steps"></a>Дальнейшие действия
[Создание и редактирование представления](create-edit-views.md)
