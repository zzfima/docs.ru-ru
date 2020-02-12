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
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Практическое руководство. Изменение размеров холста с помощью бегунка
В этом примере показано, как использовать элемент управления <xref:System.Windows.Controls.Primitives.Thumb> для изменения размера элемента управления <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Пример  
 Элемент управления <xref:System.Windows.Controls.Primitives.Thumb> предоставляет функциональные возможности перетаскивания, которые можно использовать для перемещения или изменения размеров элементов управления за счет мониторинга <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> событий <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 Пользователь начинает операцию перетаскивания нажатием левой кнопки мыши, когда указатель мыши приостанавливается на элементе управления <xref:System.Windows.Controls.Primitives.Thumb>. Операция перетаскивания продолжается, пока остается нажатой левая кнопка мыши. Во время операции перетаскивания <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> может встречаться несколько раз. Каждый раз, когда происходит, класс <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> предоставляет изменение в положении, соответствующее изменению в положении указателя мыши. Когда пользователь отпускает левую кнопку мыши, операция перетаскивания завершается. Операция перетаскивания предоставляет только новые координаты; Он не перемещает <xref:System.Windows.Controls.Primitives.Thumb>автоматически.  
  
 В следующем примере показан элемент управления <xref:System.Windows.Controls.Primitives.Thumb>, который является дочерним элементом элемента управления <xref:System.Windows.Controls.Canvas>. Обработчик событий для события <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> предоставляет логику для перемещения <xref:System.Windows.Controls.Primitives.Thumb> и изменения размера <xref:System.Windows.Controls.Canvas>. Обработчики событий для событий <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> изменяют цвет <xref:System.Windows.Controls.Primitives.Thumb> во время операции перетаскивания. В следующем примере определяется <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>, который перемещает <xref:System.Windows.Controls.Primitives.Thumb> и изменяет размер <xref:System.Windows.Controls.Canvas> в ответ на перемещение мыши.  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>.  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>.  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Полный пример см. в разделе [пример функции перетаскивания бегунка](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
