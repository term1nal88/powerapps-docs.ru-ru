---
title: Создание с нуля приложения на основе холста при помощи Common Data Service for Apps | Документы Майкрософт
description: Создание в PowerApps приложения на основе холста для добавления, обновления и удаления записей в Common Data Service for Apps.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b90024e3864420c541b0e0e1ef0ad1d86b900aa0
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2018
ms.locfileid: "42852283"
---
# <a name="create-a-canvas-app-from-scratch-using-common-data-service-for-apps"></a>Создание с нуля приложения на основе холста при помощи Common Data Service for Apps

Вы можете создать приложение на основе холста для управления данными в службе Common Data Service for Apps с использованием стандартных (встроенных) и настраиваемых (созданных вашей организацией) сущностей.

При создании приложения на основе службы Common Data Service не требуется создавать подключение из PowerApps, как в случае с источниками данных, например SharePoint, Dynamics 365 и Salesforce. Требуется только указать сущности, которые нужно показать или которыми вы собираетесь управлять в приложении.

## <a name="prerequisites"></a>Технические условия

- Прежде чем создавать приложение с нуля, ознакомьтесь с основами PowerApps, [создав приложение](data-platform-create-app.md), а затем настроив его [коллекцию](customize-layout-sharepoint.md), [формы](customize-forms-sharepoint.md) и [карточки](customize-card.md).
- [Перейдите в среду](working-with-environments.md), в которой был создан образец базы данных. Если у вас есть соответствующая лицензия, вы можете [создать среду](../../administrator/create-environment.md) с этой целью.

## <a name="open-a-blank-app"></a>Пустое приложение

