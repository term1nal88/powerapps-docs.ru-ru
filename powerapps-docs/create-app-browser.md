---
title: "Создание и изменение приложений в браузере | Документация Майкрософт"
description: "Создание или изменение приложений в браузере с помощью PowerApps Studio в Интернете."
services: 
suite: powerapps
documentationcenter: na
author: karthik-1
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/06/2017
ms.author: karthikb
ms.openlocfilehash: 3c675e84f03e008a7f478d358a99fe3fff602002
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2017
---
# <a name="create-or-edit-apps-in-powerapps-studio-for-web"></a>Создание или изменение приложений в PowerApps Studio в Интернете
Можно создавать и изменять приложения в среде PowerApps Studio в Интернете, которая открывается в окне браузера в Windows или на других платформах.

**Предварительные требования**

* [Регистрация](signup-for-powerapps.md) в PowerApps.
* Microsoft Edge, Google Chrome или Internet Explorer 11 на компьютере с Windows или Mac OS.

## <a name="open-powerapps-studio-for-web"></a>Запуск PowerApps Studio для Web
1. Войдите на сайт [powerapps.com](http://go.microsoft.com/fwlink/p/?LinkId=708209).
2. В левом нижнем углу нажмите кнопку **Создать приложение**.
   
    ![Элемент "Создать приложение" в области навигации слева](./media/create-app-browser/left-nav.png)

PowerApps Studio для Web откроется на новой вкладке браузера. Вы можете создавать и изменять приложения точно так же, как в PowerApps Studio для Windows.

## <a name="next-steps"></a>Дальнейшие действия
* Автоматически создайте приложение на основе своих данных, например, из [Excel](get-started-create-from-data.md) или [SharePoint](app-from-sharepoint.md).
* Узнайте, как [добавить элемент управления и задать свойства](add-configure-controls.md), определяющие внешний вид и поведение приложения.
* Проявите свои творческие способности, [создавая приложение с нуля](get-started-create-from-blank.md).

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

