---
title: "Практическое руководство. Анимация объекта вдоль пути (двойная анимация)"
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
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a461b741675a18ac1e3544b17a9bbe9a8d18547
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a>Практическое руководство. Анимация объекта вдоль пути (двойная анимация)
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> класса для перемещения объекта вдоль пути, заданного с <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Пример  
 В следующем примере используются два <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> объектов для перемещения прямоугольника вдоль геометрического пути:  
  
-   Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимирует <xref:System.Windows.Media.TranslateTransform.X%2A> из <xref:System.Windows.Media.TranslateTransform> применительно к прямоугольнику. В результате прямоугольник перемещается горизонтально вдоль пути.  
  
-   Второй <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимирует <xref:System.Windows.Media.TranslateTransform.Y%2A> из <xref:System.Windows.Media.TranslateTransform> применительно к прямоугольнику. В результате прямоугольник перемещается вертикально вдоль пути.  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 Полный пример см. в разделе [Пример анимации пути](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 Другой способ перемещения объекта с использованием геометрического пути является использование <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> объекта. Пример см. в разделе [анимация объекта вдоль пути (матрица анимации)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Практические руководства, посвященные анимации по контуру](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
