---
title: Создание и изменение приложений в браузере | Документация Майкрософт
description: Создание или изменение приложений в браузере с помощью PowerApps Studio в Интернете.
documentationcenter: na
author: aftowen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/08/2018
ms.author: anneta
ms.openlocfilehash: 4add1e15c1a85b27b83295422dbb6472ac02ad9f
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "32329118"
---
# <a name="create-or-edit-apps-in-powerapps-studio-for-web"></a>Создание или изменение приложений в PowerApps Studio в Интернете
Можно создавать и изменять приложения в среде PowerApps Studio в Интернете, которая открывается в окне браузера в Windows или на других платформах.

## <a name="prerequisites"></a>Технические условия
* [Регистрация](../signup-for-powerapps.md) в PowerApps.
* Используйте [поддерживаемый браузер](limits-and-config.md#supported-browsers-for-powerapps-studio).

## <a name="open-powerapps-studio-for-web"></a>Открыть PowerApps Studio для Web
1. Войдите на сайт [powerapps.com](http://go.microsoft.com/fwlink/p/?LinkId=708209).
2. В левом нижнем углу нажмите кнопку **Создать приложение**.

    ![Элемент "Создать приложение" в области навигации слева](./media/create-app-browser/left-nav.png)

PowerApps Studio для Web откроется на новой вкладке браузера. Вы можете создавать и изменять приложения точно так же, как в PowerApps Studio для Windows.

## <a name="known-limitations"></a>Известные ограничения
1. **Создание подключения.**

    Чтобы [создать подключение](add-manage-connections.md) к источнику данных, который требует аутентификации службы, войдите на сайт [powerapps.com](https://web.powerapps.com) и [добавьте подключение](add-data-connection.md) в приложение с помощью PowerApps Studio для Web.
2. **Изменение и сохранение приложения локально**.

    Для локального изменения и сохранения приложений лучше всего использовать PowerApps Studio для Windows. В браузере вы не сможете сохранить изменения в локальном приложении, или вам придется сохранить новый файл вместо перезаписи открытого.
3. **Использование сигнальных функций.**

    Функции **["Ускорение" и "Компас"](functions/signals.md)** возвращают точные значения в опубликованном приложении, но если вы создаете или изменяете приложение в браузере, эти значения будут нулевыми.
4. **Экспорт и импорт данных.**

    Вы можете [экспортировать и импортировать данные](controls/control-export-import.md) в опубликованном приложении, но тогда, когда создаете или изменяете приложение в браузере.
5. **Копирование элемента управления между двумя сеансами.**

    Элементы управления нельзя копировать из одного сеанса PowerApps Studio для Web в другой.

## <a name="next-steps"></a>Дальнейшие действия
* Автоматически создайте приложение на основе своих данных, например, из [Excel](get-started-create-from-data.md) или [SharePoint](app-from-sharepoint.md).
* Узнайте, как [добавить элемент управления и задать свойства](add-configure-controls.md), определяющие внешний вид и поведение приложения.
* Проявите свои творческие способности, [создавая приложение с нуля](get-started-create-from-blank.md).
