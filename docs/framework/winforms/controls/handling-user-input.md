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
ms.openlocfilehash: 3ebe82fc18deba52fafe76da7ff85fb247446e46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074959"
---
# <a name="handling-user-input"></a><span data-ttu-id="0b6bc-102">Обработка введенных пользователем данных</span><span class="sxs-lookup"><span data-stu-id="0b6bc-102">Handling User Input</span></span>
<span data-ttu-id="0b6bc-103">В этом разделе описываются основные события клавиатуры и мыши, предоставляемые <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-103">This topic describes the main keyboard and mouse events provided by <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0b6bc-104">При обработке события разработчики элементов управления должны переопределить защищенный `On` метод *EventName*, а не подключить делегат к событию.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-104">When handling an event, control authors should override the protected `On`*EventName* method rather than attaching a delegate to the event.</span></span> <span data-ttu-id="0b6bc-105">Сведения о событиях см. в разделе [Инициирование событий из компонента](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="0b6bc-105">For a review of events, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b6bc-106">Если нет данных связанные с событием, экземпляр базового класса <xref:System.EventArgs> передается в качестве аргумента для `On` *EventName* метод.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-106">If there is no data associated with an event, an instance of the base class <xref:System.EventArgs> is passed as an argument to the `On`*EventName* method.</span></span>  
  
## <a name="keyboard-events"></a><span data-ttu-id="0b6bc-107">События клавиатуры</span><span class="sxs-lookup"><span data-stu-id="0b6bc-107">Keyboard Events</span></span>  
 <span data-ttu-id="0b6bc-108">Общими событиями клавиатуры, которые может обрабатывать элемент управления, <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, и <xref:System.Windows.Forms.Control.KeyUp>.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-108">The common keyboard events that your control can handle are <xref:System.Windows.Forms.Control.KeyDown>, <xref:System.Windows.Forms.Control.KeyPress>, and <xref:System.Windows.Forms.Control.KeyUp>.</span></span>  
  
