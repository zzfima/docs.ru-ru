---
title: Практическое руководство. Анимация объекта вдоль пути (точечная анимация)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (point animation)
- point animation [WPF]
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
ms.openlocfilehash: eff0c24a9369ffaa0cfca1cc46af4eff39f58a38
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452900"
---
# <a name="how-to-animate-an-object-along-a-path-point-animation"></a>Практическое руководство. Анимация объекта вдоль пути (точечная анимация)
В этом примере показано, как использовать объект <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимации <xref:System.Windows.Point> вдоль криволинейного пути.  
  
## <a name="example"></a>Пример  
 В следующем примере перемещается <xref:System.Windows.Media.EllipseGeometry> вдоль пути, определенного <xref:System.Windows.Media.PathGeometry>. Свойство <xref:System.Windows.Media.EllipseGeometry.Center%2A>, представляющее собой геометрию эллипса, которое принимает значение <xref:System.Windows.Point>, задает его расположение. чтобы переместить фигуру эллипса, необходимо анимировать ее свойство <xref:System.Windows.Media.EllipseGeometry.Center%2A>. В примере используется <xref:System.Windows.Media.Animation.PointAnimationUsingPath> для анимации свойства <xref:System.Windows.Media.EllipseGeometry.Center%2A> объекта <xref:System.Windows.Media.EllipseGeometry>.  
  
 [!code-xaml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Полный пример см. в разделе [Пример анимации по путям](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).  
  
 Версия кода предыдущего примера использовала <xref:System.Windows.Media.Animation.Storyboard> для анимации <xref:System.Windows.Media.EllipseGeometry>, несмотря на то, что применена только одна анимация. <xref:System.Windows.Media.Animation.Storyboard> часто является самым простым способом применения нескольких анимаций, так как эти анимации могут управляться одним и тем же <xref:System.Windows.Media.Animation.Storyboard>. Однако более простым способом применения одной анимации к свойству при использовании кода является использование метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A>. Пример см. в разделе [Анимация свойства без использования раскадровки](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>См. также раздел

- [Пример анимации вдоль пути](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Практические руководства, посвященные анимации вдоль пути](path-animation-how-to-topics.md)
