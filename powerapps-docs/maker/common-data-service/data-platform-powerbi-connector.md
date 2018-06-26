---
title: Создание отчета PowerBI | Документация Майкрософт
description: Вы можете подключаться к своим данными из PowerBI Desktop с помощью соединителя службы Common Data Service для приложений.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
ms.openlocfilehash: d8323eb103751a1be78aeea0093b9d6651ddc3e2
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "34445897"
---
# <a name="create-a-power-bi-report"></a>Создание отчета Power BI
Служба Common Data Service для приложений позволяет напрямую подключаться к данным с помощью Power BI Desktop для создания отчетов и их публикации в Power BI. Из Power BI отчеты можно использовать на панелях мониторинга, открытых для других пользователей и доступных в мобильных приложениях Power BI на разных платформах.

![Power BI Desktop](./media/data-platform-cds-powerbi-connector/PBIDesktop.png "Power BI Desktop")

## <a name="prerequisites"></a>Технические условия

Для работы Power BI со службой Common Data Service для приложений необходимо выполнить следующие условия.

* Скачать и установить Power BI Desktop — бесплатное приложение, которое выполняется на локальном компьютере. Power BI Desktop можно скачать [здесь](https://powerbi.microsoft.com/desktop/).
* Среда Common Data Service для приложений с разрешениями на создание для доступа к порталу и разрешениями на чтение для доступа к данным в сущностях.

## <a name="finding-your-common-data-service-for-apps-environment-url"></a>Поиск URL-адреса среды Common Data Service для приложений

1. Откройте [PowerApps](https://web.powerapps.com) и выберите среду, к которой необходимо подключиться. Затем нажмите значок **шестеренки** в правом верхнем углу и щелкните **Advanced customizations** (Дополнительная настройка).

    ![Среда CDS для приложений](./media/data-platform-cds-powerbi-connector/CDSEnv1.png "Среда CDS для приложений")

2. В разделе "Ресурсы разработчика" нажмите кнопку **Ресурсы**, после чего откроется новая вкладка.

    ![Среда CDS для приложений](./media/data-platform-cds-powerbi-connector/CDSEnv2.png "Среда CDS для приложений")

3. Скопируйте корень URL-адреса на новой вкладке — это уникальный URL-адрес вашей среды. URL-адрес будет иметь формат **https://yourenvironmentid.crm.dynamics.com/**. Оставшуюся часть URL-адреса копировать не нужно. Сохраните URL-адрес в быстродоступном месте, чтобы использовать его при создании отчета PowerBI.

    ![Среда CDS для приложений](./media/data-platform-cds-powerbi-connector/CDSEnv3.png "Среда CDS для приложений")

## <a name="connecting-to-common-data-service-for-apps-from-power-bi-desktop"></a>Подключение к службе Common Data Service для приложений из Power BI Desktop

1. Запустите **Power BI Desktop**. В первый раз может появиться экран приветствия или пустой холст. В любом случае щелкните **Get Data** (Получить данные) и **More** (Дополнительно), чтобы открыть полный список доступных источников данных для Power BI Desktop.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport1.png "Power BI Desktop")

2. В списке соединителей выберите **Веб-службы** и **Служба Common Data Service для приложений (бета-версия)**. Нажмите кнопку **Подключить**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport2.png "Power BI Desktop")

3. Вставьте **URL-адрес среды Common Data Service для приложений** в поле **URL-адрес сервера** и нажмите кнопку **OK**. Если вы выполняете эти действия в первый раз, вам будет предложено войти в систему с помощью тех же учетных данных, которые используются для подключения к PowerApps и службе Common Data Service для приложений.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport3.png "Power BI Desktop")

4. В навигаторе будут отображены все доступные для среды сущности, сгруппированные в три папки. Разверните папку **Common Data Service**.

    * Common Data Service — это стандартные широко используемые сущности, которые доступны во всех средах в составе Common Data Service.
    * Настраиваемые сущности — это сущности, которые были созданы или импортированы в вашей среде.
    * Система — содержит все сущности в среде, включая сущности Common Data Service и настраиваемые сущности.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport4.png "Power BI Desktop")

5. Выберите сущность **Account**, чтобы просмотреть данные на правой панели, а затем нажмите кнопку **Load** (Загрузить).

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport5.png "Power BI Desktop")

6. Сущность будет загружена в отчет, после чего вы можете начать создавать отчеты. Если необходимо, повторите эту процедуру, чтобы добавить дополнительные сущности.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport6.png "Power BI Desktop")

7. На панели "Поле" щелкните поле **Имя**, чтобы добавить новую визуализацию на холст отчета. Вы можете повторять этот процесс и изменять визуализации для создания отчета.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport7.png "Power BI Desktop")


## <a name="using-option-sets"></a>Использование наборов параметров

Наборы параметров используются в сущности для предоставления пользователю раскрывающегося списка значений в приложениях и потоках. При использовании соединителя Power BI поля набора параметров будут представлены в виде двух столбцов для отображения уникального и отображаемого значений.

Например, если в сущности ApprovalStatus есть набор параметров, вы увидите два следующих поля в Power BI.

* ApprovalStatus — в этом поле будет отображаться уникальное целое значение для каждого элемента в наборе параметров. Это полезно при применении фильтров, так как значения не затрагиваются при последующих изменениях отображаемого имени.
* ApprovalStatus_display — в этом поле будет отображается понятное отображаемое имя элемента. Чаще всего оно используется при представлении параметра в таблице или диаграмме.

    |ApproalStatus|ApprovalStatus_Display|
    |---------|---------|
    1|Отправлено
    2|На проверке
    3|Approved
    4|Отклонено

## <a name="navigating-relationships"></a>Переход по связям

В службе Common Data Service для приложений необходимо создать связь в PowerBI Desktop между двумя сущностями с помощью поля GUID (это созданный системой уникальный идентификатор, который обеспечивает создание связей для записей создания в случаях неоднозначности или дублирования в других полях). Дополнительные сведения об управлении связями в Power BI Desktop см. [здесь](https://docs.microsoft.com/power-bi/desktop-create-and-manage-relationships).

Несмотря на то, что некоторые связи можно создавать автоматически, вы по-прежнему можете проверять формирование правильных связей при создании отчета:

* Поле для поиска будет содержать идентификатор GUID записи в связанной сущности.
* У связанной сущности будет поле в формате [EntityName]id, содержащее идентификатор GUID, например Accountid или MyCustomEntityid
* С помощью функции PowerBI Desktop "Управление связями" можно создать связь между полем для поиска и полем идентификатора в связанной сущности.


## <a name="next-steps"></a>Дальнейшие действия
* [Управление полями сущности](data-platform-manage-fields.md)
* [Определение связи между сущностями в модели общих данных](data-platform-entity-lookup.md)


