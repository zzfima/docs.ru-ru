---
title: "Практическое руководство. Анимация объекта вдоль пути (двойная анимация) | Microsoft Docs"
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
  - "анимация, объекты вдоль путей (двойная анимация)"
  - "двойная анимация"
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Анимация объекта вдоль пути (двойная анимация)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> класса для перемещения объекта вдоль пути, определенного <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Пример  
 В следующем примере используются два <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> объектов для перемещения прямоугольника вдоль геометрического пути:  
  
-   Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимирует <xref:System.Windows.Media.TranslateTransform.X%2A> из <xref:System.Windows.Media.TranslateTransform> применительно к прямоугольнику. Он заставляет прямоугольник перемещаться горизонтально вдоль пути.  
  
-   Второй <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимирует <xref:System.Windows.Media.TranslateTransform.Y%2A> из <xref:System.Windows.Media.TranslateTransform> применительно к прямоугольнику. Он заставляет прямоугольник перемещаться вертикально вдоль пути.  
  
 [!code-xml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 Полный пример см. [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Другой способ перемещения объекта с использованием геометрического пути является использование <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> объекта. Например, в разделе [анимация объекта вдоль пути (матричная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>См. также  
 [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Разделы руководства, посвященные анимации пути](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)