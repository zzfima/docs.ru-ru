---
title: "Практическое руководство. Анимация объектов по всему пути (Матричная анимации с накоплением смещения)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- offset accumulation [WPF]
- animation [WPF], objects along paths (matrix animation with offset accumulation)
- matrix animation with offset accumulation [WPF]
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5259e930060a8ac6118d232f08d02193a6a1b300
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation-with-offset-accumulation"></a>Практическое руководство. Анимация объектов по всему пути (Матричная анимации с накоплением смещения)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> класса, чтобы анимация объекта вдоль пути анимации накапливаются его смещение значения при повторе его.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> анимируемый объект <xref:System.Windows.Media.MatrixTransform.Matrix%2A> свойство <xref:System.Windows.Media.MatrixTransform> применяется к кнопке. В результате кнопка перемещается вдоль изогнутого пути.  
  
 Кроме того, в этом примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> свойства `true`, чего смещение анимированной матрицы накапливаться при повторе анимации. Поскольку смещение накапливается, при повторении анимации кнопка перемещается все дальше по экрану, а не возвращается в начальную позицию.  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 Обратите внимание, что, несмотря на то что <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> свойство вызывает накопление значений смещения, оно не вызывает накопления значений поворота. Чтобы значения вращения накапливаться, задайте анимации <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> и <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> свойства `true`.  
  
 Полный пример см. в разделе [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028). Пример, показывающий, как анимировать <xref:System.Windows.Media.Matrix> значение пути без накапливания смещения см. в разделе [анимация объекта вдоль пути (матрица анимации)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Практические руководства, посвященные анимации по контуру](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
