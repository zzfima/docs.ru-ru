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
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124303"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a><span data-ttu-id="65ec7-102">Практическое руководство. Изменение размеров холста с помощью бегунка</span><span class="sxs-lookup"><span data-stu-id="65ec7-102">How to: Resize a Canvas by Using a Thumb</span></span>
<span data-ttu-id="65ec7-103">В этом примере показано, как использовать элемент управления <xref:System.Windows.Controls.Primitives.Thumb> для изменения размера элемента управления <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="65ec7-103">This example shows how to use a <xref:System.Windows.Controls.Primitives.Thumb> control to resize a <xref:System.Windows.Controls.Canvas> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65ec7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="65ec7-104">Example</span></span>  
 <span data-ttu-id="65ec7-105">Элемент управления <xref:System.Windows.Controls.Primitives.Thumb> предоставляет функциональные возможности перетаскивания, которые можно использовать для перемещения или изменения размеров элементов управления за счет мониторинга <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> событий <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="65ec7-105">The <xref:System.Windows.Controls.Primitives.Thumb> control provides drag functionality that can be used to move or resize controls by monitoring the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> events of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="65ec7-106">Пользователь начинает операцию перетаскивания нажатием левой кнопки мыши, когда указатель мыши приостанавливается на элементе управления <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="65ec7-106">The user begins a drag operation by pressing the left mouse button when the mouse pointer is paused on the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="65ec7-107">Операция перетаскивания продолжается, пока остается нажатой левая кнопка мыши.</span><span class="sxs-lookup"><span data-stu-id="65ec7-107">The drag operation continues as long as the left mouse button remains pressed.</span></span> <span data-ttu-id="65ec7-108">Во время операции перетаскивания <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> может встречаться несколько раз.</span><span class="sxs-lookup"><span data-stu-id="65ec7-108">During the drag operation, the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> can occur more than once.</span></span> <span data-ttu-id="65ec7-109">Каждый раз, когда происходит, класс <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> предоставляет изменение в положении, соответствующее изменению в положении указателя мыши.</span><span class="sxs-lookup"><span data-stu-id="65ec7-109">Each time it occurs, the <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> class provides the change in position that corresponds to the change in mouse position.</span></span> <span data-ttu-id="65ec7-110">Когда пользователь отпускает левую кнопку мыши, операция перетаскивания завершается.</span><span class="sxs-lookup"><span data-stu-id="65ec7-110">When the user releases the left mouse button, the drag operation is finished.</span></span> <span data-ttu-id="65ec7-111">Операция перетаскивания предоставляет только новые координаты; Он не перемещает <xref:System.Windows.Controls.Primitives.Thumb>автоматически.</span><span class="sxs-lookup"><span data-stu-id="65ec7-111">The drag operation only provides new coordinates; it does not automatically reposition the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 <span data-ttu-id="65ec7-112">В следующем примере показан элемент управления <xref:System.Windows.Controls.Primitives.Thumb>, который является дочерним элементом элемента управления <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="65ec7-112">The following example shows a <xref:System.Windows.Controls.Primitives.Thumb> control that is the child element of a <xref:System.Windows.Controls.Canvas> control.</span></span> <span data-ttu-id="65ec7-113">Обработчик событий для события <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> предоставляет логику для перемещения <xref:System.Windows.Controls.Primitives.Thumb> и изменения размера <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="65ec7-113">The event handler for its <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event provides the logic to move the <xref:System.Windows.Controls.Primitives.Thumb> and resize the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="65ec7-114">Обработчики событий для событий <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> изменяют цвет <xref:System.Windows.Controls.Primitives.Thumb> во время операции перетаскивания.</span><span class="sxs-lookup"><span data-stu-id="65ec7-114">The event handlers for the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> and <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event change the color of the <xref:System.Windows.Controls.Primitives.Thumb> during a drag operation.</span></span> <span data-ttu-id="65ec7-115">В следующем примере определяется <xref:System.Windows.Controls.Primitives.Thumb>.</span><span class="sxs-lookup"><span data-stu-id="65ec7-115">The following example defines the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 <span data-ttu-id="65ec7-116">В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>, который перемещает <xref:System.Windows.Controls.Primitives.Thumb> и изменяет размер <xref:System.Windows.Controls.Canvas> в ответ на перемещение мыши.</span><span class="sxs-lookup"><span data-stu-id="65ec7-116">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> event handler that moves the <xref:System.Windows.Controls.Primitives.Thumb> and resizes the <xref:System.Windows.Controls.Canvas> in response to a mouse movement.</span></span>  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 <span data-ttu-id="65ec7-117">В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>.</span><span class="sxs-lookup"><span data-stu-id="65ec7-117">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 <span data-ttu-id="65ec7-118">В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>.</span><span class="sxs-lookup"><span data-stu-id="65ec7-118">The following example shows the <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> event handler.</span></span>  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 <span data-ttu-id="65ec7-119">Полный пример см. в разделе [пример функции перетаскивания бегунка](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span><span class="sxs-lookup"><span data-stu-id="65ec7-119">For the complete sample, see [Thumb Drag Functionality Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65ec7-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="65ec7-120">See also</span></span>

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
