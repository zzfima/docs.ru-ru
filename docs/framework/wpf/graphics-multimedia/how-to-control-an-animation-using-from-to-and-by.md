---
title: "Практическое руководство. Управление анимацией с помощью свойств From, To, и By | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Анимация From, to и by"
  - "простая анимация"
  - "анимация, простая анимация"
  - "анимация From, To, By"
ms.assetid: 59afba57-6fc1-44c8-987e-8a5f4142adad
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Управление анимацией с помощью свойств From, To, и By
«From/To/By» или «базовая анимация» создает переход между двумя целевыми значениями (см. [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md) введение в различные виды анимации). Чтобы задать целевые значения основной анимации, используйте его <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства.  В следующей таблице перечислены как <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства, которые могут использоваться совместно или отдельно для определения анимации целевого значения.  
  
|Свойства, заданные|Результирующее поведение|  
|--------------------------|------------------------|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>|Анимация продвигается от значения, указанного в <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> выходного значения, в зависимости от способа настройки предыдущей анимации к базовому значению анимируемого свойства или к предыдущей анимации свойства.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and                              <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Анимация продвигается от значения, указанного в <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство для значения, указанного в <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойства.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> and                              <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Анимация продвигается от значения, указанного в <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойству значение, указанное на сумму <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>|Анимация продвигается от базового значения анимируемого свойства или значение для значения, указанного в выходных данных предыдущей анимации <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойства.|  
|<xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>|Анимация продвигается от базового значения анимируемого свойства или предыдущей анимации выходного значения к сумме этого значения и значения, указанного в <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойство.|  
  
> [!NOTE]
>  Не задавайте одновременно <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойство одной анимации.  
  
 Чтобы использовать другие методы интерполяции или выполнять анимацию между более чем двумя целевыми значениями, используйте анимации по полным кадрам. В разделе [сведения об анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) Дополнительные сведения.  
  
 Сведения о применении нескольких анимаций к одному свойству см. в разделе [сведения об анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
 В приведенном ниже примере показаны разные влияния установки <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, и <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойств анимации.  
  
## <a name="example"></a>Пример  
 [!code-xml[BasicAnimations_snippet#AnimationTargetValuesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BasicAnimations_snippet/CS/AnimationTargetValuesExample.xaml#animationtargetvalueswholepage)]  
  
## <a name="see-also"></a>См. также  
 [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения об анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [FROM, To и пример целевых значений анимации](http://go.microsoft.com/fwlink/?LinkID=159988)