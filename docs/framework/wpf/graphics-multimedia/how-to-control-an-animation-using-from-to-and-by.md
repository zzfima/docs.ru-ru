---
title: "Практическое руководство. Управление анимацией с помощью свойств From, To, и By"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], From/to/by
- basic animation [WPF]
- animation [WPF], basic animation
- From/to/by animation
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 17f87c8bcf09022aa389df779e29f5e5affabc20
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-an-animation-using-from-to-and-by"></a>Практическое руководство. Управление анимацией с помощью свойств From, To, и By
«Из/в/By» или «базовая анимация» создает переход между двумя целевыми значениями (см. [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) основные сведения о различных типов анимации). Чтобы задать целевые значения основной анимации, используйте его <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства.  В следующей таблице представлены как <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства может быть использовано вместе или отдельно, чтобы определить анимации целевого значения.  
  
|Заданные свойства|Результирующее поведение|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|Анимация продвигается от значения, указанного в <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> выходного значения, в зависимости от настройки предыдущей анимации к базовому значению анимируемого свойства или к предыдущей анимации свойства.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.|Анимация продвигается от значения, указанного в <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство для значения, указанного в <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.|Анимация продвигается от значения, указанного в <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство значение, указанное на сумму <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Анимация продвигается от базовому значению анимируемого свойства или значение для значения, указанного в выходных данных предыдущей анимации <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Анимация продвигается от к базовому значению анимируемого свойства или предыдущей анимации выходного значения этого значения и значения, указанного в сумме <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойство.|  
  
> [!NOTE]
>  Не задавайте одновременно <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства в той же анимации.  
  
 Чтобы применить другие методы интерполяции или выполнять анимацию между более чем двумя целевыми значениями, используйте анимацию по ключевым кадрам. В разделе [кадрами ключ](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) для получения дополнительной информации.  
  
 Сведения о применении нескольких анимаций к одному свойству см. в разделе [кадрами ключ](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 В приведенном ниже примере показаны разные влияния установки <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, и <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойства анимации.  
  
## <a name="example"></a>Пример  
 [!code-xaml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Пример целевых значений анимации From, To и By](http://go.microsoft.com/fwlink/?LinkID=159988)
