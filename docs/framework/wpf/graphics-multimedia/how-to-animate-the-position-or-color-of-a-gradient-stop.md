---
title: Практическое руководство. Анимация положения или цвета ограничения градиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452848"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Практическое руководство. Анимация положения или цвета ограничения градиента
В этом примере показано, как анимировать <xref:System.Windows.Media.GradientStop.Color%2A> и <xref:System.Windows.Media.GradientStop.Offset%2A> объектов <xref:System.Windows.Media.GradientStop>.  
  
## <a name="example"></a>Пример  
 В следующем примере анимируется три остановки градиента внутри <xref:System.Windows.Media.LinearGradientBrush>. В этом примере используется три анимации, каждая из которых анимирует другую точку градиента:  
  
- Первая анимация, <xref:System.Windows.Media.Animation.DoubleAnimation>, выполняет анимацию первого ограничителя градиента <xref:System.Windows.Media.GradientStop.Offset%2A> с 0,0 до 1,0, а затем обратно в 0,0. В результате первый цвет градиента смещается с левой стороны к правой части прямоугольника, а затем обратно на левую сторону.  
  
- Вторая анимация, <xref:System.Windows.Media.Animation.ColorAnimation>, анимирует <xref:System.Windows.Media.GradientStop.Color%2A> второй ограничитель градиента от <xref:System.Windows.Media.Colors.Purple%2A> до <xref:System.Windows.Media.Colors.Yellow%2A>, а затем обратно в <xref:System.Windows.Media.Colors.Purple%2A>. В результате средний цвет в градиенте меняется с пурпурного на желтый и обратно на сиреневый.  
  
- Третья анимация, другая <xref:System.Windows.Media.Animation.ColorAnimation>, анимирует непрозрачность третьего <xref:System.Windows.Media.GradientStop.Color%2A> ограничителя градиента на-1, а затем обратно. В результате третий цвет в градиенте плавно исчезает, а затем снова становится непрозрачным.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Несмотря на то, что в этом примере используется <xref:System.Windows.Media.LinearGradientBrush>, процесс анимации <xref:System.Windows.Media.GradientStop> объектов внутри <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Дополнительные примеры см. в [образце кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.GradientStop>
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о раскадровке](storyboards-overview.md)
