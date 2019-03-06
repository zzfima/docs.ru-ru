---
title: Практическое руководство. Анимация расположения объекта с помощью PointAnimation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: 04dbcfdb64525e6231ecf33c8ac5ecf2a2d2cb7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57357948"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>Практическое руководство. Анимация расположения объекта с помощью PointAnimation
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.PointAnimation> класс для анимации объекта вдоль <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Пример  
 В следующем примере эллипс перемещается <xref:System.Windows.Shapes.Path> из одной точки на экране в другой. Пример анимирует положение <xref:System.Windows.Media.EllipseGeometry> с помощью <xref:System.Windows.Media.Animation.PointAnimation> для анимации <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Графика и мультимедиа](index.md)
- [Разделы руководства, посвященные графики](graphics-how-to-topics.md)
- [Анимации и практические руководства](animation-and-timing-how-to-topics.md)
