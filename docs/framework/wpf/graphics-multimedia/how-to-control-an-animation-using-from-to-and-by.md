---
title: Практическое руководство. Управление анимацией с помощью From, To и By
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
ms.openlocfilehash: 812217a2905671567271687b974a435dd85cea47
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930090"
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Практическое руководство. Управление анимацией с помощью From, To и By
"From/To/By" или "Basic Animation" создает переход между двумя целевыми значениями (см. [Общие сведения об анимации](animation-overview.md) для введения в различные типы анимаций). Чтобы задать целевые значения основной анимации, используйте <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>свойства, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> .  В следующей таблице показано <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, как свойства, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> можно использовать вместе или отдельно для определения целевых значений анимации.  
  
|Заданные свойства|Результирующее поведение|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|Анимация выполняется от значения, указанного <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойством, к базовому значению анимируемого свойства или к выходному значению предыдущей анимации в зависимости от настройки предыдущей анимации.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Анимация выполняется от значения, указанного <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойством, к значению, заданному <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойством.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Анимация выполняется от значения, указанного <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойством, к значению, заданному суммой <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойств и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> .|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Анимация выполняется от базового значения анимированного свойства или выходного значения предыдущей анимации к значению, заданному <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойством.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Анимация выполняется от базового значения анимируемого свойства или выходного значения предыдущей анимации до суммы этого значения и значения, заданного <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойством.|  
  
> [!NOTE]
> Не устанавливайте как <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство, так <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> и свойство в одной анимации.  
  
 Чтобы применить другие методы интерполяции или выполнять анимацию между более чем двумя целевыми значениями, используйте анимацию по ключевым кадрам. Дополнительные сведения см. в статье [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md) .  
  
 Сведения о применении нескольких анимаций к одному свойству см. в разделе [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md).  
  
 В приведенном ниже примере показаны различные эффекты настройки <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>свойств <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, и <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> для анимации.  
  
## <a name="example"></a>Пример  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Пример целевых значений анимации From, To и By](https://go.microsoft.com/fwlink/?LinkID=159988)
