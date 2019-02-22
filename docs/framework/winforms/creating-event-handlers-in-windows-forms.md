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
ms.openlocfilehash: c77a004d52afc67a3811ff98e9a62c788c001803
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/22/2019
ms.locfileid: "56664787"
---
# <a name="creating-event-handlers-in-windows-forms"></a><span data-ttu-id="f4551-102">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4551-102">Creating Event Handlers in Windows Forms</span></span>
<span data-ttu-id="f4551-103">Обработчик событий — это процедура в коде, определяющая, какие действия должны выполняться при возникновении тех или иных событий, например, если пользователь нажимает кнопку или сообщение поступает в очередь.</span><span class="sxs-lookup"><span data-stu-id="f4551-103">An event handler is a procedure in your code that determines what actions are performed when an event occurs, such as when the user clicks a button or a message queue receives a message.</span></span> <span data-ttu-id="f4551-104">При порождении события запускается получивший его обработчик или несколько обработчиков.</span><span class="sxs-lookup"><span data-stu-id="f4551-104">When an event is raised, the event handler or handlers that receive the event are executed.</span></span> <span data-ttu-id="f4551-105">События могут назначаться сразу нескольким обработчикам, а методы, которые управляют конкретными событиями, можно изменять динамически.</span><span class="sxs-lookup"><span data-stu-id="f4551-105">Events can be assigned to multiple handlers, and the methods that handle particular events can be changed dynamically.</span></span> <span data-ttu-id="f4551-106">Для создания обработчиков событий можно также использовать Конструктор Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f4551-106">You can also use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f4551-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f4551-107">In This Section</span></span>  
 [<span data-ttu-id="f4551-108">Общие сведения о событиях</span><span class="sxs-lookup"><span data-stu-id="f4551-108">Events Overview</span></span>](../../../docs/framework/winforms/events-overview-windows-forms.md)  
 <span data-ttu-id="f4551-109">Объясняет модель событий и роли делегатов.</span><span class="sxs-lookup"><span data-stu-id="f4551-109">Explains the event model and the role of delegates.</span></span>  
  
 [<span data-ttu-id="f4551-110">Общие сведения об обработчиках событий</span><span class="sxs-lookup"><span data-stu-id="f4551-110">Event Handlers Overview</span></span>](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)  
 <span data-ttu-id="f4551-111">Описывает порядок обработки событий.</span><span class="sxs-lookup"><span data-stu-id="f4551-111">Describes how to handle events.</span></span>  
  
 [<span data-ttu-id="f4551-112">Практическое руководство. Создание обработчиков событий во время выполнения для форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4551-112">How to: Create Event Handlers at Run Time for Windows Forms</span></span>](../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md)  
 <span data-ttu-id="f4551-113">Динамически выдает инструкции по реагированию на системные или пользовательские события.</span><span class="sxs-lookup"><span data-stu-id="f4551-113">Gives directions for responding to system or user events dynamically.</span></span>  
  
 [<span data-ttu-id="f4551-114">Практическое руководство. Подключение нескольких событий к одному обработчику в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4551-114">How to: Connect Multiple Events to a Single Event Handler in Windows Forms</span></span>](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)  
 <span data-ttu-id="f4551-115">Выдает инструкции по назначению одной и той же функциональности нескольким элементам управления с помощью событий.</span><span class="sxs-lookup"><span data-stu-id="f4551-115">Gives directions for assigning the same functionality to multiple controls through events.</span></span>  
  
 [<span data-ttu-id="f4551-116">Порядок событий в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4551-116">Order of Events in Windows Forms</span></span>](../../../docs/framework/winforms/order-of-events-in-windows-forms.md)  
 <span data-ttu-id="f4551-117">Описывает порядок порождения событий в элементах управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f4551-117">Describes the order in which events are raised in Windows Forms controls.</span></span>  
  
 <span data-ttu-id="f4551-118">[Практическое руководство. Создание обработчиков событий с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f4551-118">[How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100))</span></span>  
 <span data-ttu-id="f4551-119">Описывает использование Конструктора Windows Forms для создания обработчиков событий.</span><span class="sxs-lookup"><span data-stu-id="f4551-119">Describes how to use the Windows Forms Designer to create event handlers.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f4551-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f4551-120">Related Sections</span></span>  
 [<span data-ttu-id="f4551-121">События</span><span class="sxs-lookup"><span data-stu-id="f4551-121">Events</span></span>](../../../docs/standard/events/index.md)  
 <span data-ttu-id="f4551-122">Содержит ссылки на разделы по обработке и порождению событий с помощью [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4551-122">Provides links to topics on handling and raising events using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [<span data-ttu-id="f4551-123">Устранение неполадок, связанных с унаследованными обработчиками событий, в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f4551-123">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)  
 <span data-ttu-id="f4551-124">Представляет распространенные проблемы, возникающие у обработчиков событий в наследуемых компонентах.</span><span class="sxs-lookup"><span data-stu-id="f4551-124">Lists common issues that occur with event handlers in inherited components.</span></span>
