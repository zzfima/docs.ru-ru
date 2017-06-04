---
title: "Практическое руководство. Поворот объекта с использованием геометрического пути | Microsoft Docs"
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
  - "геометрические пути, поворот объектов по"
  - "поворот объекта с помощью геометрических путей"
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Поворот объекта с использованием геометрического пути
В этом примере демонстрируется поворот (вращение) объекта вдоль геометрического пути, который определяется <xref:System.Windows.Media.PathGeometry> объекта.  
  
## <a name="example"></a>Пример  
 В следующем примере используется три <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> объектов для перемещения прямоугольника вдоль геометрического пути.  
  
-   Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимирует <xref:System.Windows.Media.RotateTransform> , применительно к прямоугольнику. Анимация формирует значения угла. Он заставляет прямоугольник поворот (вращение) по контурам пути.  
  
-   Анимация двух объектов <xref:System.Windows.Media.TranslateTransform.X%2A> и <xref:System.Windows.Media.TranslateTransform.Y%2A> значения <xref:System.Windows.Media.TranslateTransform> , применительно к прямоугольнику. Они заставляют прямоугольник перемещения по горизонтали и вертикали вдоль пути.  
  
 [!code-xml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 Поворот объекта с использованием геометрического пути другим способом является использование <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> и задайте его <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойства `true`. Дополнительные сведения и пример см. в разделе [поворот объекта с использованием геометрического пути (матрица анимации)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).  
  
 Полный пример см. [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
## <a name="see-also"></a>См. также  
 [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Пример анимации пути перемещения](http://go.microsoft.com/fwlink/?LinkID=160028)   
 [Разделы руководства, посвященные анимации пути](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)