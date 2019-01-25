---
title: Как выполнить Анимация расположения объекта с помощью PointAnimation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], animation
- animation [WPF], PointAnimation
ms.assetid: 42310977-cc90-438a-8a47-0345898e01be
ms.openlocfilehash: e359e712f533c861a694c53848ca0eaeb289eb21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495557"
---
# <a name="how-to-animate-the-position-of-an-object-by-using-pointanimation"></a>Как выполнить Анимация расположения объекта с помощью PointAnimation
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.PointAnimation> класс для анимации объекта вдоль <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Пример  
 В следующем примере эллипс перемещается <xref:System.Windows.Shapes.Path> из одной точки на экране в другой. Пример анимирует положение <xref:System.Windows.Media.EllipseGeometry> с помощью <xref:System.Windows.Media.Animation.PointAnimation> для анимации <xref:System.Windows.Media.EllipseGeometry.Center%2A> свойство.  
  
 [!code-csharp[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snip/CSharp/PointAnimationExample.cs#pointanimationwholepage)]
 [!code-vb[BasicAnimations_snip#PointAnimationWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BasicAnimations_snip/VisualBasic/PointAnimationExample.vb#pointanimationwholepage)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.Animation.PointAnimation>
- <xref:System.Windows.Shapes.Path>
- <xref:System.Windows.Media.EllipseGeometry>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A>
- [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Графика и мультимедиа](../../../../docs/framework/wpf/graphics-multimedia/index.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/graphics-how-to-topics.md)
- [Анимация и расчет времени](https://msdn.microsoft.com/library/7d83765b-d5ae-41b1-b423-80206e1124aa)
- [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
