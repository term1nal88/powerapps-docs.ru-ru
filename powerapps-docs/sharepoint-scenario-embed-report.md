---
title: "Внедрение отчета о проекте Power BI в SharePoint Online | Документация Майкрософт"
description: "В этой задаче мы внедрим отчет Power BI на тот же веб-сайт SharePoint Online, где размещены два наши списка."
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
ms.openlocfilehash: 481e6d13cce7624cf46cadbf78f877fdfb9fd481
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2018
---
# <a name="embed-the-power-bi-project-report-in-sharepoint-online"></a>Внедрение отчета о проекте Power BI в SharePoint Online
> [!NOTE]
> Эта статья входит в серию руководств по использованию PowerApps, Microsoft Flow и Power BI совместно с SharePoint Online. Обязательно просмотрите [вводные сведения](sharepoint-scenario-intro.md), чтобы получить общее представление о процессе и скачать связанные файлы.

Последняя задача этого сценария — внедрение отчета Power BI на тот же веб-сайт SharePoint Online, где размещены два наши списка. В Power BI доступны разные способы внедрения. Недавно мы добавили возможность интеграции непосредственно в страницы SharePoint для мобильных и веб-представлений.

Используя этот подход, Power BI внедряет отчет в качестве веб-части, предоставляет соответствующие права доступа для пользователей и позволяет переходить от внедренного отчета к отчету на веб-сайте powerbi.com. Мы создадим в Power BI ссылку для внедрения, а затем используем эту ссылку на создаваемой странице. Дополнительные сведения о внедрении см. в статье [Внедрение с помощью веб-части отчетов в SharePoint Online](https://powerbi.microsoft.com/documentation/powerbi-service-embed-report-spo) (особо рекомендуется прочесть раздел "Требования").

## <a name="step-1-generate-an-embed-link"></a>Шаг 1. Создание ссылки для внедрения
1. Войдите в Power BI и в левой области навигации выберите имя отчета.
   
    ![Перейдите к отчету](./media/sharepoint-scenario-embed-report/08-01-01-reports.png)
2. Выберите **Внедрить в SharePoint Online**.
   
    ![Внедрение в SharePoint Online](./media/sharepoint-scenario-embed-report/08-01-02-embed-spo.png)
3. Скопируйте ссылку для внедрения из диалогового окна в файл и нажмите кнопку **Закрыть**. Мы воспользуемся этой ссылкой после создания страницы SharePoint.
   
    ![Ссылка для внедрения для SharePoint](./media/sharepoint-scenario-embed-report/08-01-03-embed-url.png)

## <a name="step-2-embed-the-report"></a>Шаг 2. Внедрение отчета
1. Войдите в SharePoint и выберите **Содержимое сайта**.
   
    ![Содержимое сайта SharePoint](./media/sharepoint-scenario-embed-report/08-01-04-site-contents.png)
2. Можно просто включить отчет в домашнюю страницу команды, но мы создадим для него отдельную страницу. Нажмите кнопку **Создать**, а затем выберите параметр **Страница**.
   
    ![Новая страница SharePoint](./media/sharepoint-scenario-embed-report/08-01-05-new-page.png)
3. Введите имя страницы, например "Анализ проекта".
4. Нажмите ![Значок плюса](./media/sharepoint-scenario-embed-report/icon-plus.png) и выберите **Power BI**.
   
    ![Добавление части страницы Power BI](./media/sharepoint-scenario-embed-report/08-01-06-add-page-part.png)
5. Нажмите кнопку **Добавить отчет**.
   
    ![Добавление отчета](./media/sharepoint-scenario-embed-report/08-01-07-add-report.png)
6. В области справа скопируйте URL-адрес для внедрения в поле **Ссылка на отчет Power BI**. Присвойте параметрам **Показать область фильтров** и **Показать область навигации** значение **Вкл**.
   
    ![Параметры отчета](./media/sharepoint-scenario-embed-report/08-01-08-report-settings.png)
7. Теперь отчет внедрен в страницу. Нажмите кнопку **Опубликовать**, чтобы отчет стал доступным для всех, у кого есть доступ к базовому отчету.
   
    ![Завершение внедрения отчета](./media/sharepoint-scenario-embed-report/08-01-09-report-complete.png)

## <a name="step-3-grant-access-to-the-report"></a>Шаг 3. Предоставление доступа к отчету.
Если вы, как и рекомендуется, используете группы Office 365, убедитесь, что пользователи, которым необходим доступ, являются членами рабочей области группы в службе Power BI. Так они смогут просматривать содержимое группы. См. дополнительные сведения о [создании групп в Power BI](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-group-in-power-bi).

На этом мы завершим работу в Power BI для текущего сценария. Мы начали с извлечения данных из списков SharePoint в Power BI и завершили полный цикл внедрением отчета Power BI назад в SharePoint.

## <a name="next-steps"></a>Дальнейшие действия
Следующий шаг в этой серии руководств — [сквозное выполнение созданного нами рабочего процесса](sharepoint-scenario-summary.md).

