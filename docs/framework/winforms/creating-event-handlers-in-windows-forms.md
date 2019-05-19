---
title: Создание обработчиков событий в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: e90e1d6643a30c1d2f4438e77317a2348b07fd71
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65882415"
---
# <a name="creating-event-handlers-in-windows-forms"></a>Создание обработчиков событий в Windows Forms

Обработчик событий — это процедура в коде, определяющая, какие действия должны выполняться при возникновении тех или иных событий, например, если пользователь нажимает кнопку или сообщение поступает в очередь. При порождении события запускается получивший его обработчик или несколько обработчиков. События могут назначаться сразу нескольким обработчикам, а методы, которые управляют конкретными событиями, можно изменять динамически. Можно также использовать конструктор Windows Forms в Visual Studio для создания обработчиков событий.

## <a name="in-this-section"></a>В этом разделе

 [Общие сведения о событиях](events-overview-windows-forms.md)\
 Объясняет модель событий и роли делегатов.

 [Общие сведения об обработчиках событий](event-handlers-overview-windows-forms.md)\
 Описывает порядок обработки событий.

 [Практическое руководство. Создание обработчиков событий во время выполнения для форм Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)\
 Динамически выдает инструкции по реагированию на системные или пользовательские события.

 [Практическое руководство. Подключение нескольких событий к одному обработчику в Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)\
 Выдает инструкции по назначению одной и той же функциональности нескольким элементам управления с помощью событий.

 [Порядок событий в Windows Forms](order-of-events-in-windows-forms.md)\
 Описывает порядок порождения событий в элементах управления Windows Forms.

 [Практическое руководство. Создание обработчиков событий с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) описывается, как использовать конструктор Windows Forms для создания обработчиков событий.

## <a name="related-sections"></a>Связанные разделы

 [События](../../standard/events/index.md)\
 Содержит ссылки на разделы по обработке и порождению событий с помощью .NET Framework.

 [Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)\
 Представляет распространенные проблемы, возникающие у обработчиков событий в наследуемых компонентах.
