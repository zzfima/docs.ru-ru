---
title: "Практическое руководство. Прокручивание содержимого с помощью интерфейса IScrollInfo | Microsoft Docs"
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
  - "IScrollInfo - интерфейс"
  - "прокрутка содержимого"
  - "ScrollViewer - элемент управления, прокрутка содержимого"
ms.assetid: d8700bef-a3f8-4c12-9de2-fc3b79f32cd3
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Прокручивание содержимого с помощью интерфейса IScrollInfo
В этом примере демонстрируется прокрутка содержимого с помощью интерфейса <xref:System.Windows.Controls.Primitives.IScrollInfo>.  
  
## Пример  
 В следующем примере показаны свойства интерфейса <xref:System.Windows.Controls.Primitives.IScrollInfo>.  В примере создается элемент <xref:System.Windows.Controls.StackPanel> в коде [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], вложенный в родительский элемент управления <xref:System.Windows.Controls.ScrollViewer>.  Дочерние элементы панели <xref:System.Windows.Controls.StackPanel> поддерживают логическую прокрутку с помощью методов, определенных интерфейсом <xref:System.Windows.Controls.Primitives.IScrollInfo>, и приведение к экземпляру <xref:System.Windows.Controls.StackPanel> \(`sp1`\) в коде.  
  
 [!code-xml[IScrollInfoMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml#2)]  
  
 Каждый элемент управления <xref:System.Windows.Controls.Button> в файле [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] вызывает связанный настраиваемый метод, который управляет режимом прокрутки в панели <xref:System.Windows.Controls.StackPanel>.  В следующем примере показано использование методов <xref:System.Windows.Controls.Primitives.IScrollInfo.LineUp%2A> и <xref:System.Windows.Controls.Primitives.IScrollInfo.LineDown%2A>; также в целом показано использование всех методов позиционирования, определенных в классе <xref:System.Windows.Controls.Primitives.IScrollInfo>.  
  
 [!code-csharp[IScrollInfoMethods#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/IScrollInfoMethods/CSharp/Window1.xaml.cs#3)]
 [!code-vb[IScrollInfoMethods#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/IScrollInfoMethods/VisualBasic/Window1.xaml.vb#3)]  
  
## См. также  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.Primitives.IScrollInfo>   
 <xref:System.Windows.Controls.StackPanel>   
 [Общие сведения об элементе управления ScrollViewer](../../../../docs/framework/wpf/controls/scrollviewer-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/scrollviewer-how-to-topics.md)   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)