1. Войдите в [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    ![Домашняя страница PowerApps](./media/data-platform-create-app-scratch/sign-in.png)

1. В области **Разрабатывайте такие приложения** наведите указатель на плитку **Начать с пустого**, нажмите значок телефона, а затем выберите пункт **Создать это приложение**.

    ![Плитка пустого приложения](./media/data-platform-create-app-scratch/blank-app.png)

    Вы можете разработать приложение с нуля для телефонов или других устройств (например, планшетов). В этой статье будет рассмотрено создание приложения для телефонов.

## <a name="specify-an-entity"></a>Указание сущности

1. В центре экрана нажмите **подключиться к данным**, а затем в области **Данные** выберите подключение **Common Data Service**.

1. В поле поиска введите или вставьте первые несколько букв фразы **учетные записи**, чтобы отфильтровать список сущностей, установите флажок рядом с пунктом **Учетные записи**, а затем нажмите кнопку **Подключиться**.

    ![Выбор сущности "Учетные записи"](./media/data-platform-create-app-scratch/cds-connect.png)

1. Закройте область **Данные**, нажав значок закрытия в правом верхнем углу.

## <a name="add-a-list-screen"></a>Добавление окна списка

1. На вкладке **Главная** нажмите стрелку вниз рядом с элементом **Новый экран** и выберите пункт **Окно списка**.

    ![Добавление окна списка](./media/data-platform-create-app-scratch/list-screen.png)

1. На панели навигации слева выберите пункт **TemplateGalleryList1**, чтобы выбрать этот шаблон, а затем в качестве значения свойства **Items** укажите следующую формулу:

    `SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))`

    Согласно этой формуле:

   - в коллекции должны отображаться данные из сущности **Учетные записи**;
   - данные должны сортироваться в порядке возрастания, пока пользователь не изменит порядок сортировки, нажав кнопку сортировки;
   - если пользователь введет или вставит в поле поиска один или несколько символов, в списке будут отображаться только те учетные записи, поле имени которых содержит эти символы.

     Вы можете использовать [эти и многие другие функции](formula-reference.md) для настройки внешнего вида и поведения приложения.

     ![Задание свойства Items коллекции](./media/data-platform-create-app-scratch/gallery-items.png)

1. Настройте макет коллекции так, чтобы отображалось только имя каждой учетной записи, а заголовок настройте так, чтобы отображалось слово **Обзор**, как описано в статье [Настройка коллекции](customize-layout-sharepoint.md).

    ![Экран обзора](./media/data-platform-create-app-scratch/final-browse.png)

1. На панели навигации слева наведите указатель на пункт **Screen1**, нажмите значок многоточия (...), а затем выберите пункт **Удалить**.

1. На панели навигации слева наведите указатель на пункт **Screen2**, нажмите значок многоточия (...), а затем выберите пункт **Переименовать**.

1. Введите или вставьте слово **BrowseScreen**, а затем измените имя коллекции в этом окне на **BrowseGallery**.

    ![Переименование окна обзора, коллекция](./media/data-platform-create-app-scratch/rename-browse.png)

## <a name="add-a-form-screen"></a>Добавление окна формы

1. Повторите первое действие из предыдущей процедуры, но добавьте **окно формы** вместо **окна списка**.

1. На вкладке **Дополнительно** в области справа присвойте свойству **DataSource** формы значение **Учетные записи**, а ее свойству **Item** — значение **BrowseGallery.Selected**.

    ![Задание свойств Datasource и Item формы](./media/data-platform-create-app-scratch/form-datasource.png)

1. На вкладке **Свойства** в области справа нажмите **Учетные записи**, чтобы открыть область **Данные**, а затем установите флажки рядом со следующими полями:

    - Имя учетной записи
    - Адрес 1: улица 1
    - Адрес 1: город
    - Адрес 1: почтовый индекс
    - Количество сотрудников
    - Годовой доход

1. Задайте для свойства **Text** заголовка значение **Создание или изменение**.

    Изменения отразятся на экране.

    ![Задание свойств Datasource и Item формы](./media/data-platform-create-app-scratch/field-list.png)

1. Измените имя экрана на **FormScreen**.

## <a name="configure-icons"></a>Настройка значков

1. В верхней части окна **BrowseScreen** нажмите круглый значок и задайте в качестве значения его свойства **OnSelect** следующую формулу:

    `Refresh(Accounts)`

    ![Значок обновления](./media/data-platform-create-app-scratch/refresh-icon.png)

1. Нажмите значок "плюс" и задайте следующую формулу в качестве значения свойства **OnSelect**:

    `NewForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Значок добавления](./media/data-platform-create-app-scratch/plus-icon.png)

1. Нажмите первую стрелку, направленную вправо, и задайте следующую формулу в качестве значения свойства **OnSelect**:

    `EditForm(EditForm1); Navigate(FormScreen, ScreenTransition.None)`

    ![Значок "Далее"](./media/data-platform-create-app-scratch/next-icon.png)

1. В окне **FormScreen** нажмите значок отмены и задайте в качестве значения его свойства **OnSelect** следующую формулу:

    `ResetForm(EditForm1);Navigate(BrowseScreen, ScreenTransition.None)`

    ![Значок отмены](./media/data-platform-create-app-scratch/cancel-icon.png)

1. Нажмите значок с галочкой и задайте следующую формулу в качестве значения свойства **OnSelect**:

    `SubmitForm(EditForm1); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Значок с галочкой](./media/data-platform-create-app-scratch/checkmark-icon.png)

1. На вкладке **Вставка** нажмите элемент **Значки**, а затем выберите значок **Корзина**.

1. Задайте для свойства **Color** значка **Корзина** значение **White**, а в качестве значения свойства **OnSelect** укажите следующую формулу:

    `Remove(Accounts, BrowseGallery.Selected); Navigate(BrowseScreen, ScreenTransition.None)`

    ![Значок корзины](./media/data-platform-create-app-scratch/trash-icon.png)

## <a name="test-the-app"></a>Тестирование приложения

1. На панели навигации слева выберите окно **BrowseScreen**, а затем откройте режим предварительного просмотра, нажав клавишу F5 (либо нажав значок воспроизведения в правом верхнем углу).

    ![Открытие режима предварительного просмотра](./media/data-platform-create-app-scratch/open-preview.png)

1. Переключитесь между порядками сортировки по возрастанию и по убыванию и отфильтруйте список, указав символы, входящие в имена учетных записей.

1. Добавьте учетную запись, измените ее, начните обновлять ее, но отмените изменения, а затем удалите учетную запись.

## <a name="next-steps"></a>Дальнейшие действия

[Откройте один или несколько примеров приложений](open-and-run-a-sample-app.md) и ознакомьтесь с различными типами приложений, которые можно создавать.