|<span data-ttu-id="0b6bc-109">Имя события</span><span class="sxs-lookup"><span data-stu-id="0b6bc-109">Event Name</span></span>|<span data-ttu-id="0b6bc-110">Метод для переопределения</span><span class="sxs-lookup"><span data-stu-id="0b6bc-110">Method to Override</span></span>|<span data-ttu-id="0b6bc-111">Описание события</span><span class="sxs-lookup"><span data-stu-id="0b6bc-111">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`KeyDown`|`void OnKeyDown(KeyEventArgs)`|<span data-ttu-id="0b6bc-112">Возникает только при первоначальном нажатии клавиши.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-112">Raised only when a key is initially pressed.</span></span>|  
|`KeyPress`|`void OnKeyPress`<br /><br /> `(KeyPressEventArgs)`|<span data-ttu-id="0b6bc-113">Возникает при каждом нажатии клавиши.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-113">Raised every time a key is pressed.</span></span> <span data-ttu-id="0b6bc-114">Если удерживается клавиша, <xref:System.Windows.Forms.Control.KeyPress> события с частотой повторения, определенные операционной системой.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-114">If a key is held down, a <xref:System.Windows.Forms.Control.KeyPress> event is raised at the repeat rate defined by the operating system.</span></span>|  
|`KeyUp`|`void OnKeyUp(KeyEventArgs)`|<span data-ttu-id="0b6bc-115">Возникает при отпускании клавиши.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-115">Raised when a key is released.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="0b6bc-116">Обработка ввода с клавиатуры значительно сложнее, чем переопределение событий в предыдущей таблице и в данном разделе не рассматривается.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-116">Handling keyboard input is considerably more complex than overriding the events in the preceding table and is beyond the scope of this topic.</span></span> <span data-ttu-id="0b6bc-117">Дополнительные сведения см. в разделе [Ввод данных пользователем в Windows Forms](../user-input-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="0b6bc-117">For more information, see [User Input in Windows Forms](../user-input-in-windows-forms.md).</span></span>  
  
## <a name="mouse-events"></a><span data-ttu-id="0b6bc-118">События мыши</span><span class="sxs-lookup"><span data-stu-id="0b6bc-118">Mouse Events</span></span>  
 <span data-ttu-id="0b6bc-119">События мыши, которые может обрабатывать элемент управления: <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, и <xref:System.Windows.Forms.Control.MouseUp>.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-119">The mouse events that your control can handle are <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseHover>, <xref:System.Windows.Forms.Control.MouseLeave>, <xref:System.Windows.Forms.Control.MouseMove>, and <xref:System.Windows.Forms.Control.MouseUp>.</span></span>  
  
|<span data-ttu-id="0b6bc-120">Имя события</span><span class="sxs-lookup"><span data-stu-id="0b6bc-120">Event Name</span></span>|<span data-ttu-id="0b6bc-121">Метод для переопределения</span><span class="sxs-lookup"><span data-stu-id="0b6bc-121">Method to Override</span></span>|<span data-ttu-id="0b6bc-122">Описание события</span><span class="sxs-lookup"><span data-stu-id="0b6bc-122">Description of Event</span></span>|  
|----------------|------------------------|--------------------------|  
|`MouseDown`|`void OnMouseDown(MouseEventArgs)`|<span data-ttu-id="0b6bc-123">Возникает при нажатии кнопки мыши, когда указатель мыши находится на элементе управления.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-123">Raised when the mouse button is pressed while the pointer is over the control.</span></span>|  
|`MouseEnter`|`void OnMouseEnter(EventArgs)`|<span data-ttu-id="0b6bc-124">Возникает, когда указатель мыши впервые входит в область элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-124">Raised when the pointer first enters the region of the control.</span></span>|  
|`MouseHover`|`void OnMouseHover(EventArgs)`|<span data-ttu-id="0b6bc-125">Возникает, когда указатель мыши наводится на элемент управления.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-125">Raised when the pointer hovers over the control.</span></span>|  
|`MouseLeave`|`void OnMouseLeave(EventArgs)`|<span data-ttu-id="0b6bc-126">Возникает, когда указатель мыши покидает область элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-126">Raised when the pointer leaves the region of the control.</span></span>|  
|`MouseMove`|`void OnMouseMove(MouseEventArgs)`|<span data-ttu-id="0b6bc-127">Возникает, когда указатель мыши перемещается в область элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-127">Raised when the pointer moves in the region of the control.</span></span>|  
|`MouseUp`|`void OnMouseUp(MouseEventArgs)`|<span data-ttu-id="0b6bc-128">Возникает при отпускании кнопки мыши, когда указатель мыши находится на элементе управления или покидает область элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-128">Raised when the mouse button is released while the pointer is over the control or the pointer leaves the region of the control.</span></span>|  
  
 <span data-ttu-id="0b6bc-129">В следующем фрагменте кода показан пример переопределения <xref:System.Windows.Forms.Control.MouseDown> событий.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-129">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseDown> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#7)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#7)]  
  
 <span data-ttu-id="0b6bc-130">В следующем фрагменте кода показан пример переопределения <xref:System.Windows.Forms.Control.MouseMove> событий.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-130">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseMove> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#8)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#8)]  
  
 <span data-ttu-id="0b6bc-131">В следующем фрагменте кода показан пример переопределения <xref:System.Windows.Forms.Control.MouseUp> событий.</span><span class="sxs-lookup"><span data-stu-id="0b6bc-131">The following code fragment shows an example of overriding the <xref:System.Windows.Forms.Control.MouseUp> event.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#9)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#9](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#9)]  
  
 <span data-ttu-id="0b6bc-132">Полный исходный код для `FlashTrackBar` пример, см. в разделе [как: Создание элемента управления Windows Forms, показывающего прогресс](how-to-create-a-windows-forms-control-that-shows-progress.md).</span><span class="sxs-lookup"><span data-stu-id="0b6bc-132">For the complete source code for the `FlashTrackBar` sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b6bc-133">См. также</span><span class="sxs-lookup"><span data-stu-id="0b6bc-133">See also</span></span>

- [<span data-ttu-id="0b6bc-134">События элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0b6bc-134">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
- [<span data-ttu-id="0b6bc-135">Определение событий</span><span class="sxs-lookup"><span data-stu-id="0b6bc-135">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="0b6bc-136">События</span><span class="sxs-lookup"><span data-stu-id="0b6bc-136">Events</span></span>](../../../standard/events/index.md)
- [<span data-ttu-id="0b6bc-137">Ввод данных пользователем в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0b6bc-137">User Input in Windows Forms</span></span>](../user-input-in-windows-forms.md)
