---
title: Свойства специальных полей управляемых моделью приложений для основных форм в PowerApps | MicrosoftDocs
description: Познакомьтесь со специальными свойствами полей для основных форм
Keywords: Main forms; Special field properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 6ad7e43c-b6a1-48c4-9dfb-ed830142a841
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="overview-of-model-driven-app-special-field-properties"></a>Обзор специальных свойств полей управляемых моделью приложений

 Все поля имеют свойства, перечисленные в разделе [Общие свойства полей](common-field-properties-legacy.md), однако некоторые поля, такие как поле объема обслуживания, имеют дополнительные свойства, которые можно открыть из основной формы сущности обращения.  

![диалоговое-окно-специальных-свойств](media/special-properties.png)
  
<a name="BKMK_LookupFieldProperties"></a>  
 
## <a name="lookup-field-properties"></a>Свойства поля поиска  
  
> [!NOTE]
>  Параметры, описанные в следующей таблице, доступны только для полей поиска одной сущности.  
  
|Раздел|Свойство|Описание|  
|-------------|--------------|-----------------|  
|**Фильтрация связанных записей**|**Показывать только записи, где**|Если это свойство включено, к записям, отображаемым при поиске пользователем какой-либо записи, будет применяться дополнительный фильтр. Это позволит получить более точные результаты поиска при настройке значения поиска.<br /><br /> По умолчанию эта функция отключена.<br /><br /> В таблице, приведенной за этой, перечислены комбинации отношений, возможных при фильтрации связанных записей.*<br /><br /> Первый список заполняется потенциальными отношениями, которые можно использовать для фильтрации поиска. Выберите один.<br /><br /> Второй список затем заполняется отношениями, объединяющими связанную сущность (выбранную в первом списке) с целевой сущностью. Выберите один.<br /><br /> Установите флажок **Позволять пользователям отключать фильтр**, чтобы дать пользователям возможность выключить определенный здесь фильтр.<br /><br /> Когда пользователи выбирают пункт **Поиск дополнительных записей** при установке значение для поиска, они видят это диалоговое окно.<br /><br /> ![поиск-дополнительных-записей](media/crm-ua-v-8-1-look-up-more-records.png) <br /><br /> Если при настройке поля поиска установлен флажок **Разрешить пользователям отключать фильтр**, пользователям отображается флажок, позволяющий выключить фильтр.  Это позволит им просматривать более широкий диапазон записей. Снимите флажок **Разрешить пользователям отключать фильтр**, чтобы пользователи видели только ограниченный диапазон записей, определенный этим фильтром.|  
|**Дополнительные свойства**|**Отобразить поле поиска в диалоговом окне поиска**|Можно отключить отображение поля поиска в диалоговом окне поиска.|  
||**Представление умолчанию**|Это представление используется для фильтрации результатов встроенного поиска и задания представления по умолчанию в диалоговом окне поиска при выборе пользователями параметра **Поиск дополнительных записей**.<br /><br /> Представления по умолчанию также определяет, какие поля включаются во встроенный поиск.<br /><br /> При использовании поисков, в которых можно выбрать только один тип сущности, полями, отображаемыми во встроенном поиске, будут первые два поля, включенные в представление по умолчанию. В этом примере **Основной телефон** и **Электронная почта** — это первые два столбца в представлении по умолчанию, настроенном для поиска организации.<br /><br /> В случае системных поисков, допускающих несколько типов сущностей, отображаются первые два столбца представления поиска сущности.|  
||**Выбор представления**|Доступно три параметра на выбор:<br /><br /> -   **Выкл.**: Пользователи не могут выбрать другое представление.<br />-   **Показать все представления**. Доступны все представления.<br />-   **Показать выбранные представления**. При выборе этого параметра можно использовать клавишу CTRL и указатель мыши, чтобы выбрать представления для отображения. Выбор представления поиска для сущности невозможно отменить.|  
  
 **\*Возможные комбинации отношений**  
  
|Отношение первого списка|Отношение второго списка|Доступные?|  
|-----------------------------|------------------------------|----------------|  
|N:1 (многие к одному)|1:N (один ко многим)|Да|  
|N:1 (многие к одному)|N:1 (многие к одному)|Да|  
|N:1 (многие к одному)|N:N (многие ко многим)|Да|  
|1:N (один ко многим)|1:N (один ко многим)|Да|  
|1:N (один ко многим)|N:1 (многие к одному)|No|  
|1:N (один ко многим)|N:N (многие ко многим)|No|  
|N:N (многие ко многим)|1:N (один ко многим)|Да|  
|N:N (многие ко многим)|N:1 (многие к одному)|No|  
|N:N (многие ко многим)|N:N (многие ко многим)|No|  
  
<a name="BKMK_TwoOptionProperties"></a>   

### <a name="two-option-field-properties"></a>Свойства полей с двумя параметрами  
 На вкладке форматирования поля с двумя параметрами имеют следующие варианты форматирования:  
  
- **Два переключателя**. Для элемента управления с подписями. Можно выбрать только один из них.  
  
- **Флажок**. Один флажок, чтобы установить значение true; в противном случае — значение false.  
  
- **Список**. Раскрывающийся список, содержащий оба значения.  
  
<a name="BKMK_MultipleLinesOfTextProperties"></a>   

### <a name="multiple-lines-of-text-field-properties"></a>Свойства полей с несколькими строками текста  
 Поля с несколькими строками текста или одной строкой текста, использующие формат `Text Area`, имеют свойство **Макет строк**. С помощью этого свойства можно указать значение для параметра **Число строк** или выбрать параметр **Автоматически развертывать для заполнения доступной области окна**.  

## <a name="next-steps"></a>Дальнейшие действия

[Использование основной формы и ее компонентов](use-main-form-and-components.md)
