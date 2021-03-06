---
title: Открытие данных сущности в Excel | Microsoft Docs
description: Открытие данных сущности в Excel для интерактивного просмотра и редактирования.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="open-entity-data-in-excel"></a>Открытие данных сущности в Excel
Открыв данные сущности в Microsoft Excel, можно быстро и легко просматривать и редактировать данные с помощью надстройки Microsoft PowerApps Excel. Для надстройки PowerApps Excel нужен Microsoft Excel 2016.

![Надстройка Excel](./media/data-platform-cds-excel-addin/ExcelAddin.png "Надстройка PowerApps Excel")

## <a name="open-entity-data-in-excel"></a>Открытие данных сущности в Excel
1. На сайте [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) разверните раздел **Данные** и щелкните или нажмите **Сущности** на левой панели навигации. Все сущности отображаются.
2. Щелкните многоточие (...) справа от интересующей вас сущности.
3. Щелкните **Открыть в Excel**, затем откройте книгу, которая создается. Эта книга содержит данные для привязки сущности, указатель на вашу среду и указатель на надстройку PowerApps Excel.  
4. В Excel щелкните **Включить изменение**, чтобы разрешить работу надстройки PowerApps Excel. Надстройка Excel запускается в области с правой стороны окна Excel.
5. Если надстройка PowerApps Excel запускается впервые, щелкните **Доверять этой надстройке**, чтобы разрешить запуск надстройки Excel.
6. Если будет предложено выполнить вход, щелкните **Войти**, после чего выполните вход с помощью тех же учетных данных, который вы использовали на сайте [powerapps.com](https:///?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Надстройка Excel будет использовать предыдущий контекст входа и автоматически выполнять вход, если она может. Поэтому проверьте имя пользователя в правом верхнем углу надстройки Excel.

Надстройка Excel автоматически считывает данные для выбранной сущности. Обратите внимание, что книга не содержит данных, пока надстройка Excel не прочитает их.

## <a name="view-and-refresh-data-in-excel"></a>Просмотр и обновление данных в Excel
После того как надстройка Excel считает данные в книгу, можно обновить данные в любое время, нажав **Обновить** в надстройке Excel.

## <a name="edit-data-in-excel"></a>Изменение данных в Excel
Можно изменить данные сущности как требуется, а затем опубликовать из обратно, нажав **Опубликовать** в надстройке Excel.

Для редактирования записи выберите ячейку на листе, затем измените значение в ячейке.

Для добавления новой записи выполните одно из следующих действий.

* Щелкните в любом месте на листе, затем нажмите **Создать** в надстройке Excel.
* Щелкните в последней строке листа, затем нажимайте клавишу TAB, пока курсор не уйдет из последнего столбца этой строки и не будет создана новая строка.
* Щелкните в строке немедленно под листом и начинайте вводить данные в ячейку. При перемещении фокуса из этой ячейки лист расширяется для включения новой строки.

Для удаления записи выполните одно из следующих действий.

* Щелкните правой кнопкой мыши номер строки рядом со строкой листа, которую требуется удалить, затем нажмите **Удалить**.
* Щелкните правой кнопкой мыши в строке, которую требуется удалить, затем нажмите **Удалить** > **Строки таблицы**.

## <a name="add-or-remove-columns"></a>Добавление или удаление столбцов
С помощью конструктора можно изменить столбцы и сущности, которые автоматически добавляются в таблицу.

1. Включите конструктор источника данных надстройки Excel, нажав кнопку **Параметры** (символ шестеренки), затем установив флажок **Включить конструктор**.
2. Щелкните **Конструктор** в надстройке Excel. Отображается список всех источников данных.
3. Рядом с источником данных щелкните кнопку **Изменить** (карандаша символ).
4. Настройте список в поле **Выбранные поля**, так как требуется.
   * Для добавления поля из поля **Доступные поля** в поле **Выбранные поля** нажмите поля, после чего щелкните **Добавить**. В качестве альтернативы дважды щелкните поле.
   * Для удаления поля из поля **Выбранные поля** щелкните поле, затем нажмите **Удалить**. В качестве альтернативы дважды щелкните поле.
   * Для изменения порядка полей щелкните поле в поле **Выбранные поля**, затем щелкайте **Вверх** или **Вниз**.
5. Примените изменения к источнику данных, нажав **Обновить**, после чего щелкните **Готово** для выхода из конструктора. Если добавлено поле (столбец), щелкните **Обновить**, чтобы получить обновленный набор данных.

> [!NOTE]
> Обязательно всегда включайте в рабочую книгу идентификатор и обязательные поля, так как при публикации могут возникать ошибки.

> [!NOTE]
> При добавлении полей подстановки обязательно добавляйте как поле идентификатора, так поле отображения.

## <a name="troubleshooting"></a>Устранение неполадок
Имеется несколько проблем, которые удастся устранить с помощью простых шагов.

* Не все сущности поддерживают редактирование и создание новых записей; такие сущности будут открываться в Excel и позволят вам просматривать данные, но публикация будет отключена.
* Поля подстановки должны редактироваться с использованием надстройки, чтобы обеспечить правильные ссылки на запись, обновление этих полей путем копирования и вставки или прямого ввода не поддерживается.


При возникновении проблемы, которая не описана здесь, свяжитесь с нами с помощью [страниц поддержки](https://powerapps.microsoft.com/support/).

## <a name="next-steps"></a>Дальнейшие действия
* [Управление полями в сущности](data-platform-manage-fields.md)
* [Определение отношений между сущностями](data-platform-entity-lookup.md)
* [Создание приложения с помощью Common Data Service для приложений](../canvas-apps/data-platform-create-app.md)
* [Создание приложения с нуля с помощью Common Data Service для приложений](../canvas-apps/data-platform-create-app-scratch.md)

