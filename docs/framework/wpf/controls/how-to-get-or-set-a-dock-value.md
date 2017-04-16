---
title: "Практическое руководство. Получение или задание значения Dock | Microsoft Docs"
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
  - "Dock - значения, получение"
  - "Dock - значения, параметр"
ms.assetid: fcf4ab8a-c7cd-4835-8d04-de1c999ab4a8
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Получение или задание значения Dock
В следующем примере показано, как присвоить значение <xref:System.Windows.Controls.Dock> для объекта.  В примере используются методы <xref:System.Windows.Controls.DockPanel.GetDock%2A> и <xref:System.Windows.Controls.DockPanel.SetDock%2A> элемента управления <xref:System.Windows.Controls.DockPanel>.  
  
## Пример  
 В примере создается экземпляр элемента <xref:System.Windows.Controls.TextBlock>, `txt1`, и ему присваивается значение <xref:System.Windows.Controls.Dock>, равное `Top`, с помощью метода <xref:System.Windows.Controls.DockPanel.SetDock%2A> элемента управления <xref:System.Windows.Controls.DockPanel>.  Затем он устанавливает значение свойства <xref:System.Windows.Controls.Dock> в <xref:System.Windows.Controls.TextBlock.Text%2A> элемента <xref:System.Windows.Controls.TextBlock> с помощью метода <xref:System.Windows.Controls.DockPanel.GetDock%2A>.  Наконец, в примере добавляется элемент <xref:System.Windows.Controls.TextBlock> родительскому <xref:System.Windows.Controls.DockPanel>, `dp1`.  
  
 [!code-csharp[DockPanelSetDock#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelSetDock/CSharp/DockPanel_SetDock.cs#1)]
 [!code-vb[DockPanelSetDock#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelSetDock/VisualBasic/DockPanel_SetDock.vb#1)]  
  
## См. также  
 <xref:System.Windows.Controls.DockPanel>   
 <xref:System.Windows.Controls.DockPanel.GetDock%2A>   
 <xref:System.Windows.Controls.DockPanel.SetDock%2A>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)