---
title: "Практическое руководство. Изменение размеров холста с помощью бегунка | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Canvas - элемент управления"
  - "элементы управления, Canvas"
  - "элементы управления, Бегунок"
  - "изменение размеров элемента управления Canvas"
  - "Thumb - элемент управления"
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Изменение размеров холста с помощью бегунка
В этом примере показано использование элемента управления <xref:System.Windows.Controls.Primitives.Thumb> для изменения размера элемента управления <xref:System.Windows.Controls.Canvas>.  
  
## Пример  
 Элемент управления <xref:System.Windows.Controls.Primitives.Thumb> предоставляет функцию перетаскивания, которая может использоваться для перемещения или изменения размера элементов управления, отслеживая событий <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> элемента управления <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 Пользователь начинает операцию перетаскивания нажатием левой кнопки мыши при приостановке указателя мыши на элементе управления <xref:System.Windows.Controls.Primitives.Thumb>.  Операция перетаскивания продолжается до тех пор, пока левая кнопка мыши остается нажатой.  Во время операции перетаскивания <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> может происходить несколько раз.  При каждом его возникновении класс <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> предоставляет возможность изменения положения в соответствии с изменением положения курсора мыши.  Когда пользователь отпускает кнопку мыши, перетаскивание завершается.  Операция перетаскивания предоставляет только новые координаты; она автоматически не перемещает <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 В следующем примере показан элемент управления <xref:System.Windows.Controls.Primitives.Thumb>, являющийся дочерним элементом элемента управления <xref:System.Windows.Controls.Canvas>.  Его обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> предоставляет логику перемещения <xref:System.Windows.Controls.Primitives.Thumb> и изменения размеров <xref:System.Windows.Controls.Canvas>.  Обработчики событий <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> и <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> изменяют цвет <xref:System.Windows.Controls.Primitives.Thumb> во время операции перетаскивания.  В следующем примере определяется <xref:System.Windows.Controls.Primitives.Thumb>.  
  
 [!code-xml[Thumb#thumb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>, который в ответ на движение мыши перемещает элемент <xref:System.Windows.Controls.Primitives.Thumb> и изменяет размеры элемента <xref:System.Windows.Controls.Canvas>.  
  
 [!code-csharp[Thumb#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>.  
  
 [!code-csharp[Thumb#DragStartedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 В следующем примере показан обработчик событий <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>.  
  
 [!code-csharp[Thumb#DragCompletedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Полный код примера см. на веб\-странице [Пример Thumb Drag Functionality](http://go.microsoft.com/fwlink/?LinkID=160042).  
  
## См. также  
 <xref:System.Windows.Controls.Primitives.Thumb>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>   
 <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>