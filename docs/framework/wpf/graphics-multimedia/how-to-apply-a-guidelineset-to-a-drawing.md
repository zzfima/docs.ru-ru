---
title: "Практическое руководство. Применение GuidelineSet к рисованию | Microsoft Docs"
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
  - "графика [WPF], GuidelineSet - свойство"
  - "GuidelineSet - свойство, применение к рисункам"
ms.assetid: 45f3e0b4-8820-45a7-b865-b8ea5b17b0c8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Практическое руководство. Применение GuidelineSet к рисованию
В этом примере показано, как применить <xref:System.Windows.Media.GuidelineSet> к объекту <xref:System.Windows.Media.DrawingGroup>.  
  
 Класс <xref:System.Windows.Media.DrawingGroup> является единственным типом <xref:System.Windows.Media.Drawing>, который имеет свойство <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>.  Чтобы применить <xref:System.Windows.Media.GuidelineSet> к другому типу <xref:System.Windows.Media.Drawing>, добавьте его к <xref:System.Windows.Media.DrawingGroup> и затем примените <xref:System.Windows.Media.GuidelineSet> к <xref:System.Windows.Media.DrawingGroup>.  
  
## Пример  
 В следующем примере создаются два объекта <xref:System.Windows.Media.DrawingGroup>, которые являются почти идентичными, с одной лишь разницей: второй объект <xref:System.Windows.Media.DrawingGroup> имеет <xref:System.Windows.Media.GuidelineSet>, который отсутствует у первого.  
  
 На следующем рисунке представлен результат выполнения данного примера.  Из\-за того, что различия в отрисовке двух объектов <xref:System.Windows.Media.DrawingGroup> не очень заметны, части рисунков увеличены.  
  
 ![DrawingGroup с и без GuidelineSet](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawinggroup-guidelineset.png "graphicsmm\_drawinggroup\_guidelineset")  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupGuidelineSetExample.cs#graphicsmmdrawinggroupguidelinesetexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMDrawingGroupGuidelineSetExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupGuidelineSetExample.xaml#graphicsmmdrawinggroupguidelinesetexamplewholepage)]  
  
## См. также  
 <xref:System.Windows.Media.DrawingGroup>   
 <xref:System.Windows.Media.GuidelineSet>   
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)