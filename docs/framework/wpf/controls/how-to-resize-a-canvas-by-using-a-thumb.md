---
title: Практическое руководство. Изменение размеров холста с помощью бегунка
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: c3e7176b0578c8fdc5f4331ad8f3b464f3a88b51
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="2770b-102">Практическое руководство. Изменение размеров холста с помощью бегунка</span><span class="sxs-lookup"><span data-stu-id="2770b-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="2770b-103">В этом примере показано, как использовать <xref:System.Windows.Controls.Primitives.Thumb> изменение размера элемента управления <xref:System.Windows.Controls.Canvas> управления.</span><span class="sxs-lookup"><span data-stu-id="2770b-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2770b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="2770b-104">Example</span></span>  
 <span data-ttu-id="2770b-105"><xref:System.Windows.Controls.Primitives.Thumb> Управления предоставляет функцию перетаскивания, которая может использоваться для перемещения или изменения размеров элементов управления, отслеживая <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> события <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="2770b-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="2770b-106">Пользователь начинает операцию перетаскивания нажатием левой кнопки мыши при наведении указателя мыши на <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2770b-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="2770b-107">Операция перетаскивания продолжается до тех пор, пока остается нажатой левую кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="2770b-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="2770b-108">Во время операции перетаскивания <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> может встречаться несколько раз.</span><span class="sxs-lookup"><span data-stu-id="2770b-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="2770b-109">Каждом его обнаружении <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> класс предоставляет изменений в позиции, в соответствии с изменением положения курсора мыши.</span><span class="sxs-lookup"><span data-stu-id="2770b-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="2770b-110">Когда пользователь отпускает левую кнопку мыши, завершения операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2770b-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="2770b-111">Операция перетаскивания предоставляет только новые координаты; он автоматически не перемещает <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="2770b-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="2770b-112">В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb> управления, являющийся дочерним элементом элемента <xref:System.Windows.Controls.Canvas> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="2770b-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="2770b-113">Обработчик событий для его <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> предоставляет логику для перемещения <xref:System.Windows.Controls.Primitives.Thumb> и измените размер <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="2770b-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="2770b-114">Обработчики событий для <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> событий изменения цвета <xref:System.Windows.Controls.Primitives.Thumb> во время операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="2770b-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="2770b-115">В следующем примере определяется <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="2770b-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="2770b-116">В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> обработчик событий, который перемещает <xref:System.Windows.Controls.Primitives.Thumb> и изменять размеры <xref:System.Windows.Controls.Canvas> в ответ на движения мыши.</span><span class="sxs-lookup"><span data-stu-id="2770b-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="2770b-117">В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="2770b-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="2770b-118">В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="2770b-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="2770b-119">Полный пример см. в разделе [Пример перетаскивания бегунка](http://go.microsoft.com/fwlink/?LinkID=160042).</span><span class="sxs-lookup"><span data-stu-id="2770b-119">For the complete sample, see [Thumb Drag Functionality Sample](http://go.microsoft.com/fwlink/?LinkID=160042).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2770b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2770b-120">See Also</span></span>  
 <xref:System.Windows.Controls.Primitives.Thumb>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
