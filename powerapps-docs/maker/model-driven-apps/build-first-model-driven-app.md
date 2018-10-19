---
title: Создание первого управляемого моделью приложения с нуля с помощью PowerApps | Microsoft Docs
description: 'Узнайте, как создать простое управляемое моделью приложение.'
documentationcenter: ''
author: Mattp123
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 04/18/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="build-your-first-model-driven-app-from-scratch"></a>Создание первого управляемого моделью приложения с нуля
Разработка управляемого моделью приложения — это основанный на компонентах подход к разработке приложений. В этом разделе можно упростить создание управляемого моделью приложения с помощью одной из стандартных сущностей, доступных в среде PowerApps.

> [!TIP]
> Дополнительные сведения о создании управляемых моделью приложений см. в разделе [Общие сведения о компонентах управляемых моделью приложений](model-driven-app-components.md). 

## <a name="sign-in-to-powerapps"></a>Вход в PowerApps
Выполните вход в [PowerApps](https://web.powerapps.com/). Если у вас еще нет учетной записи [!INCLUDE [powerapps](../../includes/powerapps.md)], выберите **Начать работу бесплатно** на сайте. 

## <a name="create-your-model-driven-app"></a>Создание управляемого моделью приложения

1.  Выберите требуемую среду или перейдите в [центр администрирования PowerApps](https://admin.powerapps.com/), чтобы создать новую.
2.  В левой области навигации выберите **Управляемые моделью**. 

    ![Управляемые моделью](media/build-first-model-driven-app/choose-design-mode.png)

  > [!IMPORTANT]
  > Если режим разработки **Управляемые моделью** недоступен, может потребоваться [создать среду](https://docs.microsoft.com/powerapps/administrator/create-environment).   

3. В левой области выберите **Приложения**, а затем выберите **Создание приложения**.

4.  На странице **Создать приложение** введите следующие сведения, затем нажмите **Готово**. 
  - **Имя**: введите имя приложения, например *Myfirstapp*. 
  - **Описание**: введите краткое описание того, что представляет из себя приложение или что оно делает, например *Это мое первое приложение*.
Сведения о дополнительных свойствах приложения см. в разделе [Создание приложения](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app#create-an-app).
 
    ![Создание приложения](media/build-first-model-driven-app/create-new-app.png)

## <a name="add-components-to-your-app"></a>Добавление компонентов в приложение
В конструкторе приложений добавьте компоненты в приложение.
1.  Нажмите стрелку **Открыть конструктор карты сайта**, чтобы открыть конструктор карты сайта. 

    ![Создание карты сайта](media/build-first-model-driven-app/new-sitemap.png)

2.  В конструкторе карты сайта выберите **Создать дочернюю область**, в правой области перейдите на вкладку **Свойства**, и затем выберите следующие свойства.
  - **Тип**: сущность
  - **Сущность**: организация

    ![Добавление компонентов на карту сайта](media/build-first-model-driven-app/sitemap.png)

3.  Выберите **Сохранить и закрыть**.
4.  На холсте в конструкторе приложений выберите **Формы** и в право области в группе **Основные формы** выберите форму **Организация**.

    ![Основная форма организации](media/build-first-model-driven-app/main-form.png)

5.  На холсте конструктора приложений выберите **Представления**, затем выберите представления **Активные организации**, **Все организации** и **Мои активные организации**.

    ![Представления "Организация"](media/build-first-model-driven-app/views.png)

6. На холсте конструктора приложений выберите **Диаграммы**, затем выберите диаграмму **Организации по отрасли**.
7. На панели инструментов конструктора приложений выберите **Сохранить**.

    ![Сохранение панели инструментов конструктора приложений](media/build-first-model-driven-app/app-designer-toolbar.png)
 
<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## <a name="publish-your-app"></a>Публикация приложения
На панели инструментов конструктора приложений выберите **Опубликовать**.

После публикации приложения оно будет готово к выполнению совместному использованию с другими пользователями.

![Простое приложение сущности организации](media/build-first-model-driven-app/accounts-quickstart-app.png)

## <a name="next-steps"></a>Дальнейшие действия
В этом разделе вы создали простое управляемое моделью приложение. 
- Чтобы узнать, как выглядит ваше приложение при выполнении, см. раздел [Запуск приложения, управляемого моделью, на мобильном устройстве](../../user/run-app-client-model-driven.md).
- Чтобы узнать, как предоставить общий доступ к приложению, см. раздел [Общий доступ к управляемому моделью приложению](share-model-driven-app.md).
- Чтобы начать работу и получить дополнительные сведения о создании управляемых моделью приложений, см. раздел [Общие сведения о компонентах управляемых моделью приложений](model-driven-app-components.md).
