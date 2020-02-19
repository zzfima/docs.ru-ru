---
title: Практическое руководство. Управление анимацией с помощью свойств From, To, и By
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: b06df97dc57c58a01f30be2d70bfeebf104521ad
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451789"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Практическое руководство. Управление анимацией с помощью свойств From, To, и By
"From/To/By" или "Basic Animation" создает переход между двумя целевыми значениями (см. [Общие сведения об анимации](animation-overview.md) для введения в различные типы анимаций). Чтобы задать целевые значения основной анимации, используйте свойства <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  В следующей таблице показано, как свойства <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> можно использовать вместе или отдельно для определения целевых значений анимации.  
  
|Заданные свойства|Результаты выполнения операции|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|Анимация выполняется от значения, указанного свойством <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, к базовому значению анимируемого свойства или к выходному значению предыдущей анимации в зависимости от настройки предыдущей анимации.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Анимация выполняется от значения, указанного свойством <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, к значению, заданному свойством <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Анимация выполняется от значения, указанного свойством <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, к значению, заданному суммой свойств <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Анимация выполняется от базового значения анимированного свойства или выходного значения предыдущей анимации к значению, заданному свойством <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Анимация выполняется от базового значения анимируемого свойства или выходного значения предыдущей анимации до суммы этого значения и значения, заданного свойством <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.|  
  
> [!NOTE]
> Не устанавливайте как свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, так и свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> в одной и той же анимации.  
  
 Чтобы применить другие методы интерполяции или выполнять анимацию между более чем двумя целевыми значениями, используйте анимацию по ключевым кадрам. Дополнительные сведения см. в статье [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md) .  
  
 Сведения о применении нескольких анимаций к одному свойству см. в разделе [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md).  
  
 В приведенном ниже примере показаны различные эффекты настройки свойств <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>и <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> анимации.  
  
## <a name="example"></a>Пример  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Пример целевых значений анимации From, To, By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
