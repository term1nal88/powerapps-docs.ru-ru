---
title: Интеграция данных в Common Data Service для приложений
description: Интеграция данных из нескольких источников в Common Data Service для приложений
author: sabinn-msft
ms.service: powerapps
ms.topic: how-to
ms.component: cds
ms.date: 10/15/2018
ms.author: sabinn
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: dfbc420dfb4945cdda635e3cbaadb1acb446753b
ms.sourcegitcommit: ebd39753e2a0b60c1d8c016e38c00dd1accf5d0c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328701"
---
# <a name="integrate-data-into-common-data-service-for-apps"></a>Интеграция данных в Common Data Service для приложений

<!--note from editor: the style guide says not to use "the" in front of Common Data Service for Apps, so I'm removing that.-->

Интегратор данных (для администраторов) — это служба двусторонней интеграции, используемая для интеграции данных в Common Data Service для приложений. Он поддерживает интеграцию данных из нескольких источников, например Dynamics 365 for Finance and Operations, Dynamics 365 for Sales and SalesForce (предварительная версия), SQL (предварительная версия), в Common Data Service для приложений. Он также поддерживает интеграцию данных в Dynamics 365 for Finance и Operations и Dynamics 365 for Sales. Эта служба общедоступна с июля 2017 г.  

Мы начали с основных приложений, например Dynamics 365 for Finance and Operations и Dynamics 365 for Sales. С помощью Power Query или соединителей на основе M теперь доступна поддержка дополнительных источников, таких как SalesForce (предварительная версия) и SQL (предварительная версия), а также возможность использования более 20 источников в ближайшем будущем. 

> [!div class="mx-imgBorder"]
> ![Источник данных и место назначения](media/data-integrator/DataIntegratorP2P-new.PNG "Data source to destination")

## <a name="how-can-you-use-the-data-integrator-for-your-business"></a>Как использовать интегратор данных для вашего бизнеса?

Интегратор данных (для администраторов) также поддерживает сценарии интеграции на основе процесса, такие как "от потенциального клиента до получения прибыли", которые предоставляют прямую синхронизацию между Dynamics 365 for Finance and Operations и Dynamics 365 for Sales. Шаблоны "от потенциального клиента до получения прибыли", доступные с функцией интеграции данных, включают поток данных для учетных записей, контактов, продуктов, предложений по продажам, заказов на продажу и счетов продажи между Finance and Operations и Sales. Во время передачи данных между Finance and Operations и Sales вы можете выполнять продажи и маркетинговые кампании в Sales, а также обрабатывать выполнение заказов, используя возможность управления запасами в Finance and Operations. 

> [!div class="mx-imgBorder"]
> ![Схема "от потенциального клиента до получения прибыли"](media/data-integrator/ProspectToCash631.png "Prospect to Cash")

Интеграция схемы "от потенциального клиента до получения прибыли" позволяет продавцам обрабатывать и контролировать свои процессы продаж благодаря преимуществам Dynamics 365 for Sales, а все аспекты выполнения и выставления счетов контролируются с использованием комплексных функциональных возможностей в Finance and Operations. С интеграцией схемы "от потенциального клиента до получения прибыли" Microsoft Dynamics 365 вы получаете объединенные возможности обеих систем. 

