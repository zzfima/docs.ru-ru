---
title: "Практическое руководство. Масштабирование элемента | Microsoft Docs"
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
  - "классы, ScaleTransform"
  - "графика, элементы масштабирования"
  - "ScaleTransform - класс"
  - "масштабирование, элементы"
ms.assetid: 18158d94-bbe7-4f6a-814e-84d27fa748bf
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Масштабирование элемента
В этом примере показано использование <xref:System.Windows.Media.ScaleTransform> для масштабирования элемента.  
  
 Используйте свойства <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> и <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> для изменения размеров элемента с определенным коэффициентом.  Например, значение 1,5 для <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> увеличивает элемент на 150 процентов от его исходной ширины.  Значение 0,5 для <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> сжимает высоту элемента на 50 процентов.  
  
 Используйте свойства <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и <xref:System.Windows.Media.ScaleTransform.CenterY%2A> для указания точки, которая будет являться центром операции масштабирования.  По умолчанию <xref:System.Windows.Media.ScaleTransform> центрируется в точке \(0,0\), которая соответствует верхнему левому углу прямоугольника.  Это приводит к перемещению элемента, а также делает его размер больше, поскольку при применении <xref:System.Windows.Media.Transform> изменяются координаты места, в котором находится объект.  
  
 В следующем примере используется <xref:System.Windows.Media.ScaleTransform>, чтобы удвоить размер "50 на 50" для <xref:System.Windows.Shapes.Rectangle>.  <xref:System.Windows.Media.ScaleTransform> имеет значение 0 \(по умолчанию\) для <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и <xref:System.Windows.Media.ScaleTransform.CenterY%2A>.  
  
## Пример  
 [!code-xml[transformsSample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#21)]  
  
 Обычно <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и <xref:System.Windows.Media.ScaleTransform.CenterY%2A> устанавливаются от центра масштабируемого объекта: \(<xref:System.Windows.FrameworkElement.Width%2A>\/2, <xref:System.Windows.FrameworkElement.Height%2A>\/2\).  
  
 В следующем примере показан другой <xref:System.Windows.Shapes.Rectangle>, который удваивается в размере. Однако <xref:System.Windows.Media.ScaleTransform> имеет значение 25 для <xref:System.Windows.Media.ScaleTransform.CenterX%2A> и <xref:System.Windows.Media.ScaleTransform.CenterY%2A>, что соответствует центру прямоугольника.  
  
 [!code-xml[transformsSample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/ScaleTransformExample.xaml#22)]  
  
 На следующем рисунке показана разница между двумя операциями <xref:System.Windows.Media.ScaleTransform>.  Пунктирная линия показывает размер и положение прямоугольника до масштабирования.  
  
 ![Масштабирование на 2 с различными точками центра](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-scalecenter.png "wcpsdk\_graphicsmm\_scalecenter")  
Две операции ScaleTransform с идентичными значениями ScaleX и ScaleY, но различными центрами  
  
 Полный пример см. на веб\-странице [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## См. также  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.ScaleTransform>   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)