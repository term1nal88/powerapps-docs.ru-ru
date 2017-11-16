---
title: "Настройка списков для интеграции SharePoint Online с PowerApps, Microsoft Flow и Power BI | Документация Майкрософт"
description: "В этом примере мы настроим списки SharePoint, чтобы использовать их в качестве источника данных для приложений, потоков, отчетов и панелей мониторинга."
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/12/2017
ms.author: mblythe
ms.openlocfilehash: 35c6e2b7ddadc0ff907ce34986accdd11a794dd4
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="set-up-lists-for-sharepoint-online-integration-with-powerapps-microsoft-flow-and-power-bi"></a>Настройка списков для интеграции SharePoint Online с PowerApps, Microsoft Flow и Power BI
**Примечание.** Эта статья входит в серию руководств по использованию PowerApps, Microsoft Flow и Power BI с SharePoint Online. Обязательно просмотрите [вводные сведения](sharepoint-scenario-intro.md), чтобы получить общее представление о процессе и скачать связанные файлы.

Хотя в SharePoint доступно много функций для обеспечения общего доступа и совместной работы, сейчас мы сосредоточимся на одной из них — [списках SharePoint](https://support.office.com/article/Introduction-to-lists-0A1C3ACE-DEF0-44AF-B225-CFA8D92C52D7). Список — это коллекция данных с возможностью совместного использования с участниками группы и другими пользователями сайта. Сначала мы рассмотрим возможности списков, используемых в этом сценарии, а затем создадим их на сайте SharePoint Online.

## <a name="step-1-understand-the-lists"></a>Шаг 1. Общие сведения о списках
Первый список — **Project Requests** (Запросы проекта), в который пользователь, запрашивающий проекты, добавляет запрос. Пользователь, утверждающий проекты, просматривает запрос, а затем утверждает или отклоняет его.

| **Столбец в списке** | **Тип данных** | **Примечания** |
| --- | --- | --- |
| Title |Однострочный текст |Столбец по умолчанию, используемый для имени проекта. |
| Description |Однострочный текст | |
| ProjectType |Однострочный текст |Значения: новое оборудование, обновленное оборудование, новое программное обеспечение, обновленное программное обеспечение. |
| RequestDate |Дата | |
| Requestor |Однострочный текст | |
| EstimatedDays |Номер |Позволяет сравнить результаты оценки запрашивающего с результатами руководителя проекта и фактическими результатами. |
| Approved |Однострочный текст |Значения: в ожидании, да, нет. |

**Примечание.** Также используется столбец **ID**, который создается в SharePoint. Он скрыт по умолчанию. Для простоты мы будем использовать базовые типы данных. Но в реальных приложениях могут использоваться более сложные типы, например **пользователь или группа** для столбца **Requestor**. Сведения о типах данных, поддерживаемых в PowerApps, см. в статье [Подключение Microsoft PowerApps к SharePoint](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/#known-issues).

Второй список — **Project Details** (Сведения о проекте), в котором отслеживаются сведения обо всех утвержденных проектах (например, о назначенном руководителе проекта).

| **Столбец в списке** | **Тип данных** | **Примечания** |
| --- | --- | --- |
| Title |Однострочный текст |Столбец по умолчанию, используемый для имени проекта. |
| RequestID |Номер |Совпадает со значением в столбце **ID** списка **Project Requests**. |
| ApprovedDate |Дата | |
| Состояние |Однострочный текст |Значения: не начато, выполняется, завершено. |
| ProjectedStartDate |Дата |Рассчитанная руководителем дата начала проекта. |
| ProjectedEndDate |Дата |Рассчитанная руководителем дата завершения проекта. |
| ProjectedDays |Номер |Рабочие дни; как правило, вычисляются, но не в нашем примере. |
| ActualDays |Номер |Для завершенных проектов. |
| PMAssigned |Однострочный текст |Руководитель проекта. |

## <a name="step-2-create-and-review-the-lists"></a>Шаг 2. Создание и просмотр списков
Для работы с этим примером нам нужно создать два списка SharePoint и заполнить их примерами данных. Мы покажем, как это сделать, создав список и вставив примеры данных. Убедитесь, что у вас есть файлы Excel из [скачиваемого пакета](https://aka.ms/o4ia0f).

**Примечание.** На этом этапе используйте Internet Explorer.

### <a name="create-the-lists"></a>Создание списка
1. В Internet Explorer на сайте SharePoint нажмите кнопку **Создать**, а затем щелкните **Список**.
   
    ![Создание списка SharePoint](./media/sharepoint-scenario-setup/01-01-01-new-list.png)
2. Введите имя "Project Requests" и нажмите кнопку **Создать**.
   
    ![Выбор имени для нового списка](./media/sharepoint-scenario-setup/01-01-02-create-list.png)
   
    Список **Project Requests** создан со столбцом **Title** по умолчанию.
   
    ![Список "Project Requests"](./media/sharepoint-scenario-setup/01-01-03-initial-list.png)

### <a name="add-columns-to-the-list"></a>Добавление столбцов в список
1. Щелкните ![Значок создания элемента](./media/sharepoint-scenario-setup/icon-new.png) и выберите **Single line of text** (Однострочный текст).
   
    ![Поле однострочного текста](./media/sharepoint-scenario-setup/01-01-04-add-column.png)
2. Введите имя "Description" и нажмите кнопку **Создать**.
   
    ![Создание столбца описания](./media/sharepoint-scenario-setup/01-01-05-description-column.png)
3. Повторите шаги **1** и **2** для других столбцов в списке:
   
   1. **Single line of text** (Однострочный текст) > "ProjectType"
   2. **Date** (Дата) > "RequestDate"
   3. **Single line of text** (Однострочный текст) > "Requestor"
   4. **Number** (Число) > "EstimatedDays"
   5. **Single line of text** (Однострочный текст) > "Approved"

### <a name="copy-data-into-the-list"></a>Копирование данных в список
1. Нажмите кнопку **Быстрое редактирование**.
   
    ![Быстрое редактирование списка](./media/sharepoint-scenario-setup/01-01-06-quick-edit.png)
2. Выделите ячейки в сетке.
   
    ![Список со всеми столбцами](./media/sharepoint-scenario-setup/01-01-07-empty-grid.png)
3. Откройте книгу project-requests.xlsx и выделите все данные (без заголовков).
   
    ![Таблица Excel списка "Project Requests"](./media/sharepoint-scenario-setup/01-01-08-excel-table.png)
4. Скопируйте данные, вставьте их в сетку в SharePoint и нажмите кнопку **Готово**.
   
    ![Список, заполненный данными](./media/sharepoint-scenario-setup/01-01-09-full-grid.png)
5. Повторите создание и копирование для списка "Project Details", используя книгу project-details.xlsx. Сведения об именах и типах данных столбцов см. в таблице Project Details в разделе [Шаг 1. Общие сведения о списках](#step-1-understand-the-lists).

## <a name="step-3-update-connections-to-samples---optional"></a>Шаг 3. Обновление подключения к примерам (необязательно)
Как отмечено во введении, мы включили в [скачиваемый пакет](https://aka.ms/o4ia0f) два примера приложений и пример отчета. Это руководство можно пройти и без этих примеров. Но если вы решили их использовать, вам нужно обновить подключения к спискам SharePoint. Так примеры приложений смогут использовать как источник данных *ваши* списки вместо наших.

### <a name="update-connections-for-the-sample-apps"></a>Обновление подключения для примеров приложений
1. Откройте файл **project-management-app.msapp** в PowerApps Studio.
2. Щелкните **Allow** (Разрешить), чтобы служба PowerApps могла использовать SharePoint.
3. На ленте откройте вкладку **View** (Представление) и щелкните **Data sources** (Источники данных).
   
    ![Источники данных в PowerApps](./media/sharepoint-scenario-setup/01-03-01-data-sources.png)
4. В области справа нажмите кнопку с многоточием (**...**) рядом с элементом **Project Details** (Сведения о проекте), а затем щелкните **Remove** (Удалить).
   
    ![Удаление источника данных "Project Details"](./media/sharepoint-scenario-setup/01-03-02-remove.png)
5. В области справа нажмите кнопку **Add data source** (Добавить источник данных).
   
    ![Добавление источника данных](./media/sharepoint-scenario-setup/01-03-03-add.png)
6. Щелкните **New connection** (Создать подключение).
   
    ![Создание подключения](./media/sharepoint-scenario-setup/01-03-03a-new-connection.png)
7. Щелкните **SharePoint** и нажмите кнопку **Connect** (Подключить).
   
    ![Подключение к SharePoint](./media/sharepoint-scenario-setup/01-03-03b-sharepoint.png)
8. Введите URL-адрес сайта SharePoint Online, который содержит созданные списки, и нажмите кнопку **Go** (Перейти).
   
    ![URL-адрес сайта SharePoint](./media/sharepoint-scenario-setup/01-03-03c-sharepoint-url.png)
9. Выберите список **Project Details** (Сведения о проекте), а затем нажмите кнопку **Connect** (Подключить).
   
    ![Список "Project Details" (Сведения о проекте)](./media/sharepoint-scenario-setup/01-03-03d-project-details.png)
   
    На вкладке **Data sources** (Источники данных) справа отобразится созданное подключение.
   
    ![Источники данных](./media/sharepoint-scenario-setup/01-03-03e-data-sources.png)
10. В области справа нажмите кнопку с многоточием (**...**) рядом с элементом **Project Details**, а затем щелкните **Refresh** (Обновить).
    
    ![Обновление источника данных "Project Details"](./media/sharepoint-scenario-setup/01-03-02-remove.png)
11. В правом верхнем углу щелкните ![Значок запуска приложения](./media/sharepoint-scenario-setup/icon-run-arrow.png) для запуска приложения. Убедитесь, что подключения работают должным образом.
12. Повторите шаги в этом разделе с файлом **project-requests-app.msapp**, используя список **Project Requests** (Запросы проекта).

### <a name="update-connections-for-the-sample-report"></a>Обновление подключений для примера отчета
1. Откройте файл **project-analysis.pbix** в Power BI Desktop.
2. На ленте откройте вкладку **Главная**, щелкните **Изменить запросы** и выберите **Параметры источника данных**.
   
    ![Элемент "Изменить запросы"](./media/sharepoint-scenario-setup/01-03-04-edit-queries.png)
3. Нажмите кнопку **Изменить источник**.
   
    ![Окно "Параметры источника данных"](./media/sharepoint-scenario-setup/01-03-05-settings.png)
4. Введите URL-адрес сайта SharePoint Online и нажмите кнопку **ОК**.
   
    ![URL-адрес списка SharePoint](./media/sharepoint-scenario-setup/01-03-06-list-url.png)
5. В Power BI Desktop под лентой отобразится баннер, который позволяет применить изменения и перенести данные из нового источника. Нажмите кнопку **Применить изменения**.
   
    ![Применение изменений запроса](./media/sharepoint-scenario-setup/01-03-07-apply.png)
6. Войдите с помощью корпоративной учетной записи (учетная запись для доступа к SharePoint Online) и нажмите кнопку **Подключить**.
   
    ![Подключение к SharePoint Online](./media/sharepoint-scenario-setup/01-03-08-connect.png)

## <a name="next-steps"></a>Дальнейшие действия
Следующий этап в этой серии руководств — [создание приложения для обработки запросов проекта](sharepoint-scenario-generate-app.md).