Ознакомьтесь с видео: [Prospect to cash integration](https://www.youtube.com/watch?v=AVV9x5x-XCg) (Интеграция схемы "от потенциального клиента до получения прибыли").

Дополнительные сведения об интеграции схемы "от потенциального клиента до получения прибыли" см. в статье [Решение "Перспективный клиент в наличные деньги"](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/prospect-to-cash).

Кроме того, поддерживаются [интеграция с Field Service](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order) и [интеграция с PSA (Project Service Automation)](https://docs.microsoft.com/dynamics365/unified-operations/financials/project-management/psa-integration?toc=/fin-and-ops/toc.json) для Dynamics 365 for Finance and Operations.

## <a name="data-integrator-platform"></a>Платформа интегратора данных

Интегратор данных (для администраторов) состоит из платформы интеграции данных, готовых шаблонов, предоставленных нашими командами разработчиков приложений (например, Dynamics 365 for Finance and Operations и Dynamics 365 for Sales) и пользовательских шаблонов, созданных нашими клиентами и партнерами. Мы разработали независимую от приложений платформу, которая может масштабироваться в различных источниках. В ее основе вы создаете подключения (к конечным точкам интеграции), выбираете один из настраиваемых шаблонов с предопределенными сопоставлениями (которые вы можете дополнительно настроить), а также создаете и выполняете проект интеграции данных.  

Шаблоны интеграции служат в качестве схемы с предопределенными сущностями и сопоставлениями полей, чтобы обеспечить передачу данных от источника к месту назначения. Она также обеспечивает возможность преобразования данных перед импортом. Во многих случаях схема между исходными и целевыми приложениями может существенно различаться, а шаблон с предопределенными сущностями и сопоставлениями полей служит отличной отправной точкой для проекта интеграции.  

> [!div class="mx-imgBorder"]
> ![Платформа интеграции данных](media/data-integrator/DIPlatform.PNG "Data Integration platform")

## <a name="how-to-set-up-a-data-integration-project"></a>Как настроить проект интеграции данных

Существует три основных этапа:

1. Создание подключения (предоставление учетных данных для источников данных).

2. Создание набора подключений (определение сред для подключений, созданных на предыдущем шаге).

3. Создание проекта интеграции данных с использованием шаблона (создание или использование предопределенных сопоставлений для одной или нескольких сущностей).

Создав проект интеграции, вы получите возможность выполнять проект вручную, а также настроить обновление по расписанию на будущее. Остальная часть этой статьи фокусируется на этих трех шагах.

### <a name="how-to-create-a-connection"></a>Создание подключения

Прежде чем вы сможете создать проект интеграции данных, вы должны установить подключение для каждой системы, с которой вы собираетесь работать на портале Microsoft PowerApps. Считайте эти подключения вашими точками интеграции.

**Создание подключения**

1. Перейдите в [Центр администрирования PowerApps](https://admin.powerapps.com).

2. В области данных выберите **Подключения**, а затем **Новое подключение**.

3. Вы можете выбрать подключение из списка подключений или выполнить поиск вашего подключения.

    > [!div class="mx-imgBorder"] 
    > ![Создание подключения](media/data-integrator/CreateConnection780.png "Create connection")

4. Выбрав подключение, щелкните **Создать**. Вам будет предложено ввести учетные данные.

5. После того как вы предоставите свои учетные данные, подключение будет указано в списке подключений.

    > [!div class="mx-imgBorder"] 
    > ![Список подключений](media/data-integrator/CreateConnection1780.png "Connection list")

> [!NOTE]
> Убедитесь, что учетная запись, указанная для каждого подключения, имеет доступ к сущностям для соответствующих приложений. Кроме того, учетная запись каждого подключения может находиться в другом клиенте. 

### <a name="how-to-create-a-connection-set"></a>Создание набора подключений

Наборы подключений представляют собой набор из двух подключений, сред для подключений, информации о сопоставлении организаций и ключей интеграции, которые могут быть повторно использованы в проектах. Вы можете начать использовать набор подключений для разработки, а затем переключиться на другой для рабочей среды. Ключевым элементом информации, которая хранится с набором подключений, является сопоставление организационных единиц, например сопоставление между юридическим лицом (или компанией) Finance and Operations и организацией или подразделением Dynamics 365 for Sales. В наборе подключений можно хранить несколько сопоставлений организации.

**Создание набора подключений**

1. Перейдите в [Центр администрирования PowerApps](https://admin.powerapps.com).

2. Выберите вкладку **Интеграция данных** на панели навигации слева.

3. Выберите **Наборы подключений** и **Создать набор подключений**.

4. Укажите имя для набора подключений.
  
    > [!div class="mx-imgBorder"] 
    > ![Создание набора подключений](media/data-integrator/CreateConnectionSet1780.png "Create connection set")
  
5. Выберите подключения, созданные ранее, и подходящую среду.

6. Повторите шаги, выбирая следующее подключение (как источник и место назначения без определенного порядка).

7. Укажите сопоставление организации и подразделения (при интеграции между системами Finance and Operations и Sales).
  
    > [!NOTE]
    > Вы можете указать несколько сопоставлений для каждого набора подключений.
  
8. Заполнив все поля, нажмите кнопку **Создать**.

9. Вы увидите набор подключений, который вы только что создали, на странице списка наборов подключений.
    
    > [!div class="mx-imgBorder"] 
    > ![Список наборов подключений](media/data-integrator/CreateConnectionSet2780.png "Connection set list")

Ваш набор подключений готов к использованию в различных интеграционных проектах.

### <a name="how-to-create-a-data-integration-project"></a>Как создать проект интеграции данных

Проекты позволяют передавать данные между системами. Проект содержит сопоставления для одной или нескольких сущностей. Сопоставления показывают соотношения между полями.

**Создание проекта интеграции данных**

1. Перейдите в [Центр администрирования PowerApps](https://admin.powerapps.com).

2. Выберите вкладку **Интеграция данных** на панели навигации слева.

3. На вкладке **Проекты** выберите **Новый проект** в правом верхнем углу.

    > [!div class="mx-imgBorder"] 
    > ![Создание проекта](media/data-integrator/CreateNewProject780.png "Create project")

4. Укажите имя для проекта интеграции.

5. Выберите один из доступных шаблонов (или [создайте собственный шаблон](#how-to-customize-or-create-your-own-template)). Таким образом, мы переносим сущность Products из Finance and Operations в Sales.

    > [!div class="mx-imgBorder"] 
    > ![Выбор шаблона для создания проекта](media/data-integrator/CreateNewProjectSelectTemplate780.png "Select template to create new project")

6. Нажмите кнопку **Далее** и выберите набор подключений, созданный ранее (или [создайте набор](#how-to-create-a-connection-set)).

7. Убедитесь, что вы выбрали правильный набор, подтвердив имена подключений и среды.

    > [!div class="mx-imgBorder"] 
    > ![Создание набора подключений](media/data-integrator/CreateNewProjectSelectConnectionSet780.png "Create a new connection set")

8. Нажмите кнопку **Далее** и выберите сопоставления юридического лица и подразделения.

    > [!div class="mx-imgBorder"] 
    > ![Создание сопоставления юридического лица](media/data-integrator/CreateNewProjectLegalEntityMapping780.png "Create new legal entity mapping")

9. Просмотрите и примите уведомление о конфиденциальности и дайте согласие в следующем окне.

10. Продолжайте создавать проект, а затем запустите проект, что, в свою очередь, приводит к его выполнению.

    > [!div class="mx-imgBorder"] 
    > ![Запуск проекта](media/data-integrator/RunProject780.png "Run project")

    На этом экране появится несколько вкладок — **Планирование** и **История выполнений**, а также нескольких кнопок — **Добавить задачу**, **Обновить сущности** и **Расширенный запрос**, которые будут описаны далее в этой статье.

### <a name="execution-history"></a>История выполнений

История выполнений показывает журнал всех исполнений проекта с именем проекта, меткой времени выполнения и состоянием выполнения, а также количеством операций upsert или ошибок.

-   Пример журнала выполнений проекта.

    > [!div class="mx-imgBorder"] 
    > ![Журнал выполнений проекта](media/data-integrator/ExecutionHistorySuccessFailures4780.png "Project execution history")

-   Пример успешного выполнения, показывающий состояние завершения с количеством  \# операций upsert. (Обновление или вставка — это логика, по которой имеющаяся запись обновляется или вставляется новая запись.)

    > [!div class="mx-imgBorder"] 
    > ![Успешное выполнение](media/data-integrator/ExecutionHistorySuccess2780.png "Execution success")

-   В случае сбоев выполнения вы можете перейти к основной причине.

    Ниже приведен пример ошибки с ошибками проверки проекта. В этом случае ошибка проверки проекта связана с отсутствием полей источника в сопоставлениях сущностей.

    > [!div class="mx-imgBorder"] 
    > ![Сбой выполнения в журнале](media/data-integrator/ExecutionHistoryFailures3780.png "Execution history failure")

-   Если выполнение проекта находится в состоянии "ОШИБКА", попытка выполнения будет повторена при следующем запланированном запуске.

-   Если выполнение проекта находится в состоянии "ПРЕДУПРЕЖДЕНИЕ", вам необходимо исправить проблемы в источнике. Попытка выполнения будет повторена при следующем запланированном запуске.

    В любом случае вы также можете вручную выполнить повторный запуск.

### <a name="how-to-set-up-a-schedule-based-refresh"></a>Как настроить обновление по расписанию

В данный момент поддерживается два типа выполнения или записи:

-   Запись вручную (выполнение и обновление проекта вручную).

-   Операции записи по расписанию (автоматическое обновление).

После создания проекта интеграции вы получаете возможность запускать его вручную или настроить записи по расписанию, благодаря чему можно настроить автоматическое обновление проектов.

**Настройка операций записи по расписанию**

1. Перейдите в [Центр администрирования PowerApps](https://admin.powerapps.com).

2. Вы можете планировать проекты двумя разными способами.<br>

    Выберите проект и перейдите на вкладку **​​Планирование** или запустите планировщик со страницы списка проектов, щелкнув многоточие рядом с именем проекта.

    > [!div class="mx-imgBorder"] 
    > ![Операции записи по расписанию](media/data-integrator/Schedulebasedwrites780.png "Schedule-based writes")

3. Установите переключатель **Повторять каждые**. Заполнив все поля, нажмите кнопку **Сохранить расписание**.

    > [!div class="mx-imgBorder"] 
    > ![Операции записи по расписанию](media/data-integrator/Schedulebasedwrites1780.png "Schedule-based writes")

Вы можете установить частоту в 1 минуту или задать определенное количество часов, дней, недель или месяцев. Обратите внимание, что следующее обновление не начнется, пока не выполнится предыдущая задача проекта.

Кроме того, обратите внимание, что в разделе "Уведомления" вы можете выбрать уведомления об оповещениях по электронной почте, в которых вы получаете сведения о выполнении задач, завершившихся с предупреждениями или не выполнившихся из-за ошибок. Вы можете предоставить несколько получателей, включая группы, через запятую.

> [!div class="mx-imgBorder"] 
> ![Уведомление по электронной почте](media/data-integrator/EmailNotification780.png "Email notification")

> [!NOTE]
> - Сейчас можно в любое время запланировать 50 проектов интеграции для всех клиентов с платной подпиской. Однако вы можете создать еще больше проектов и запустить их интерактивно.
Для клиентов с пробной версией есть дополнительное ограничение: 50 выполнений на запланированный проект.
> - Хотя вы можете запланировать запуск проектов каждую минуту, это может привести к серьезным нагрузкам на приложения и понизить общую производительность. Пользователям настоятельно рекомендуется проверять выполнения проектов в условиях реальных нагрузок и оптимизировать производительность путем уменьшения частоты обновлений.
В рабочих средах не рекомендуется запускать больше пяти проектов в минуту на клиент.

## <a name="customizing-projects-templates-and-mappings"></a>Настройка проектов, шаблонов и сопоставлений 

Шаблон используется для создания проекта интеграции данных. Шаблон обобщает процесс перемещения данных, что, в свою очередь, помогает бизнес-пользователю или администратору ускорить интеграцию данных из источников в место назначения и снижает общую нагрузку и стоимость. Бизнес-пользователь или администратор может начинать работу с готового шаблона, опубликованного корпорацией Майкрософт или ее партнером, а затем дополнительно настроить его перед созданием проекта. Затем можно сохранить проект как шаблон и поделиться с вашей организацией и/или создать проект. 

Шаблон предоставляет источник, назначение и направление для передачи данных. Это нужно учитывать при настройке или создании собственного шаблона.  

Вы можете настроить проекты и шаблоны следующими способами:

-   Настроить сопоставления полей.

-   Настроить шаблон, добавив сущность по своему усмотрению.

### <a name="how-to-customize-field-mappings"></a>Настройка сопоставлений полей

**Создание набора подключений**

1. Перейдите в [Центр администрирования PowerApps](https://admin.powerapps.com).

2. Выберите проект, для которого вы хотите настроить сопоставления полей, а затем выберите стрелку между полями источника и места назначения.

    > [!div class="mx-imgBorder"] 
    > ![Сопоставление полей](media/data-integrator/FieldMapping780.png "Field mapping")

3. Откроется окно сопоставления, в котором вы можете добавить новое сопоставление, нажав кнопку **Добавить сопоставление** в верхнем правом углу, или **настроить имеющиеся сопоставления** в выпадающем списке.

    > [!div class="mx-imgBorder"] 
    > ![Настройка сопоставления полей](media/data-integrator/FieldMappingCustomize780.png "Field mapping customize")

4. После настройки сопоставления полей нажмите кнопку **Сохранить**.

### <a name="how-to-customize-or-create-your-own-template"></a>Как настроить или создать собственный шаблон 

**Создание собственного шаблона**

1. Перейдите в [Центр администрирования PowerApps](https://admin.powerapps.com).

2. Определите источник, назначение и направление потока для нового шаблона.

3. Создайте проект, выбрав имеющийся шаблон, который соответствует выбранному источнику, назначению и направлению потока.

<!--note from editor: Didn't we create the project in step 3? Step 4 tells us to create the project.-->

4. Выбрав соответствующие соединения, создайте проект.

5. Прежде чем сохранить или запускать проект, в правом верхнем углу нажмите кнопку **Добавить задачу**.

    > [!div class="mx-imgBorder"] 
    > ![Настройка шаблона](media/data-integrator/CustomizeTemplate780.png "Customize template")

    Откроется диалоговое окно **Добавление задачи**.

6. Укажите значимое имя задачи и добавьте сущности источника и назначения по вашему выбору.

    > [!div class="mx-imgBorder"] 
    > ![Настройка шаблона и добавление задачи](media/data-integrator/CustomizeTemplateAddtask75.png "Customize template add task")

7. В раскрывающемся списке показаны все сущности источника и назначения.

    > [!div class="mx-imgBorder"] 
    > ![Настройка шаблона и добавление задачи](media/data-integrator/CustomizeTemplateAddtask175.png "Customize template add task")

    В этом случае была создана задача для синхронизации сущности User из SalesForce с сущностью Users в Common Data Service для приложений.

    > [!div class="mx-imgBorder"] 
    > ![Настройка шаблона и добавление задачи](media/data-integrator/CustomizeTemplateAddtask275.png "Customize template add task")

8. Затем вы увидите новую задачу и можете удалить исходную.

    > [!div class="mx-imgBorder"] 
    > ![Настройка шаблона и добавление задачи](media/data-integrator/CustomizeTemplateAddtask3780.png "Customize template add task")

9. Вы только что создали шаблон для извлечения данных сущности User из SalesForce в Common Data Service. Нажмите кнопку **Сохранить**, чтобы сохранить настройки.

10. Следуйте инструкциям по настройке сопоставления полей для этого нового шаблона. Вы может запустить этот проект или сохранить в качестве шаблона на странице **Список проектов**.

    > [!div class="mx-imgBorder"] 
    > ![Настройка и сохранение шаблона](media/data-integrator/CustomizeTemplateSaveAsTemplate780.png "Customize template save as template")

11. Укажите имя и описание и/или поделитесь с другими в своей организации.

    > [!div class="mx-imgBorder"] 
    > ![Настройка и сохранение шаблона](media/data-integrator/CustomizeTemplateSaveAsTemplate175.png "Customize template save as template")

## <a name="advanced-data-transformation-and-filtering"></a>Расширенная трансформация и фильтрация данных 

Благодаря поддержке Power Query теперь мы предлагаем расширенную фильтрацию и преобразование исходных данных. Power Query позволяет пользователям изменять данные в соответствии с их потребностями с помощью простого в использовании, привлекательного интерфейса пользователя. Вы можете сделать это поэтапно. 

### <a name="how-to-enable-advanced-query-and-filtering"></a>Как включить расширенные запросы и фильтрацию

**Настройка расширенной фильтрации и преобразования данных**

1. Перейдите в [Центр администрирования PowerApps](https://admin.powerapps.com).

2. Выберите проект, в который вы хотите включить расширенный запрос, а затем выберите **Расширенный запрос**.

    > [!div class="mx-imgBorder"] 
    > ![Выбор расширенного запроса](media/data-integrator/EnablePQ1780.png "Select Advanced Query")

3. Вы получите предупреждение о том, что включение расширенного запроса является односторонним и его нельзя отменить. Нажмите кнопку **ОК** для продолжения и затем выберите стрелку сопоставления источника и назначения.

    > [!div class="mx-imgBorder"] 
    > ![Предупреждение](media/data-integrator/EnablePQ275.png "Warning")

4. Теперь откроется ​​знакомая страница сопоставления сущностей со ссылкой для запуска расширенного запроса и фильтрации.

    > [!div class="mx-imgBorder"] 
    > ![Расширенный запрос и фильтрация](media/data-integrator/EnablePQ3780.png "Advanced Query and Filtering")

5. Выберите **ссылку**, чтобы запустить интерфейс расширенных запросов и фильтрации, который предоставляет исходные поля данных в столбцах типа Microsoft Excel.

    > [!div class="mx-imgBorder"] 
    > ![Расширенный запрос и фильтрация](media/data-integrator/EnablePQ4780.png "Advanced Query and Filtering")

6. В верхнем меню вы увидите несколько параметров преобразования данных, таких как **Добавить условный столбец**, **Создать дубликат столбца** и **Извлечь**.

    > [!div class="mx-imgBorder"] 
    > ![Добавление столбца](media/data-integrator/EnablePQAddColumn75.png "Add column")

7. Вы можете щелкнуть любой столбец правой кнопкой, чтобы увидеть дополнительные параметры, например **Удалить столбцы**, **Удалить дубликаты** и **Разделить столбец**.

    > [!div class="mx-imgBorder"] 
    > ![Щелчок столбцы правой кнопкой мыши](media/data-integrator/EnablePQAddColumn180.png "Right-click column")

8. Вы также можете фильтровать, щелкая каждый столбец и используя фильтры типа Excel.

    > [!div class="mx-imgBorder"] 
    > ![Включение фильтрации](media/data-integrator/EnablePQFiltering80.png "Enable filtering")

<!--note from editor: I don't see an "otherwise" in the screenshot. I see "else".-->

9. Значения по умолчанию можно преобразовать с использованием условного столбца. Для этого из раскрывающегося списка **Добавление столбца** выберите **Добавить условный столбец** и введите имя нового столбца. Заполните поля **Затем** и **В противном случае** значениями по умолчанию, используя любое поле и значение для **Если** и **равно**

    > [!div class="mx-imgBorder"] 
    > ![Добавление условного столбца](media/data-integrator/EnablePQDefaultValueTransforms2780.png "Add conditional column")

10. Обратите внимание на предложение **each** в редакторе *fx* вверху.

    > [!div class="mx-imgBorder"] 
    > ![Редактор fx](media/data-integrator/EnablePQDefaultValueTransforms2780.png "fx editor")

11. Исправьте предложение **each** в редакторе *fx* и нажмите кнопку **ОК**.

    > [!div class="mx-imgBorder"] 
    > ![Исправление предложения each](media/data-integrator/EnablePQDefaultValueTransforms5780.png "Fix the each clause")

<!--note from editor: The sentence that starts with "Additionally" is confusing - not sure where the "same steps" fit in.-->

12. Каждый раз при внесении изменений можно применить шаг. Вы можете увидеть применяемые шаги на правой панели (прокрутите вниз, чтобы увидеть последний шаг). Вы можете отменить шаг, если вам нужно его отредактировать. Кроме того, вы можете перейти в расширенный редактор, щелкнув правой кнопкой мыши **QrySourceData** на левой панели вверху, чтобы просмотреть язык M, который выполняется в фоновом режиме, таким же образом.

    > [!div class="mx-imgBorder"] 
    > ![Расширенный редактор](media/data-integrator/EnablePQDefaultValueTransforms4780.png "Advanced editor")

13. Нажмите кнопку **ОК**, чтобы закрыть интерфейс расширенного запроса и фильтрации, а затем на странице задачи сопоставления выберите созданный столбец в качестве источника для соответствующего создания сопоставления.

    > [!div class="mx-imgBorder"] 
    > ![Выбор нового столбца](media/data-integrator/EnablePQDefaultValueTransforms6780.png "Pick new column")

С дополнительными сведениями о Power Query ознакомьтесь в [документации по Power Query](https://docs.microsoft.com/power-query/).
