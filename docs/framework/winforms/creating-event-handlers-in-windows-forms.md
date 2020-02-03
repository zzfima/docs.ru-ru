---
title: Создание обработчиков событий
ms.date: 03/30/2017
helpviewer_keywords:
- event handling [Windows Forms]
- Windows Forms controls, event handling
- Windows Forms, event handling
- events [Windows Forms], event handlers
- event handlers [Windows Forms]
ms.assetid: 6514e530-c6b8-489c-a8d2-eda7b7072701
ms.openlocfilehash: 90acb3c7691acbcb528ae66692af67c2fb28eeaf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742332"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="7ae70-102">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7ae70-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="7ae70-103">Обработчик событий — это процедура в коде, определяющая, какие действия должны выполняться при возникновении тех или иных событий, например, если пользователь нажимает кнопку или сообщение поступает в очередь.</span><span class="sxs-lookup"><span data-stu-id="7ae70-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="7ae70-104">При порождении события запускается получивший его обработчик или несколько обработчиков.</span><span class="sxs-lookup"><span data-stu-id="7ae70-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="7ae70-105">События могут назначаться сразу нескольким обработчикам, а методы, которые управляют конкретными событиями, можно изменять динамически.</span><span class="sxs-lookup"><span data-stu-id="7ae70-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="7ae70-106">Для создания обработчиков событий также можно использовать конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7ae70-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7ae70-107">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="7ae70-107">In This Section</span></span>

 <span data-ttu-id="7ae70-108">[Общие сведения о событиях](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="7ae70-108">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="7ae70-109">Объясняет модель событий и роли делегатов.</span><span class="sxs-lookup"><span data-stu-id="7ae70-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="7ae70-110">[Общие сведения об обработчиках событий](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="7ae70-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="7ae70-111">Описывает порядок обработки событий.</span><span class="sxs-lookup"><span data-stu-id="7ae70-111">Describes how to handle events.</span></span>

 <span data-ttu-id="7ae70-112">[Практические руководства. Создание обработчиков событий во время выполнения для Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="7ae70-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="7ae70-113">Динамически выдает инструкции по реагированию на системные или пользовательские события.</span><span class="sxs-lookup"><span data-stu-id="7ae70-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="7ae70-114">[Как подключить несколько событий к одному обработчику событий в Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="7ae70-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="7ae70-115">Выдает инструкции по назначению одной и той же функциональности нескольким элементам управления с помощью событий.</span><span class="sxs-lookup"><span data-stu-id="7ae70-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="7ae70-116">[Порядок событий в Windows Forms](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="7ae70-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="7ae70-117">Описывает порядок порождения событий в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7ae70-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="7ae70-118">[Инструкции. Создание обработчиков событий с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Описывает, как использовать конструктор Windows Forms для создания обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="7ae70-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="7ae70-119">См. также</span><span class="sxs-lookup"><span data-stu-id="7ae70-119">Related Sections</span></span>

 <span data-ttu-id="7ae70-120">[События](../../standard/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="7ae70-120">[Events](../../standard/events/index.md)</span></span>\
 <span data-ttu-id="7ae70-121">Содержит ссылки на разделы, посвященные обработке и вызову событий с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7ae70-121">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="7ae70-122">[Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="7ae70-122">[Troubleshooting Inherited Event Handlers in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span></span>\
 <span data-ttu-id="7ae70-123">Представляет распространенные проблемы, возникающие у обработчиков событий в наследуемых компонентах.</span><span class="sxs-lookup"><span data-stu-id="7ae70-123">Lists common issues that occur with event handlers in inherited components.</span></span>
