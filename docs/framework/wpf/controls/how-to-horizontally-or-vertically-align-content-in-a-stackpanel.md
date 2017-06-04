---
title: "Практическое руководство. Выравнивание содержимого в StackPanel по горизонтали или по вертикали | Microsoft Docs"
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
  - "выравнивание, содержание"
  - "выравнивание содержимого"
  - "StackPanel - элемент управления, выравнивание содержимого"
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Выравнивание содержимого в StackPanel по горизонтали или по вертикали
В этом примере показано, как настроить <xref:System.Windows.Controls.StackPanel.Orientation%2A> содержимого в элементе <xref:System.Windows.Controls.StackPanel>, и как настроить <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> содержимого дочернего элемента.  
  
## Пример  
 В следующем примере создаются три элемента <xref:System.Windows.Controls.ListBox> в [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Каждый элемент <xref:System.Windows.Controls.ListBox> представляет возможные значения свойств <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> и <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> элемента <xref:System.Windows.Controls.StackPanel>.  Когда пользователь выбирает значение в любом из элементов <xref:System.Windows.Controls.ListBox>, связанное свойство элемента <xref:System.Windows.Controls.StackPanel> и его дочерних элементов <xref:System.Windows.Controls.Button> изменяется.  
  
 [!code-xml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 Следующий файл с выделенным кодом определяет изменения в событиях, связанных с изменениями выбора <xref:System.Windows.Controls.ListBox>.  <xref:System.Windows.Controls.StackPanel> определяется с помощью <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## См. также  
 <xref:System.Windows.Controls.StackPanel>   
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)