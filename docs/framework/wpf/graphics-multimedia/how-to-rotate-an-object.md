---
title: "Практическое руководство. Вращение объекта | Microsoft Docs"
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
  - "графика, поворот объектов"
  - "поворот объектов"
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Вращение объекта
В этом примере демонстрируется поворот объекта.  В примере сначала создается <xref:System.Windows.Media.RotateTransform>, а затем указывается его <xref:System.Windows.Media.RotateTransform.Angle%2A> в градусах.  
  
 В следующем примере объект <xref:System.Windows.Shapes.Polyline> поворачивается на 45 градусов относительно его верхнего левого угла.  
  
## Пример  
 [!code-xml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> <xref:System.Windows.Media.RotateTransform> указывают координаты точки, вокруг которой будет повернут объект.  Эта центральная точка выражается в пространстве координат преобразуемого элемента.  По умолчанию поворот применяется к точке \(0,0\), которая является левым верхним углом преобразуемого объекта.  
  
 В следующем примере осуществляется поворот объекта <xref:System.Windows.Shapes.Polyline> по часовой стрелке на 45 градусов относительно точки \(25,50\).  
  
 [!code-xml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 На следующем рисунке показаны результаты применения <xref:System.Windows.Media.Transform> к двум объектам.  
  
 ![Вращения на 45 градусов с различными точками центра](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.png "wcpsdk\_graphicsmm\_rotatetransform45degrees")  
Два объекта, повернутых на 45 градусов относительно разных центров поворота  
  
 <xref:System.Windows.Shapes.Polyline> в предыдущих примерах является <xref:System.Windows.UIElement>.  При применении <xref:System.Windows.Media.Transform> к свойству <xref:System.Windows.UIElement.RenderTransform%2A> <xref:System.Windows.UIElement> можно использовать свойство <xref:System.Windows.UIElement.RenderTransformOrigin%2A> для указания источника каждой <xref:System.Windows.Media.Transform>, применяемой к элементу.  Поскольку свойство <xref:System.Windows.UIElement.RenderTransformOrigin%2A> использует относительные координаты, можно применить преобразование относительно центра элемента даже в том случае, если не известен его размер.  Дополнительные сведения и примеры см. в разделе [Задание источника преобразования с помощью относительных значений](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Полный пример см. на веб\-странице [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## См. также  
 <xref:System.Windows.Media.Transform>   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)