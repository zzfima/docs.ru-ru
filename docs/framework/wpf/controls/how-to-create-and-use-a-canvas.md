---
title: "Практическое руководство. Создание и использование Canvas | Microsoft Docs"
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
  - "Canvas - элемент управления, создание"
  - "Canvas - элемент управления, использование"
  - "элементы управления, Canvas"
ms.assetid: 420b9487-9a15-477c-9489-a22a4dec7779
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Создание и использование Canvas
В этом примере демонстрируется создание и использование экземпляра <xref:System.Windows.Controls.Canvas>.  
  
## Пример  
 Следующий пример явным образом располагает два элемента <xref:System.Windows.Controls.TextBlock> с помощью методов <xref:System.Windows.Controls.Canvas.SetTop%2A> и <xref:System.Windows.Controls.Canvas.SetLeft%2A> из <xref:System.Windows.Controls.Canvas>.  Пример также присваивает цвет <xref:System.Windows.Controls.Control.Background%2A> `LightSteelBlue` элементу <xref:System.Windows.Controls.Canvas>.  
  
> [!NOTE]
>  При использовании [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для размещения элементов <xref:System.Windows.Controls.TextBlock> следует использовать свойства <xref:System.Windows.Controls.Canvas.Top%2A> и <xref:System.Windows.Controls.Canvas.Left%2A>.  
  
 [!code-csharp[CanvasCode#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CanvasCode/CSharp/Canvas_Code.cs#1)]
 [!code-vb[CanvasCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasCode/VisualBasic/canvas_vb.vb#1)]  
  
## См. также  
 <xref:System.Windows.Controls.Canvas>   
 <xref:System.Windows.Controls.TextBlock>   
 <xref:System.Windows.Controls.Canvas.SetTop%2A>   
 <xref:System.Windows.Controls.Canvas.SetLeft%2A>   
 <xref:System.Windows.Controls.Canvas.Top%2A>   
 <xref:System.Windows.Controls.Canvas.Left%2A>   
 [Общие сведения о панелях](../../../../docs/framework/wpf/controls/panels-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/canvas-how-to-topics.md)