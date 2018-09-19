---
title: Обработка введенных пользователем данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], user input using code
- custom controls [Windows Forms], keyboard events using code
- custom controls [Windows Forms], mouse events using code
ms.assetid: d9b12787-86f6-4022-8e0f-e12d312c4af2
ms.openlocfilehash: 19bb494d6f478c8cb7adda770f441470c4b2d19f
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "45969656"
---
# <a name="handling-user-input"></a><span data-ttu-id="44e4d-102">Обработка введенных пользователем данных</span><span class="sxs-lookup"><span data-stu-id="44e4d-102">Handling User Input</span></span>
<span data-ttu-id="44e4d-103">В этом разделе описываются основные события клавиатуры и мыши, предоставляемые <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="44e4d-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="44e4d-104">При обработке события разработчики элементов управления должны переопределить защищенный `On` метод *EventName*, а не подключить делегат к событию.</span><span class="sxs-lookup"><span data-stu-id="44e4d-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="44e4d-105">Сведения о событиях см. в разделе [Инициирование событий из компонента](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span><span class="sxs-lookup"><span data-stu-id="44e4d-105">For a review of events, see [Raising Events from a Component](https://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44e4d-106">Если нет данных связанные с событием, экземпляр базового класса <xref:System.EventArgs> передается в качестве аргумента для `On` *EventName* метод.</span><span class="sxs-lookup"><span data-stu-id="44e4d-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="44e4d-107">События клавиатуры</span><span class="sxs-lookup"><span data-stu-id="44e4d-107">Keyboard Events</span></span>  
 <span data-ttu-id="44e4d-108">Общими событиями клавиатуры, которые может обрабатывать элемент управления, <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, и <xref:System.Windows.Forms.Control.KeyUp>.</span><span class="sxs-lookup"><span data-stu-id="44e4d-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="44e4d-109">Имя события</span><span class="sxs-lookup"><span data-stu-id="44e4d-109">Event Name</span></span>|<span data-ttu-id="44e4d-110">Метод для переопределения</span><span class="sxs-lookup"><span data-stu-id="44e4d-110">Method to Override</span></span>|<span data-ttu-id="44e4d-111">Описание события</span><span class="sxs-lookup"><span data-stu-id="44e4d-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="44e4d-112">Возникает только при первоначальном нажатии клавиши.</span><span class="sxs-lookup"><span data-stu-id="44e4d-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="44e4d-113">Возникает при каждом нажатии клавиши.</span><span class="sxs-lookup"><span data-stu-id="44e4d-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="44e4d-114">Если удерживается клавиша, <xref:System.Windows.Forms.Control.KeyPress> события с частотой повторения, определенные операционной системой.</span><span class="sxs-lookup"><span data-stu-id="44e4d-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="44e4d-115">Возникает при отпускании клавиши.</span><span class="sxs-lookup"><span data-stu-id="44e4d-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="44e4d-116">Обработка ввода с клавиатуры значительно сложнее, чем переопределение событий в предыдущей таблице и в данном разделе не рассматривается.</span><span class="sxs-lookup"><span data-stu-id="44e4d-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="44e4d-117">Дополнительные сведения см. в разделе [Ввод данных пользователем в Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="44e4d-117">For more information, see [User Input in Windows Forms](../../../../docs/framework/winforms/user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="44e4d-118">События мыши</span><span class="sxs-lookup"><span data-stu-id="44e4d-118">Mouse Events</span></span>  
 <span data-ttu-id="44e4d-119">События мыши, которые может обрабатывать элемент управления: <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, и <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="44e4d-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="44e4d-120">Имя события</span><span class="sxs-lookup"><span data-stu-id="44e4d-120">Event Name</span></span>|<span data-ttu-id="44e4d-121">Метод для переопределения</span><span class="sxs-lookup"><span data-stu-id="44e4d-121">Method to Override</span></span>|<span data-ttu-id="44e4d-122">Описание события</span><span class="sxs-lookup"><span data-stu-id="44e4d-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="44e4d-123">Возникает при нажатии кнопки мыши, когда указатель мыши находится на элементе управления.</span><span class="sxs-lookup"><span data-stu-id="44e4d-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="44e4d-124">Возникает, когда указатель мыши впервые входит в область элемента управления.</span><span class="sxs-lookup"><span data-stu-id="44e4d-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="44e4d-125">Возникает, когда указатель мыши наводится на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="44e4d-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="44e4d-126">Возникает, когда указатель мыши покидает область элемента управления.</span><span class="sxs-lookup"><span data-stu-id="44e4d-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="44e4d-127">Возникает, когда указатель мыши перемещается в область элемента управления.</span><span class="sxs-lookup"><span data-stu-id="44e4d-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="44e4d-128">Возникает при отпускании кнопки мыши, когда указатель мыши находится на элементе управления или покидает область элемента управления.</span><span class="sxs-lookup"><span data-stu-id="44e4d-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="44e4d-129">В следующем фрагменте кода показан пример переопределения <xref:System.Windows.Forms.Control.MouseDown> событий.</span><span class="sxs-lookup"><span data-stu-id="44e4d-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="44e4d-130">В следующем фрагменте кода показан пример переопределения <xref:System.Windows.Forms.Control.MouseMove> событий.</span><span class="sxs-lookup"><span data-stu-id="44e4d-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="44e4d-131">В следующем фрагменте кода показан пример переопределения <xref:System.Windows.Forms.Control.MouseUp> событий.</span><span class="sxs-lookup"><span data-stu-id="44e4d-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="44e4d-132">Полный исходный код для примера `FlashTrackBar` см. в разделе [Практическое руководство. Создание элемента управления, показывающего прогресс в форме Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="44e4d-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](../../../../docs/framework/winforms/controls/how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e4d-133">См. также</span><span class="sxs-lookup"><span data-stu-id="44e4d-133">See Also</span></span>  
 [<span data-ttu-id="44e4d-134">События элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="44e4d-134">Events in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/events-in-windows-forms-controls.md)  
 [<span data-ttu-id="44e4d-135">Определение событий</span><span class="sxs-lookup"><span data-stu-id="44e4d-135">Defining an Event</span></span>](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [<span data-ttu-id="44e4d-136">События</span><span class="sxs-lookup"><span data-stu-id="44e4d-136">Events</span></span>](../../../../docs/standard/events/index.md)  
 [<span data-ttu-id="44e4d-137">Ввод данных пользователем в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="44e4d-137">User Input in Windows Forms</span></span>](../../../../docs/framework/winforms/user-input-in-windows-forms.md)
