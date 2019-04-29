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
ms.openlocfilehash: f969769725ae099ddf477fd11efb03277a555fa6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967106"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="3c867-102">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c867-102">Creating Event Handlers in Windows Forms</span></span>
<span data-ttu-id="3c867-103">Обработчик событий — это процедура в коде, определяющая, какие действия должны выполняться при возникновении тех или иных событий, например, если пользователь нажимает кнопку или сообщение поступает в очередь.</span><span class="sxs-lookup"><span data-stu-id="3c867-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="3c867-104">При порождении события запускается получивший его обработчик или несколько обработчиков.</span><span class="sxs-lookup"><span data-stu-id="3c867-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="3c867-105">События могут назначаться сразу нескольким обработчикам, а методы, которые управляют конкретными событиями, можно изменять динамически.</span><span class="sxs-lookup"><span data-stu-id="3c867-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="3c867-106">Для создания обработчиков событий можно также использовать Конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3c867-106">You can also use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c867-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="3c867-107">In This Section</span></span>  
 [<span data-ttu-id="3c867-108">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="3c867-108">Events Overview</span></span>](events-overview-windows-forms.md)  
 <span data-ttu-id="3c867-109">Объясняет модель событий и роли делегатов.</span><span class="sxs-lookup"><span data-stu-id="3c867-109">Explains the event model and the role of delegates.</span></span>  
  
 [<span data-ttu-id="3c867-110">Общие сведения об обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="3c867-110">Event Handlers Overview</span></span>](event-handlers-overview-windows-forms.md)  
 <span data-ttu-id="3c867-111">Описывает порядок обработки событий.</span><span class="sxs-lookup"><span data-stu-id="3c867-111">Describes how to handle events.</span></span>  
  
 [<span data-ttu-id="3c867-112">Практическое руководство. Создание обработчиков событий во время выполнения для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c867-112">How to: Create Event Handlers at Run Time for Windows Forms</span></span>](how-to-create-event-handlers-at-run-time-for-windows-forms.md)  
 <span data-ttu-id="3c867-113">Динамически выдает инструкции по реагированию на системные или пользовательские события.</span><span class="sxs-lookup"><span data-stu-id="3c867-113">Gives directions for responding to system or user events dynamically.</span></span>  
  
 [<span data-ttu-id="3c867-114">Практическое руководство. Подключение нескольких событий к одному обработчику в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c867-114">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)  
 <span data-ttu-id="3c867-115">Выдает инструкции по назначению одной и той же функциональности нескольким элементам управления с помощью событий.</span><span class="sxs-lookup"><span data-stu-id="3c867-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>  
  
 [<span data-ttu-id="3c867-116">Порядок событий в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3c867-116">Order of Events in Windows Forms</span></span>](order-of-events-in-windows-forms.md)  
 <span data-ttu-id="3c867-117">Описывает порядок порождения событий в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="3c867-117">Describes the order in which events are raised in Windows Forms controls.</span></span>  
  
 <span data-ttu-id="3c867-118">[Практическое руководство. Создание обработчиков событий с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3c867-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))</span></span>  
 <span data-ttu-id="3c867-119">Описывает использование Конструктора Windows Forms для создания обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="3c867-119">Describes how to use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3c867-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3c867-120">Related Sections</span></span>  
 [<span data-ttu-id="3c867-121">События</span><span class="sxs-lookup"><span data-stu-id="3c867-121">Events</span></span>](../../standard/events/index.md)  
 <span data-ttu-id="3c867-122">Содержит ссылки на разделы по обработке и порождению событий с помощью [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3c867-122">Provides links to topics on handling and raising events using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [<span data-ttu-id="3c867-123">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3c867-123">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="3c867-124">Представляет распространенные проблемы, возникающие у обработчиков событий в наследуемых компонентах.</span><span class="sxs-lookup"><span data-stu-id="3c867-124">Lists common issues that occur with event handlers in inherited components.</span></span>
