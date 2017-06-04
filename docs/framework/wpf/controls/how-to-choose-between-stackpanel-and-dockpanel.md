---
title: "Практическое руководство. Выбор между StackPanel и DockPanel | Microsoft Docs"
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
  - "элементы управления [WPF], DockPanel"
  - "элементы управления [WPF], StackPanel"
  - "DockPanel - элемент управления, сравнение с элементом управления StackPanel"
  - "StackPanel - элемент управления, сравнение с элементом управления DockPanel"
ms.assetid: f9239086-451f-42e6-81f7-ef89ef349742
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Выбор между StackPanel и DockPanel
В этом примере показано, как сделать выбор между использованием <xref:System.Windows.Controls.StackPanel> или <xref:System.Windows.Controls.DockPanel>, если стека расположен в <xref:System.Windows.Controls.Panel>.  
  
## Пример  
 Несмотря на то, что можно использовать и <xref:System.Windows.Controls.DockPanel>, и <xref:System.Windows.Controls.StackPanel> для расположения дочерних элементов, два элемента управления не всегда дают один результат.  Например, порядок, в котором расположены дочерние элементы, может повлиять на размер дочерних элементов в <xref:System.Windows.Controls.DockPanel>, но не в <xref:System.Windows.Controls.StackPanel>.  Это различие возникает из\-за того, что размеры <xref:System.Windows.Controls.StackPanel> зависят от направления стека в <xref:System.Double>.<xref:System.Double.PositiveInfinity>; однако, <xref:System.Windows.Controls.DockPanel> измеряет только доступный размер.  
  
 В следующем примере показано это ключевое различие между <xref:System.Windows.Controls.DockPanel> и <xref:System.Windows.Controls.StackPanel>.  
  
 [!code-cpp[StackPanelOvw4#1](../../../../samples/snippets/cpp/VS_Snippets_Wpf/StackPanelOvw4/CPP/StackPanel_Ovw_Sample4.cpp#1)]
 [!code-csharp[StackPanelOvw4#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelOvw4/CSharp/StackPanel_Ovw_Sample4.cs#1)]
 [!code-vb[StackPanelOvw4#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelOvw4/VisualBasic/StackPanelSamp.vb#1)]
 [!code-xml[StackPanelOvw4#1](../../../../samples/snippets/xaml/VS_Snippets_Wpf/StackPanelOvw4/XAML/default.xaml#1)]  
  
## См. также  
 <xref:System.Windows.Controls.StackPanel>   
 <xref:System.Windows.Controls.DockPanel>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)