---
title: "Описание настраиваемого соединителя с помощью Postman | Документация Майкрософт"
description: "Создание коллекции Postman Collection для регистрации настраиваемых соединителей"
services: 
suite: powerapps
documentationcenter: 
author: archnair
manager: anneta
editor: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/28/2017
ms.author: archanan
ms.openlocfilehash: fd060ff873ee376b7ca886f721d360372c1d13ed
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2018
---
# <a name="describe-a-custom-connector-with-postman"></a>Описание настраиваемого соединителя с помощью Postman
[Postman](https://www.getpostman.com/) — это средство, позволяющее ускорить и облегчить разработку API. В этом руководстве показано, как создать коллекцию Postman, которую затем можно использовать для быстрого создания [настраиваемых соединителей](register-custom-api.md) в PowerApps.

## <a name="prerequisites"></a>Технические условия
* Установите [приложение Postman](https://www.getpostman.com/apps).

## <a name="create-a-postman-collection"></a>Создание коллекции Postman Collection
Давайте создадим коллекцию Postman Collection для [API анализа текста](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api) Azure Cognitive Services. Этот API определяет язык, тональность и ключевые фразы в тексте, который вы передаете.

1. Первым этапом создания коллекции Postman Collection является создание запроса. При создании запроса можно задать команду HTTP, URL-адрес запроса, параметры запроса или пути, заголовки и текст. Дополнительные сведения см. в разделе [отправки запросов](https://www.getpostman.com/docs/requests) документации по Postman. Для конечной точки API определения языка задайте значения следующим образом:
   
    ![Запрос Postman](./media/postman-collection/request.png)
   
    Сведения об используемых параметрах и значениях:
   
   | Параметр | Значение |
   | --- | --- |
   | Команда |POST |
   | URL-адрес запроса |https://westus.api.cognitive.microsoft.com/text/analytics/v2.0/languages |
   | Параметры |numberOfLanguagesToDetect |
   | Авторизация |No Auth |
   | Заголовки |Ocp-Apim-Subscription-Key = <your subscription key> <br/>Content-Type = application/json |
   | Текст |<code>{<br/>&nbsp;&nbsp;&nbsp;"documents": [<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": "1",<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"text": "Hello World"<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;]<br/>}<code> |
2. Щелкните **Отправить** для отправки запроса и получения ответа.
3. Щелкните **Сохранить** для сохранения запроса в коллекции Postman Collection.
   
    ![Ответ Postman](./media/postman-collection/request-response-save.png)
4. Укажите **имя** и **описание** запроса в диалоговом окне **Save Request** (Cохранение запроса). Эти значения будут использоваться в настраиваемом соединителе.
   
    ![Сохранение коллекции Postman Collection](./media/postman-collection/save-request-note.png)
   
    Вы также можете сохранить ответ в запросе. В настоящее время настраиваемые соединители поддерживают только один ответ на запрос. При сохранении нескольких ответов на запрос используется только первый из них.
   
    ![Сохранение ответа Postman](./media/postman-collection/save-response.png)
5. Продолжайте создание коллекции Postman Collection, формируя и сохраняя другие запросы и ответы.
6. Когда вы создадите коллекцию Postman Collection для всех запросов и ответов, экспортируйте ее.
   
    ![Экспорт коллекции Postman](./media/postman-collection/export.png)
7. Выберите **Collection v1** (Коллекция в. 1) в качестве формата экспорта.
   
    ![Экспорт коллекции Postman](./media/postman-collection/export2.png)

Теперь вы можете использовать коллекцию Postman Collection для создания настраиваемого соединителя в PowerApps. Дополнительные сведения см. в статье [Регистрация настраиваемых интерфейсов API в PowerApps](register-custom-api.md). 

