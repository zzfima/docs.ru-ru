---
title: "Практическое руководство. Анимация объектов по всему пути (Матричная анимации с накоплением смещения) | Microsoft Docs"
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
  - "накопление смещения"
  - "анимация, объекты вдоль путей (матричная анимации с накоплением смещения)"
  - "матричная анимации с накоплением смещения"
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Практическое руководство. Анимация объектов по всему пути (Матричная анимации с накоплением смещения)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> класс анимация объекта вдоль пути и анимации накапливаются его смещение значения, как она повторяется.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> анимируемого объекта <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform> применяется к кнопке. В результате кнопка перемещается вдоль изогнутого пути.  
  
 Кроме того, в этом примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> свойства `true`, вследствие чего смещение анимированный матрицы накапливается при повторе анимации. Поскольку смещение накапливается, кнопка перемещается дальше по экрану при повторении анимации, а не возвращается в начальную позицию.  
  
 [!code-xml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 Обратите внимание, что, хотя <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> свойство вызывает накопление значений смещения, оно не вызывает накопления значений поворота. Чтобы накопления значений поворота, задайте анимации <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> и <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> свойства `true`.  
  
 Полный пример см. [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028). Пример, показывающий, как анимировать <xref:System.Windows.Media.Matrix> значение вдоль пути без накапливания смещения см. в разделе [анимация объекта вдоль пути (матричная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>См. также  
 [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Разделы руководства, посвященные анимации пути](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)