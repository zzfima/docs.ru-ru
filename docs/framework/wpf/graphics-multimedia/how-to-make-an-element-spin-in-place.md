---
title: "Практическое руководство. Создание элемента Spin | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "классы, DoubleAnimation"
  - "классы, RotateTransform"
  - "DoubleAnimation - класс"
  - "графика, поворот элементов"
  - "RotateTransform - класс"
  - "поворот элементов"
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание элемента Spin
В этом примере демонстрируется, как создать элемент Spin с помощью <xref:System.Windows.Media.RotateTransform> и <xref:System.Windows.Media.Animation.DoubleAnimation>.  
  
 В следующем примере <xref:System.Windows.Media.RotateTransform> применяется к свойству элемента <xref:System.Windows.UIElement.RenderTransform%2A>.  В примере <xref:System.Windows.Media.Animation.DoubleAnimation> используется, чтобы анимировать <xref:System.Windows.Media.RotateTransform.Angle%2A> для <xref:System.Windows.Media.RotateTransform>.  Чтобы создать элемент Spin, в примере для свойства <xref:System.Windows.UIElement.RenderTransformOrigin%2A> элемента задается точка \(0,5, 0,5\).  
  
## Пример  
 [!code-xml[transformanimations_snip#11](../../../../samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 Полный пример с большим количеством примеров преобразований см. в разделе [Пример двумерных преобразований](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)