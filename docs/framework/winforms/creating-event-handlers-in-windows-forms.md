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
ms.openlocfilehash: 6b1d146dfd9d51641bc9eb5d8be4cd2508c223a1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963482"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="6a664-102">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a664-102">Creating Event Handlers in Windows Forms</span></span>

<span data-ttu-id="6a664-103">Обработчик событий — это процедура в коде, определяющая, какие действия должны выполняться при возникновении тех или иных событий, например, если пользователь нажимает кнопку или сообщение поступает в очередь.</span><span class="sxs-lookup"><span data-stu-id="6a664-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="6a664-104">При порождении события запускается получивший его обработчик или несколько обработчиков.</span><span class="sxs-lookup"><span data-stu-id="6a664-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="6a664-105">События могут назначаться сразу нескольким обработчикам, а методы, которые управляют конкретными событиями, можно изменять динамически.</span><span class="sxs-lookup"><span data-stu-id="6a664-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="6a664-106">Для создания обработчиков событий также можно использовать конструктор Windows Forms в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6a664-106">You can also use the Windows Forms Designer in Visual Studio to create event handlers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6a664-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="6a664-107">In This Section</span></span>

 <span data-ttu-id="6a664-108">[Общие сведения о событиях](events-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="6a664-108">[Events Overview](events-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="6a664-109">Объясняет модель событий и роли делегатов.</span><span class="sxs-lookup"><span data-stu-id="6a664-109">Explains the event model and the role of delegates.</span></span>

 <span data-ttu-id="6a664-110">[Общие сведения об обработчиках событий](event-handlers-overview-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="6a664-110">[Event Handlers Overview](event-handlers-overview-windows-forms.md)</span></span>\
 <span data-ttu-id="6a664-111">Описывает порядок обработки событий.</span><span class="sxs-lookup"><span data-stu-id="6a664-111">Describes how to handle events.</span></span>

 <span data-ttu-id="6a664-112">[Практическое руководство. Создание обработчиков событий во время выполнения для Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="6a664-112">[How to: Create Event Handlers at Run Time for Windows Forms](how-to-create-event-handlers-at-run-time-for-windows-forms.md)</span></span>\
 <span data-ttu-id="6a664-113">Динамически выдает инструкции по реагированию на системные или пользовательские события.</span><span class="sxs-lookup"><span data-stu-id="6a664-113">Gives directions for responding to system or user events dynamically.</span></span>

 <span data-ttu-id="6a664-114">[Практическое руководство. Подключение нескольких событий к одному обработчику событий в Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="6a664-114">[How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)</span></span>\
 <span data-ttu-id="6a664-115">Выдает инструкции по назначению одной и той же функциональности нескольким элементам управления с помощью событий.</span><span class="sxs-lookup"><span data-stu-id="6a664-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>

 <span data-ttu-id="6a664-116">[Порядок событий в Windows Forms](order-of-events-in-windows-forms.md)</span><span class="sxs-lookup"><span data-stu-id="6a664-116">[Order of Events in Windows Forms](order-of-events-in-windows-forms.md)</span></span>\
 <span data-ttu-id="6a664-117">Описывает порядок порождения событий в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6a664-117">Describes the order in which events are raised in Windows Forms controls.</span></span>

 <span data-ttu-id="6a664-118">[Практическое руководство. Создание обработчиков событий с помощью](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) конструктора описывает, как использовать конструктор Windows Forms для создания обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="6a664-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)) Describes how to use the Windows Forms Designer to create event handlers.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6a664-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6a664-119">Related Sections</span></span>

 <span data-ttu-id="6a664-120">[События](../../standard/events/index.md)</span><span class="sxs-lookup"><span data-stu-id="6a664-120">[Events](../../standard/events/index.md)</span></span>\
 <span data-ttu-id="6a664-121">Содержит ссылки на разделы, посвященные обработке и вызову событий с помощью .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6a664-121">Provides links to topics on handling and raising events using the .NET Framework.</span></span>

 <span data-ttu-id="6a664-122">[Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span><span class="sxs-lookup"><span data-stu-id="6a664-122">[Troubleshooting Inherited Event Handlers in Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)</span></span>\
 <span data-ttu-id="6a664-123">Представляет распространенные проблемы, возникающие у обработчиков событий в наследуемых компонентах.</span><span class="sxs-lookup"><span data-stu-id="6a664-123">Lists common issues that occur with event handlers in inherited components.</span></span>
