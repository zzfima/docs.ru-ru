---
title: "Практическое руководство. Получение или задание свойств размещения Canvas | Microsoft Docs"
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
  - "Canvas - элемент управления, установка свойств позиционирования"
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Получение или задание свойств размещения Canvas
В этом примере показано, как использовать методы размещения элемента <xref:System.Windows.Controls.Canvas> для размещения дочернего элемента.  В этом примере содержимое в <xref:System.Windows.Controls.ListBoxItem> используется для представления значений размещения и преобразования их в экземпляры <xref:System.Double>, что необходимо для размещения.  Значения затем преобразуются обратно в строки и отображаются в виде текста в элементе <xref:System.Windows.Controls.TextBlock> с помощью метода <xref:System.Windows.Controls.Canvas.GetLeft%2A>.  
  
## Пример  
 В следующем примере создается элемент <xref:System.Windows.Controls.ListBox>, который содержит одиннадцать выбираемых элементов <xref:System.Windows.Controls.ListBoxItem>.  Событие <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> вызывает пользовательский метод `ChangeLeft`, который определяется в последующем блоке кода.  
  
 Каждый <xref:System.Windows.Controls.ListBoxItem> представляет значение <xref:System.Double>, которое является одним из аргументов, принимаемых методом <xref:System.Windows.Controls.Canvas.SetLeft%2A> для <xref:System.Windows.Controls.Canvas>.  Чтобы использовать <xref:System.Windows.Controls.ListBoxItem> для представления экземпляра <xref:System.Double>, необходимо сначала преобразовать <xref:System.Windows.Controls.ListBoxItem> к правильному типу данных.  
  
 [!code-xml[CanvasPositioningProperties#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 При изменении выделения <xref:System.Windows.Controls.ListBox> пользователем, вызывается пользовательский метод `ChangeLeft`.  Этот метод передает <xref:System.Windows.Controls.ListBoxItem> в объект <xref:System.Windows.LengthConverter>, который преобразует <xref:System.Windows.Controls.ContentControl.Content%2A> для <xref:System.Windows.Controls.ListBoxItem> в экземпляр <xref:System.Double> \(обратите внимание, что это значение уже было преобразовано к <xref:System.String> с помощью метода <xref:System.Windows.Controls.Control.ToString%2A>\).  Это значение затем передается обратно методам <xref:System.Windows.Controls.Canvas.SetLeft%2A> и <xref:System.Windows.Controls.Canvas.GetLeft%2A> для <xref:System.Windows.Controls.Canvas>, чтобы изменить положение объекта `text1`.  
  
 [!code-csharp[CanvasPositioningProperties#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## См. также  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.ListBoxItem>   
 <xref:System.Windows.LengthConverter>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)