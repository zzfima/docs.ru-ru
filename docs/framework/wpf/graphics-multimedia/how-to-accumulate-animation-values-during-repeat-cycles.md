---
title: Как выполнить Накапливание значений анимации в повторяющихся циклах
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 6e98b7eefd0c30e728b60926096c0f082bc079ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587285"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Как выполнить Накапливание значений анимации в повторяющихся циклах
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойство к накоплению значений анимации в повторяющихся циклах.  
  
## <a name="example"></a>Пример  
 Используйте <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойство к накоплению значений анимации в повторяющихся циклах. Например, если выбрать Повтор 9 раз анимации (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = «9 x») и задать свойство для анимации в диапазоне от 10 до 15 (From = 10 = 15), свойство анимируется от 10 до 15 во время первого цикла, от 15 до 20 во время второго цикла , от 20 до 25 во время третьего цикла и т. д. Таким образом каждый цикл анимации использует конечное значение анимации из предыдущего цикла анимации в качестве базового.  
  
 Можно использовать `IsCumulative` свойство с большинством базовых анимаций и большинство анимации ключевого кадра. Дополнительные сведения см. в разделе [Общие сведения об анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) и [сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 В следующем примере показано такое поведение при анимации ширины четыре прямоугольника. Пример:  
  
-   Анимирует первый прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimation> и задает <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойства `true`.  
  
-   Анимирует второй прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimation> и задает <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> присваивается значение по умолчанию `false`.  
  
-   Анимирует третий прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> и задает <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> свойства `true`.  
  
-   Анимирует последний прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> и задает <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> свойства `false`.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>См. также
- [Добавление выходного значения анимации к начальному значению анимации](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)
- [Повторение анимации](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)
- [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
