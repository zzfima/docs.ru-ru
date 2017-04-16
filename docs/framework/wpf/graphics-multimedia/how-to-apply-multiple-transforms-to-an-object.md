---
title: "Практическое руководство. Применение нескольких преобразований к объекту | Microsoft Docs"
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
  - "графика, группировка объектов Transform"
  - "группировка объектов Transform"
  - "Transform - объекты, группирование"
  - "TransformGroup"
ms.assetid: 98cd1921-12bc-4bf5-8193-529228fb7402
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Применение нескольких преобразований к объекту
В данном примере показано, как использовать объект <xref:System.Windows.Media.TransformGroup> для группировки двух или более объектов <xref:System.Windows.Media.Transform> в один составной объект <xref:System.Windows.Media.Transform>.  
  
## Пример  
 В следующем примере объект <xref:System.Windows.Media.TransformGroup> используется для выполнения преобразований <xref:System.Windows.Media.ScaleTransform> и <xref:System.Windows.Media.RotateTransform> к объекту <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[Transforms_snip#MultipleTransformExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/MultipleTransformExample.xaml#multipletransformexamplewholepage)]  
  
 [!code-csharp[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/MultipleTransformsExample.cs#multipletransformscodeexamplewholepage)]
 [!code-vb[Transforms_Procedural_snip#MultipleTransformsCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/MultipleTransformsExample.vb#multipletransformscodeexamplewholepage)]  
  
## См. также  
 <xref:System.Windows.UIElement.RenderTransform%2A>   
 <xref:System.Windows.Media.TransformGroup>   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252)