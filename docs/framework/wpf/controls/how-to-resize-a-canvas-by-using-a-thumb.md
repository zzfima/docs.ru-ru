---
title: "Практическое руководство. Изменение размеров холста с помощью бегунка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 757745b24c8e9e281d243cd15a5351b01d3479ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Практическое руководство. Изменение размеров холста с помощью бегунка
В этом примере показано, как использовать <xref:System.Windows.Controls.Primitives.Thumb> изменение размера элемента управления <xref:System.Windows.Controls.Canvas> управления.  
  
## <a name="example"></a>Пример  
 <xref:System.Windows.Controls.Primitives.Thumb> Управления предоставляет функцию перетаскивания, которая может использоваться для перемещения или изменения размеров элементов управления, отслеживая <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> события <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 Пользователь начинает операцию перетаскивания нажатием левой кнопки мыши при наведении указателя мыши на <xref:System.Windows.Controls.Primitives.Thumb> элемента управления. Операция перетаскивания продолжается до тех пор, пока остается нажатой левую кнопку мыши. Во время операции перетаскивания <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> может встречаться несколько раз. Каждом его обнаружении <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> класс предоставляет изменений в позиции, в соответствии с изменением положения курсора мыши. Когда пользователь отпускает левую кнопку мыши, завершения операции перетаскивания. Операция перетаскивания предоставляет только новые координаты; он автоматически не перемещает <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb> управления, являющийся дочерним элементом элемента <xref:System.Windows.Controls.Canvas> элемента управления. Обработчик событий для его <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> предоставляет логику для перемещения <xref:System.Windows.Controls.Primitives.Thumb> и измените размер <xref:System.Windows.Controls.Canvas>. Обработчики событий для <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> событий изменения цвета <xref:System.Windows.Controls.Primitives.Thumb> во время операции перетаскивания. В следующем примере определяется <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xaml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> обработчик событий, который перемещает <xref:System.Windows.Controls.Primitives.Thumb> и изменять размеры <xref:System.Windows.Controls.Canvas> в ответ на движения мыши.  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> обработчика событий.  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 В следующем примере показан <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> обработчика событий.  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Полный пример см. в разделе [Пример перетаскивания бегунка](http://go.microsoft.com/fwlink/?LinkID=160042).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Controls.Primitives.Thumb>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>  
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
