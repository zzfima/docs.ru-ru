---
title: "Практическое руководство. Сохранение пропорций изображения, используемого в качестве фона | Microsoft Docs"
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
  - "пропорции фоновых рисунков, сохранение"
  - "фоновые изображения, сохранение пропорций"
  - "кисти, сохранение пропорций фоновых рисунков"
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Сохранение пропорций изображения, используемого в качестве фона
Этот пример показывает, как использовать свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> из <xref:System.Windows.Media.ImageBrush>, чтобы сохранить [пропорции](GTMT) изображения.  
  
 По умолчанию при использовании <xref:System.Windows.Media.ImageBrush> для закраски области, его содержимое увеличивается до полного заполнения выходной области.  Если выходная область и изображение имеют различные [пропорции](GTMT), рисунок искажается этим расширением.  
  
 Чтобы заставить <xref:System.Windows.Media.ImageBrush> сохранять пропорции изображения, установите свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> в <xref:System.Windows.Media.Stretch> или <xref:System.Windows.Media.Stretch>.  
  
## Пример  
 Следующий пример использует два объекта <xref:System.Windows.Media.ImageBrush> для рисования двух прямоугольников.  Каждый прямоугольник имеет размер 300 на 150 [пикселей](GTMT) и каждый содержит изображение размером 300 на 300 пикселей.  Свойство <xref:System.Windows.Media.TileBrush.Stretch%2A>первой кисти устанавливается в <xref:System.Windows.Media.Stretch>, и свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> второй кисти устанавливается в <xref:System.Windows.Media.Stretch>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 На следующем рисунке показан результат выполнения первой кисти, который имеет параметр <xref:System.Windows.Media.TileBrush.Stretch%2A> из <xref:System.Windows.Media.Stretch>.  
  
 ![ImageBrush с растяжением Uniform](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.png "graphicsmm\_ImageBrushUniformStretch")  
  
 На следующем рисунке показан результат выполнения второй кисти, который имеет параметр <xref:System.Windows.Media.TileBrush.Stretch%2A> из <xref:System.Windows.Media.Stretch>.  
  
 ![ImageBrush с растяжением UniformToFill](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.png "graphicsmm\_ImageBrushUniformToFillStretch")  
  
 Обратите внимание, что свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> ведет себя идентично для других объектов <xref:System.Windows.Media.TileBrush>, т. е. для <xref:System.Windows.Media.DrawingBrush> и <xref:System.Windows.Media.VisualBrush>.  Дополнительные сведения о <xref:System.Windows.Media.ImageBrush> и других объектах <xref:System.Windows.Media.TileBrush>, см. в разделе [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Также обратите внимание, что, хотя свойство <xref:System.Windows.Media.TileBrush.Stretch%2A> указывает, как содержимое <xref:System.Windows.Media.TileBrush> увеличивается для заполнения его выходной области, оно фактически указывает, как содержимое <xref:System.Windows.Media.TileBrush> увеличивается для заполнения его базового фрагмента.  Дополнительные сведения см. в разделе <xref:System.Windows.Media.TileBrush>.  
  
 Этот пример кода является частью более крупного примера для класса <xref:System.Windows.Media.ImageBrush>.  Полный код примера см. в разделе [Пример ImageBrush](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## См. также  
 <xref:System.Windows.Media.TileBrush>   
 [Рисование с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)