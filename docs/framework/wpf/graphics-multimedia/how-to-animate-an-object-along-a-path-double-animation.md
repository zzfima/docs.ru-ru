---
title: Практическое руководство. Анимация объекта вдоль пути (двойная анимация)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (double animation)
- double animation [WPF]
ms.assetid: 5a3c4a99-f303-42ad-a52a-e4794bb1798e
ms.openlocfilehash: 084caac26fd68b6914ec3858652ec44557a0dbd7
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452861"
---
# <a name="how-to-animate-an-object-along-a-path-double-animation"></a>Практическое руководство. Анимация объекта вдоль пути (двойная анимация)
В этом примере показано, как использовать класс <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> для перемещения объекта вдоль пути, определенного <xref:System.Windows.Media.PathGeometry>.  
  
## <a name="example"></a>Пример  
 В следующем примере используются два объекта <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> для перемещения прямоугольника вдоль геометрического пути:  
  
- Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимируется <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform>, применяемого к прямоугольнику. В результате прямоугольник перемещается горизонтально вдоль пути.  
  
- Вторая <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимируется <xref:System.Windows.Media.TranslateTransform.Y%2A> <xref:System.Windows.Media.TranslateTransform>, применяемого к прямоугольнику. В результате прямоугольник перемещается вертикально вдоль пути.  
  
 [!code-xaml[PathAnimationGallery_snippet#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/doubleanimationusingpathexample.xaml#doubleanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/DoubleAnimationUsingPathExample.cs#doubleanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#DoubleAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/DoubleAnimationUsingPathExample.vb#doubleanimationusingpathwholepage)]  
  
 Полный пример см. в разделе [Пример анимации по путям](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 Другой способ перемещения объекта с помощью геометрического пути заключается в использовании объекта <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath>. Пример см. в разделе [анимация объекта вдоль пути (матричная анимация)](how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Практические руководства, посвященные анимации вдоль пути](path-animation-how-to-topics.md)
