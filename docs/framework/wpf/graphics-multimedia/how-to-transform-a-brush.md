---
title: "Практическое руководство. Преобразование кисти | Microsoft Docs"
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
  - "кисти, вращение содержимого"
  - "кисти, Transform - свойство"
  - "вращение содержимого Brush"
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Преобразование кисти
Этот пример демонстрирует способ преобразования объектов <xref:System.Windows.Media.Brush> с помощью двух свойств преобразования: <xref:System.Windows.Media.Brush.RelativeTransform%2A> и <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 В следующих примерах <xref:System.Windows.Media.RotateTransform> используется для поворота содержимого <xref:System.Windows.Media.ImageBrush> на 45 градусов.  
  
 На следующем рисунке показана <xref:System.Windows.Media.ImageBrush> без <xref:System.Windows.Media.RotateTransform> с <xref:System.Windows.Media.RotateTransform>, примененным к свойству <xref:System.Windows.Media.Brush.RelativeTransform%2A>, и с <xref:System.Windows.Media.RotateTransform>, примененным к свойству <xref:System.Windows.Media.Brush.Transform%2A>.  
  
 ![Параметры кисти RelativeTransform и Transform](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk\_graphicsmm\_transformandrelativetransform")  
  
## Пример  
 В первом примере <xref:System.Windows.Media.RotateTransform> применяется к свойству <xref:System.Windows.Media.Brush.RelativeTransform%2A> элемента <xref:System.Windows.Media.ImageBrush>.  Свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> объекта <xref:System.Windows.Media.RotateTransform>установлены в значение 0,5, что является относительной координатой центральной точки этого содержимого.  В результате содержимое <xref:System.Windows.Media.ImageBrush> поворачивается относительно своего центра.  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 Во втором примере также применяется <xref:System.Windows.Media.RotateTransform> к <xref:System.Windows.Media.ImageBrush>; однако, в этом примере используется свойство <xref:System.Windows.Media.Brush.Transform%2A> вместо свойства <xref:System.Windows.Media.Brush.RelativeTransform%2A>.  
  
 Чтобы повернуть кисть относительно ее центра, пример присваивает свойствам <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> объекта <xref:System.Windows.Media.RotateTransform> абсолютные координаты.  Поскольку кисть рисует прямоугольник размером 175 на 90 [пикселей](GTMT), центральная точка прямоугольника имеет координаты \(87.5, 45\).  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xml[BrushesIntroduction_snip#ImageBrushTransformExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 Описание принципа действия свойств <xref:System.Windows.Media.Brush.RelativeTransform%2A>и <xref:System.Windows.Media.Brush.Transform%2A> см. в разделе [Общие сведения о преобразованиях объекта Brush](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md).  
  
 Полный код примера см. на веб\-странице [Пример использования кистей](http://go.microsoft.com/fwlink/?LinkID=159973).  Дополнительные сведения о кистях см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).  
  
## См. также  
 [Общие сведения о преобразованиях объекта Brush](../../../../docs/framework/wpf/graphics-multimedia/brush-transformation-overview.md)   
 [Общие сведения о закраске сплошным цветом и градиентом](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)   
 [Общие сведения о классах Transform](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)