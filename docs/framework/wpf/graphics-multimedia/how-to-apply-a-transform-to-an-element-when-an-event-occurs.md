---
title: "Практическое руководство. Применение преобразования к элементу при возникновении события | Microsoft Docs"
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
  - "графика, преобразования в качестве реакции на события"
  - "LayoutTransform - свойство"
  - "свойства, LayoutTransform"
  - "свойства, RenderTransform"
  - "RenderTransform - свойство"
  - "преобразования в качестве реакции на события"
ms.assetid: 71e4327e-ca57-444c-a3cf-09fb381491a0
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Применение преобразования к элементу при возникновении события
В этом примере демонстрируется применение <xref:System.Windows.Media.ScaleTransform> при возникновении события.  Показанная здесь концепция совпадает с той, которая используется для применения других типов преобразований.  Дополнительные сведения о доступных типах преобразований см. в описании класса <xref:System.Windows.Media.Transform> или в разделе [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md).  
  
 Существует два способа применения преобразования к элементу.  
  
-   Если *не* требуется, чтобы преобразование оказывало влияние на макет, то следует использовать свойство <xref:System.Windows.UIElement.RenderTransform%2A> элемента.  
  
-   Если необходимо, чтобы преобразование оказывало влияние на макет, то следует использовать свойство <xref:System.Windows.FrameworkElement.LayoutTransform%2A> элемента.  
  
 В следующем примере <xref:System.Windows.Media.ScaleTransform> применяется к свойству <xref:System.Windows.UIElement.RenderTransform%2A> кнопки.  При наведении указателя мыши на кнопку свойства <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> у <xref:System.Windows.Media.ScaleTransform> устанавливаются в значение `2`, что приводит к увеличению кнопки.  При перемещении указателя мыши с кнопки свойства <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> устанавливаются в значение `1`, что восстанавливает исходный размер кнопки.  
  
## Пример  
 [!code-xml[ButtonTransform#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml#1)]  
  
 [!code-csharp[ButtonTransform#1cb](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ButtonTransform/CSharp/ButtonTransformExample.xaml.cs#1cb)]
 [!code-vb[ButtonTransform#1cb](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ButtonTransform/VisualBasic/ButtonTransformExample.xaml.vb#1cb)]  
  
## См. также  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.ScaleTransform>   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)   
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)