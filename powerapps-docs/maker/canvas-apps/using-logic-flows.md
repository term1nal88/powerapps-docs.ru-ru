---
title: Запуск потока в приложении на основе холста | Документы Майкрософт
description: Создание потока, который выполняет те или иные задачи после определенного события, например нажатия кнопки пользователем, в приложении на основе холста.
author: stepsic-microsoft-com
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/05/2017
ms.author: sharik
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 05d633b20038ad61215a8e898b1ec7afa044b574
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42840776"
---
# <a name="start-a-flow-in-a-canvas-app"></a>Запуск потока в приложении на основе холста

Microsoft Flow позволяет создать логику, выполняющую какой-то набор задач, когда в приложении на основе холста происходит определенное событие. Например, настройте кнопку таким образом, чтобы при ее нажатии в списке SharePoint создавался элемент, отправлялось электронное сообщение или запрос на собрание, файл добавлялся в облако или чтобы выполнялись все из перечисленных действий. Вы можете настроить любой элемент управления в приложение для запуска последовательности, которая будет выполняться, даже если закрыть PowerApps.

## <a name="prerequisites"></a>Технические условия

* [Регистрация](../signup-for-powerapps.md) в PowerApps.
* Узнайте, как [настроить элемент управления](add-configure-controls.md).

## <a name="create-a-flow"></a>Создание последовательности

1. Войдите на сайт [powerapps.com](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), а затем на панели навигации слева выберите **Потоки**.

2. На странице **Мои потоки** выберите **Создать с нуля**.

    ![Параметр, позволяющий создать последовательность без использования шаблона](./media/using-logic-flows/create-from-blank.png)

    **PowerApps** добавляется как триггер по умолчанию.

    ![PowerApps — триггер, запускающий последовательность](./media/using-logic-flows/set-trigger.png)

3. Выберите **New step** (Новый шаг), а затем — **Добавить действие**.

    ![Параметр, позволяющий добавить действие](./media/using-logic-flows/add-action.png)

4. В поле с текстом **Поиск по всем службам и действиям** укажите действие для последовательности, как показано в следующем примере.

   1. В поле введите **SharePoint**, а затем из списка **Действия** выберите **SharePoint — Create item** (SharePoint — создать элемент).

       ![Параметр, позволяющий создать элемент SharePoint](./media/using-logic-flows/create-sharepoint-item.png)

   2. При появлении запроса введите учетные данные для подключения к SharePoint.

   3. В поле **Адрес сайта** введите или вставьте URL-адрес сайта SharePoint Online, содержащего список.

       > [!NOTE]
      > Укажите URL-адрес для сайта без списка.

   4. В поле **Имя списка** выберите список, который нужно использовать.

   5. Щелкните (коснитесь) поле **Заголовок**, а затем выберите **Добавить динамическое содержимое**.

       ![Добавление параметра "Спросить в PowerApps" в поле Title (Заголовок)](./media/using-logic-flows/ask-in-powerapps.png)

   6. В списке параметров выберите **Спросить в PowerApps**.

       ![Добавление параметра](./media/using-logic-flows/add-parameter.png)

5. (Необязательно.) Укажите одно или несколько дополнительных действий, например отправку письма об утверждении на указанный адрес или создание связанной записи в другом источнике данных.

6. В верхней части экрана введите или вставьте имя своей последовательности и выберите **Создать поток**.

    ![Именование и сохранение последовательности](./media/using-logic-flows/name-flow.png)

## <a name="add-a-flow-to-an-app"></a>Добавление последовательности в приложение
1. В PowerApps в меню **Файл** выберите **Создать**.

2. На плитке **Пустое приложение** выберите **Макет для телефона**.

3. Добавьте элемент управления **[Текстовое поле](controls/control-text-input.md)** и назовите его **RecordTitle**.

4. Добавьте элемент управления **[Кнопка](controls/control-button.md)** и переместите его под элемент управления **RecordTitle**.

5. Выберите элемент управления **[Кнопка](controls/control-button.md)**, а затем на вкладке **Действие** щелкните **Потоки**.

    ![Параметр "Потоки" на вкладке "Действия"](./media/using-logic-flows/action-tab.png)

6. В появившейся области выберите последовательность, созданную при выполнении предыдущей процедуры.

    > [!NOTE]
   > Если последовательность, которую вы создали, недоступна, убедитесь, что в PowerApps выбрана именно то окружение, в котором эта последовательность была создана.

    ![Добавление последовательности из области настройки](./media/using-logic-flows/add-flow-from-pane.png)

7. В строке формул введите или вставьте **RecordTitle.Text)** в конце формулы, добавленной автоматически.

    ![Свойство OnSelect, содержащее последовательность](./media/using-logic-flows/onselect-with-flow.png)

## <a name="test-the-flow"></a>Тестирование последовательности
1. Откройте режим предварительного просмотра, нажав клавишу F5 (или выбрав стрелку в правом верхнем углу).

    ![Свойство OnSelect, содержащее последовательность](./media/using-logic-flows/open-preview.png)

2. Введите или вставьте текст в элементе управления **RecordTitle**, а затем щелкните (коснитесь) элемент управления **[Кнопка](controls/control-button.md)**.

    После этого в заданном списке с текстом, указанным в качестве заголовка, будет создан элемент SharePoint. Если список был открыт при выполнении последовательности, может потребоваться обновить окно браузера для отображения изменений.
