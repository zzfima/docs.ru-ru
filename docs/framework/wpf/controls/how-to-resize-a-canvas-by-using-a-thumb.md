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
ms.openlocfilehash: 80b873e81acc243ff61257bc305c4f782b5bf867
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351833"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="0b8f8-102">Практическое руководство. Изменение размеров холста с помощью бегунка</span><span class="sxs-lookup"><span data-stu-id="0b8f8-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="0b8f8-103">В этом примере показано, как использовать <xref:System.Windows.Controls.Primitives.Thumb> изменение размера элемента управления <xref:System.Windows.Controls.Canvas> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b8f8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0b8f8-104">Example</span></span>  
 <span data-ttu-id="0b8f8-105"><xref:System.Windows.Controls.Primitives.Thumb> Элемент управления предоставляет функциональные возможности перетаскивания, который может использоваться для перемещения или изменения размеров элементов управления, отслеживая <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> события <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="0b8f8-106">Пользователь начинает операцию перетаскивания, нажав клавишу левой кнопки мыши при наведении указателя мыши на <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="0b8f8-107">Операция перетаскивания продолжается до тех пор, пока остается нажатой левую кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="0b8f8-108">Во время операции перетаскивания <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> может встречаться несколько раз.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="0b8f8-109">Каждый раз, оно возникает, <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> класс обеспечивает изменение положения в соответствии с изменением положения курсора мыши.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="0b8f8-110">Когда пользователь отпускает левую кнопку мыши, операция перетаскивания завершена.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="0b8f8-111">Операция перетаскивания предоставляет только новые координаты; его положение не автоматически <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="0b8f8-112">В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb> управления, являющийся дочерним элементом элемента <xref:System.Windows.Controls.Canvas> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="0b8f8-113">Обработчик событий для его <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> событие предоставляет логику перемещения <xref:System.Windows.Controls.Primitives.Thumb> и измените размер <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="0b8f8-114">Обработчики событий для <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> событий изменения цвета <xref:System.Windows.Controls.Primitives.Thumb> во время операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="0b8f8-115">В следующем примере определяется <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="0b8f8-116">В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> обработчик событий, который перемещает <xref:System.Windows.Controls.Primitives.Thumb> и изменяет размер <xref:System.Windows.Controls.Canvas> в ответ на движения мыши.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="0b8f8-117">В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="0b8f8-118">В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="0b8f8-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="0b8f8-119">Полный пример см. в разделе [Пример перетаскивания бегунка](https://go.microsoft.com/fwlink/?LinkID=160042).</span><span class="sxs-lookup"><span data-stu-id="0b8f8-119">For the complete sample, see [Thumb Drag Functionality Sample](https://go.microsoft.com/fwlink/?LinkID=160042).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b8f8-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0b8f8-120">See also</span></span>
- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
