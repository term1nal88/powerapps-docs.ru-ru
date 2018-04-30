---
title: Краткое руководство по созданию первого приложения на основе модели с нуля в PowerApps | Документация Майкрософт
description: Сведения о создании простого приложения на основе модели
documentationcenter: ''
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 04/18/2018
ms.author: matp
ms.openlocfilehash: ad11ce81544095c5730e326325b4b5bf6b136e93
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-build-your-first-model-driven-app-from-scratch"></a>Краткое руководство. Создание первого приложения на основе модели с нуля
Создание приложений на основе модели — это ориентированный на компоненты подход к разработке приложений. В этом кратком руководстве вы узнаете, как легко создать приложение на основе модели с помощью одной из стандартных сущностей, доступных в вашей среде [!INCLUDE [powerapps](../../includes/powerapps.md)]. 

> [!IMPORTANT]
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]

## <a name="sign-in-to-powerapps"></a>Вход в PowerApps
Войдите в [PowerApps](https://web.powerapps.microsoft.com/). Если у вас еще нет учетной записи [!INCLUDE [powerapps](../../includes/powerapps.md)], перейдите по ссылке **Зарегистрируйтесь бесплатно**. 

## <a name="create-your-model-driven-app"></a>Создание приложения на основе модели

1.  Выберите нужную среду или перейдите в [центр администрирования PowerApps](https://admin.powerapps.microsoft.com/), чтобы создать новое приложение.
2.  В области навигации слева выберите **На основе модели**. 

    ![На основе модели](media/build-first-model-driven-app/choose-design-mode.png)

3. В области слева выберите **Приложения**, а затем — **Создать приложение**.

4.  На странице **Create a New App** (Создание нового приложения) введите следующие данные и нажмите кнопку **Готово**: 
  - **Имя**: введите имя приложения, например *Myfirstapp*. 
  - **Описание**: введите краткое описание приложения или его предназначение, например *Мое первое приложение*.
Подробнее о дополнительных свойствах приложения см. в статье [Создание или изменение приложения, управляемого моделью, с помощью конструктора приложений](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app#create-an-app).
 
    ![Создание нового приложения](media/build-first-model-driven-app/create-new-app.png)

## <a name="add-components-to-your-app"></a>Добавление компонентов в приложение
В конструкторе приложений добавьте компоненты в приложение.
1.  Щелкните стрелку **Open the Site Map Designer** (Открыть конструктор карты сайта), чтобы открыть конструктор карты сайта. 

    ![Создание новой карты сайта](media/build-first-model-driven-app/new-sitemap.png)

2.  В конструкторе карты сайта выберите **New Subarea** (Новая дочерняя область), в правой области выберите вкладку **Свойства**, а затем выберите следующие свойства.
  - **Тип**: "Сущность".
  - **Сущность**: "Учетная запись".

    ![Добавление компонентов на карту сайта](media/build-first-model-driven-app/sitemap.png)

3.  Щелкните **Сохранить и закрыть**.
4.  На холсте конструктора приложений выберите **Формы**, а затем в правой области в группе **Main Forms** (Основные формы) выберите форму **Учетная запись**.

    ![Основная форма учетной записи](media/build-first-model-driven-app/main-form.png)

5.  На холсте конструктора приложений щелкните **Представления**, а затем выберите **Active Accounts** (Активные учетные записи), **All Accounts** (Все учетные записи) и **My Active Accounts** (Мои активные учетные записи).

    ![Представления учетных записей](media/build-first-model-driven-app/views.png)

6. На холсте конструктора приложений выберите **Диаграммы**, а затем выберите диаграмму **Accounts by Industry** (Учетные записи по отраслям).
7. На панели инструментов конструктора приложений нажмите кнопку **Сохранить**.

    ![Кнопка "Сохранить" на панели инструментов конструктора приложений](media/build-first-model-driven-app/app-designer-toolbar.png)
 
<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## <a name="publish-your-app"></a>Публикация приложения
На панели инструментов конструктора приложений нажмите кнопку **Опубликовать**.

После публикации приложения можно запустить его и предоставить к нему общий доступ другим пользователям.

![Простое приложение сущности учетной записи](media/build-first-model-driven-app/accounts-quickstart-app.png)

## <a name="next-steps"></a>Дальнейшие действия
В этом кратком руководстве вы создали простое приложение на основе модели. Чтобы увидеть, как выглядит запущенное приложение, см. статью [Краткое руководство: запуск приложения на основе модели на мобильном устройстве](../../user/run-app-client-model-driven.md).
Сведения о том, как предоставить общий доступ к приложению на основе модели, см. в [этом руководстве](share-model-driven-app.md).
