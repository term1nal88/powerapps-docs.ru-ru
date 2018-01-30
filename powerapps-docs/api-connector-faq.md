---
title: "Часто задаваемые вопросы о соединителе API | Документация Майкрософт"
description: "Ответы на вопросы о требованиях, триггерах и других аспектах."
services: 
suite: powerapps
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: b945f2775e26327557255a75f18e87a638a9fe66
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2018
---
# <a name="api-connector-faq-powerapps"></a>Часто задаваемые вопросы о соединителе API (PowerApps)
## <a name="requirements"></a>Требования
**Вопрос.** Могут ли создать соединители пользователи, не являющиеся независимыми поставщиками программного обеспечения?

**Ответ.** Чтобы выпустить общедоступный соединитель, пользователь должен быть либо владельцем соответствующей службы, либо иметь явные права на использование API.

**Вопрос.** Можно ли создать соединитель без интерфейсов REST API?

**Ответ.** Нет. Чтобы создать соединитель API, в службе необходимо реализовать поддержку интерфейсов HTTP REST API.

**Вопрос.** Какие типы проверки подлинности поддерживаются?

**Ответ.** Мы поддерживаем следующие стандарты проверки подлинности:

* OAuth2.0 (включает Azure Active Directory);
* ключ API;
* обычная проверка подлинности;

## <a name="triggers"></a>Триггеры
**Вопрос.** Можно ли создавать триггеры без веб-перехватчиков? 

**Ответ.** С помощью соединителей API для Microsoft Flow и Logic Apps можно создавать только триггеры на основе веб-перехватчиков. Если вам нужны другие формы реализации, обратитесь по адресу [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) и предоставьте дополнительные сведения о своем API.

## <a name="miscellaneous"></a>Прочие положения
**Вопрос.** Мои API используют динамической узел. Как реализовать использование динамического узла в OpenAPI?

**Ответ.** Соединитель API не поддерживает динамические узлы. Для разработки и тестирования используйте статический узел. Во время подачи заявки на развертывание соединителя поговорите с представителем Майкрософт о реализации поддержки динамического узла.

**Вопрос.** Поддерживается ли Postman Collection версии 2?

**Ответ.** Нет. Сейчас Postman Collection версии 2 не поддерживается.

**Вопрос.** Поддерживается ли OpenAPI 3.0?

**Ответ.** Нет. Сейчас поддерживается только OpenAPI 2.0.
