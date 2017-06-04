---
title: "Практическое руководство. Создание экземпляра класса DockPanel | Microsoft Docs"
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
  - "элементы управления, DockPanel"
  - "DockPanel - элемент управления, создание"
ms.assetid: 9194f663-e279-4f1a-86d7-125a57d05c6f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Создание экземпляра класса DockPanel
## Пример  
 В следующем примере с помощью кода создается и используется экземпляр класса <xref:System.Windows.Controls.DockPanel>.  В примере показано, как разделить пространство путем создания пяти элементов класса <xref:System.Windows.Shapes.Rectangle> и размещения \(закрепления\) их в родительском классе <xref:System.Windows.Controls.DockPanel>.  Если сохранить параметр по умолчанию, конечный прямоугольник заполнит все оставшиеся незанятое пространство.  
  
 [!code-csharp[DockPanelCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DockPanelCode/CSharp/DockPanel_Code.cs#1)]
 [!code-vb[DockPanelCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DockPanelCode/VisualBasic/dockpanel_vb.vb#1)]  
  
## См. также  
 <xref:System.Windows.Controls.DockPanel>   
 <xref:System.Windows.Controls.Dock>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)