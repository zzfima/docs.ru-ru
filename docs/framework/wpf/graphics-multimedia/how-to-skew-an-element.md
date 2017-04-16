---
title: "Практическое руководство. Отклонение элемента | Microsoft Docs"
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
  - "классы, SkewTransform"
  - "графика, наклон элементов"
  - "наклон элементов"
  - "SkewTransform - класс"
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Отклонение элемента
В этом примере показано использование <xref:System.Windows.Media.SkewTransform> для наклона элемента.  [Наклон](GTMT), также называемый сдвигом, является преобразованием, которое растягивает пространство координат неравномерно.  Одним из примеров использования <xref:System.Windows.Media.SkewTransform> является имитация глубины [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] в объектах [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)].  
  
 Свойства <xref:System.Windows.Media.SkewTransform.CenterX%2A> и <xref:System.Windows.Media.SkewTransform.CenterY%2A> используются для указания точки центра <xref:System.Windows.Media.SkewTransform>.  
  
 Свойства <xref:System.Windows.Media.SkewTransform.AngleX%2A> и <xref:System.Windows.Media.SkewTransform.AngleY%2A> используются для указания угла наклона по осям x и y и для наклона текущей системы координат вместе с этими осями.  
  
 Чтобы спрогнозировать результат наклона, рассмотрите значения наклонов <xref:System.Windows.Media.SkewTransform.AngleX%2A> по оси x относительно исходной системы координат.  Таким образом, при задании для <xref:System.Windows.Media.SkewTransform.AngleX%2A> значения 30 ось y поворачивается на 30 градусов через начало координат, и значения наклоняются по оси x на 30 градусов от этого начала координат.  Аналогично, при задании для <xref:System.Windows.Media.SkewTransform.AngleY%2A> значения 30 выполняется наклон фигуры по оси y на 30 градусов от начала координат.  Обратите внимание, что это не тоже самое, что перенос \(перемещение\) системы координат на 30 градусов по оси x и y.  
  
 В следующем примере применяется горизонтальный наклон в 45 градусов <xref:System.Windows.Shapes.Rectangle> от точки центра \(0,0\).  
  
## Пример  
 [!code-xml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 В следующем примере применяется горизонтальный наклон в 45 градусов <xref:System.Windows.Shapes.Rectangle> от точки с координатами \(25,25\).  
  
 [!code-xml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 В следующем примере применяется вертикальный наклон в 45 градусов <xref:System.Windows.Shapes.Rectangle> от точки центра с координатами \(25,25\).  
  
 [!code-xml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 На следующем рисунке показаны разные наклоны, использованные в этом примере.  
  
 ![Примеры SkewTransform](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.png "img\_wcpsdk\_graphicsmm\_skewtransformexample")  
Иллюстрированные три примера SkewTransform  
  
 Полный пример см. на веб\-странице [2\-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).  
  
## См. также  
 <xref:System.Windows.Media.Transform>   
 <xref:System.Windows.Media.SkewTransform>   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)   
 [Практические руководства](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)