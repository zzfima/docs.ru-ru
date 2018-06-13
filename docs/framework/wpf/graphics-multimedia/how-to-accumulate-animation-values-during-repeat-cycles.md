---
title: Практическое руководство. Накапливание значений анимации в повторяющихся циклах
ms.date: 03/30/2017
helpviewer_keywords:
- accumulating animation values across repeating cycles [WPF]
- animation [WPF], accumulating values across repeating cycles
ms.assetid: 548df369-c7cc-4dab-b569-08b95ced2e7e
ms.openlocfilehash: 7b954a388549f1bc6f3fa6ec1bcb2df61cc4e045
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557671"
---
# <a name="how-to-accumulate-animation-values-during-repeat-cycles"></a>Практическое руководство. Накапливание значений анимации в повторяющихся циклах
В этом примере показано, как использовать <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойства для накапливания значений анимации в повторяющихся циклах.  
  
## <a name="example"></a>Пример  
 Используйте <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойство для накапливания базовых значений анимации в повторяющихся циклах. Например, если значение анимации 9 раз (<xref:System.Windows.Media.Animation.Timeline.RepeatBehavior%2A> = «9 x») и задать для свойства между 10 и 15 (From = 10 = 15), свойство выполняет анимацию от 10 до 15 во время первого цикла, от 15 до 20 во время второго цикла , от 20 до 25 во время третьего цикла и т. д. Таким образом каждый цикл анимации использует конечное значение анимации из предыдущего цикла анимации в качестве базового значения.  
  
 Можно использовать `IsCumulative` свойство с большинством базовых анимаций и большинство анимации ключевого кадра. Дополнительные сведения см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) и [кадрами ключ](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 В следующем примере показано такое поведение при анимации ширины четырех прямоугольников. Пример:  
  
-   Анимируется первый прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimation> и задает <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойства `true`.  
  
-   Анимируется второй прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimation> и задает <xref:System.Windows.Media.Animation.DoubleAnimation.IsCumulative%2A> свойство в значение по умолчанию `false`.  
  
-   Анимирует третий прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> и задает <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> свойства `true`.  
  
-   Анимирует последний прямоугольник с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> и задает <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.IsCumulative%2A> свойства `false`.  
  
 [!code-xaml[timingbehaviors_snip#IsCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/IsCumulativeExample.xaml#iscumulativewholepage)]  
  
## <a name="see-also"></a>См. также  
 [Добавление выходного значения анимации к начальному значению анимации](../../../../docs/framework/wpf/graphics-multimedia/how-to-add-an-animation-output-value-to-an-animation-starting-value.md)  
 [Повторение анимации](../../../../docs/framework/wpf/graphics-multimedia/how-to-repeat-an-animation.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Разделы практического руководства](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-how-to-topics.md)
