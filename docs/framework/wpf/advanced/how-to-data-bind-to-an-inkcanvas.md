---
title: "Практическое руководство. Выполнение привязки данных к объекту класса InkCanvas | Microsoft Docs"
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
  - "InkCanvas, привязка данных к"
  - "Привязка данных к InkCanvas"
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# Практическое руководство. Выполнение привязки данных к объекту класса InkCanvas
## <a name="example"></a>Пример  
 В следующем примере демонстрируется привязка <xref:System.Windows.Controls.InkCanvas.Strokes%2A> свойство <xref:System.Windows.Controls.InkCanvas> в другой <xref:System.Windows.Controls.InkCanvas>.  
  
 [!code-xml[InkCanvasBindingSnippet#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 В следующем примере демонстрируется привязка <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> свойства в источнике данных.  
  
 [!code-xml[InkCanvasBindingSnippet#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xml[InkCanvasBindingSnippet#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 В следующем примере объявляется два <xref:System.Windows.Controls.InkCanvas> объектов в XAML и устанавливает привязку данных между ними и другими источниками данных.  Первый <xref:System.Windows.Controls.InkCanvas>, который называется `ic`, привязан к двум источникам данных.  <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> и <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> свойства `ic` привязаны к <xref:System.Windows.Controls.ListBox> объекты, которые в свою очередь привязывается к массивам, определенным в XAML.  <xref:System.Windows.Controls.InkCanvas.EditingMode%2A>, <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>, и <xref:System.Windows.Controls.InkCanvas.Strokes%2A> второго <xref:System.Windows.Controls.InkCanvas> привязаны к первому <xref:System.Windows.Controls.InkCanvas>, `ic`.  
  
 [!code-xml[InkCanvasBindingSnippet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]