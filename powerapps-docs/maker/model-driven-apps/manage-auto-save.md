---
title: Отключение автосохранения в управляемых моделью приложениях с помощью PowerApps | MicrosoftDocs
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
author: Mattp123
ms.assetid: 2e7f75dd-7a3f-4716-b995-b626929c0501
caps.latest.revision: 14
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="disable-auto-save-in-a-model-driven-app"></a>Отключение автосохранения управляемого моделью приложении

Функция автосохранения помогает пользователям приложения сконцентрироваться на работе, не задумываясь о сохранении данных в форме. Большинство людей оценит отсутствие необходимости явно сохранять данные при каждом обновлении записи, однако в некоторых организациях могут быть пользовательские настройки, предназначенные для явного сохранения. Для этих организаций можно выбрать вариант применения автосохранения.  
  
<a name="BKMK_HowAutoSaveWorks"></a>   

## <a name="how-auto-save-works"></a>Как работает автосохранение  
 По умолчанию все основные формы для [обновленных сущностей и классических сущностей](create-design-forms.md#updated-versus-classic-entities) поставляются с включенным автосохранением. После создания записи (изначально сохраняемой) любые изменения в форме будут автоматически сохраняться через 30 секунд после внесения изменения. Если изменения в форму не вносятся, то при открытой форме автоматического сохранения не происходит. После внесения изменений снова происходит 30-секундный отсчет перед включением автоматического сохранения. Поле, редактируемое в настоящее время другим пользователем, не включено в автосохранение. Если кто-то еще обновил ту же запись, пока вы ее редактируете, эти изменения будут извлечены и отображены в форме во время автосохранения.  
  
 С включенным автосохранением кнопка "Сохранить" отображается только для первоначального сохранения записи. После создания записи кнопка "Сохранить" на панели команд не отображается, однако в нижнем правом углу видна кнопка ![Кнопка автоматического сохранения](media/auto-save-icon.png "Кнопка автоматического сохранения"), показывающая, имеются ли какие-либо несохраненные изменения. Этот элемент управления также отображается, если автосохранение отключено.  
  
 Можно выбрать эту кнопку, чтобы сохранить запись и немедленно обновить данные в форме. Если автосохранение включено, запись будет сохраняться всякий раз при уходе из записи или закрытии отдельного окна с записью. Нет необходимости в кнопке **Сохранить и закрыть**, которая появляется в формах для необновляемых сущностей.  
  
<a name="BKMK_AutoSave"></a>   
## <a name="should-you-disable-auto-save"></a>Следует отключить автосохранение?  
 При наличии подключаемых модулей, рабочих процессов и скриптов форм, исполняемых при сохранении записи, они будут выполняться всякий раз при автосохранении. Это может привести к нежелательному поведению, если соответствующие расширения не были предназначены для работы с автосохранением. Включено ли автосохранение или нет, подключаемые модули, рабочие процессы и скрипты форм необходимо адаптировать для поиска конкретных изменений, они не должны исполняться для каждого события сохранения беспорядочно.  
  
 Если аудит настроен для сущности, каждое сохранение расценивается как отдельное обновление. Если пользователь задумался над формой с несохраненными изменениями более 30 секунд, дополнительная запись появится только в случае добавления данных после автосохранения. При наличии отчетов, которые зависят от аудита данных и расценивают каждое сохранение как индивидуальное "прикосновение" к записи, можно отменить увеличение частоты таких "прикосновений". Если вы используете этот подход, следует помнить, что поведение отдельных пользователей делает его ненадежным независимо от того, включено автосохранение или нет.  
  
<a name="BKMK_DisableAutoSaveOrg"></a>   
## <a name="disable-auto-save-for-the-organization"></a>Отключение автосохранения в организации  
 Если определено, что автосохранение вызовет проблемы с используемыми расширениями, можно отключить его в вашей организации. Отсутствует возможность отключения автосохранения для отдельных сущностей или форм.  
  
1. Перейдите в **[Параметры](advanced-navigation.md#settings)** > **Администрирование**.  
  
2.  Выберите **Системные параметры**.  
  
3.  Для параметра **Включение автосохранения для всех форм** выберите **Нет**.  
  
<a name="BKMK_DisalbleAutoSaveForm"></a>   
## <a name="disable-auto-save-for-a-form"></a>Отключение автосохранения для формы  
 Если требуется отключить автосохранение для конкретных форм сущностей, можно добавить код в событие `OnSave` в сущности.  
  
> [!NOTE]
>  Автосохранение будет отключено для формы, но данные все же будут сохранены, когда пользователь выберет кнопку ![Кнопка автоматического сохранения](media/auto-save-icon.png "Кнопка автоматического сохранения") в нижнем правом углу. Если пользователь попытается покинуть или закрыть форму с измененными данными, появится запрос на сохранение изменений, только после этого форму можно будет покинуть или закрыть.  
  
1.  На сайте [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) выберите **Управляемые моделью** (в левой нижней части панели навигации).  

    ![Режим разработки, управляемый моделью](../model-driven-apps/media/model-driven-switch.png)

2.  Разверните **Данные**, выберите **Сущности**, выберите требуемую сущность, затем выберите вкладку **Формы**.  
  
3.  Откройте форму, который требуется изменять.  
  
4.  Создайте веб-ресурс JavaScript и добавьте его к форме:  
  
    1.  В редакторе форм в группе **Форма** выберите **Свойства формы**.  
  
    2.  На вкладке **События** в разделе **Библиотеки форм** выберите **Добавить**.  
  
    3.  В диалоговом окне **Поиск записи** выберить **Создать**.  
  
    4.  Введите следующие сведения в форму веб-ресурсов.  
  
        |||  
        |-|-|  
        |**Название**|preventAutoSave|  
        |**Отображаемое имя**|Запрет автосохранения|  
        |**Тип**|Скрипт (JScript)|  
  
    5.  Рядом с полем **Тип** выберите **Текстовый редактор**.  
  
    6.  В поле **Источник** вставьте следующий код:  
  
        ```javascript  
        function preventAutoSave(econtext) {  
            var eventArgs = econtext.getEventArgs();  
            if (eventArgs.getSaveMode() == 70 || eventArgs.getSaveMode() == 2) {  
                eventArgs.preventDefault();  
            }  
        }  
  
        ```  
  
    7.  Выберите **ОК**, чтобы закрыть текстовый редактор.  
  
    8.  Выберите **Сохранить**, чтобы сохранить веб-ресурс, а затем закройте окно веб-ресурса.  
  
    9. В диалоге **Поиск записи** будет выбран новый веб-ресурс, только что созданный вами. Выберите **Добавить**, чтобы закрыть диалоговое окно.  
  
5.  Настройка события OnSave:  
  
    1.  В поле **Свойства формы** в разделе **Обработчики событий** установите **Событие** в **При сохранении**.  
  
    2.  Выберите **Добавить**.  
  
    3.  В окне **Свойства обработчика** задайте для раздела **Библиотека** веб-ресурс, добавленный в предыдущем шаге.  
  
    4.  Введите `preventAutoSave` в поле **Функция**. Ввод осуществляется с учетом регистра. Не используйте кавычки.  
  
    5.  Убедитесь, что установлен флажок **Включено**.  
  
    6.  Установите флажок **Передача контекста выполнения в качестве первого параметра**.  
  
        > [!IMPORTANT]
        >  В противном случае скрипт не заработает.  
  
         Диалог **Свойства обработчика** должен выглядеть так. Префикс настройки: "new_" может меняться в зависимости от префикса пользовательской настройки, заданного для издателя по умолчанию для вашей организации.  
  
 ![Обработчик событий OnSave, позволяющий предотвратить автоматическое сохранение в Dynamics 365](media/prevent-auto-save-script.png "Обработчик событий OnSave, позволяющий предотвратить автоматическое сохранение в Dynamics 365")  
  
    7.  Выберите **ОК**, чтобы закрыть диалог **Свойства обработчика**.  
  
    8.  При наличии других обработчики событий для события `OnSave` используйте зеленые стрелки для перемещения данного обработчика вверх.  
  
6. Выберите **ОК**, чтобы закрыть диалог **Свойства формы**.  
  
7. Выберите **Сохранить и закрыть**, чтобы закрыть форму.  
  
8. В обозревателе решений выберите **Опубликовать все настройки**.  
  
 После применения этого сценария к событию `OnSave` при редактировании пользователем записи с использованием этой формы сообщение **несохраненные изменения** отображается в нижнем правом углу формы, как если бы автосохранение не было отключено. Однако это сообщение не будет отправлено, пока пользователь не выберет кнопку ![Кнопка автоматического сохранения](media/auto-save-icon.png "Кнопка автоматического сохранения") рядом с ним.  
  
## <a name="next-steps"></a>Дальнейшие действия  
 [Создание и разработка форм](create-design-forms.md)      

 