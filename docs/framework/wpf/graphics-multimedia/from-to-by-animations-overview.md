---
title: Обзор анимации от
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 135f01823d374b30f8d4d41762d2267a254f98c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186460"
---
# <a name="fromtoby-animations-overview"></a>Общие сведения об анимациях From/To/By
В этом разделе описываются способы использования анимаций From/To/By для свойств зависимостей. Анимация From/To/By создает переход между двумя целевыми значениями.  
  
<a name="prereq"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы понять эту тему, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] вы должны быть знакомы с функциями анимации. Для введения в функции анимации, [см.](animation-overview.md)  
  
<a name="whatisanimation"></a>
## <a name="what-is-a-fromtoby-animation"></a>Что такое анимация From/To/By?  
 A From/To/By animation — <xref:System.Windows.Media.Animation.AnimationTimeline> это тип, создающий переход между исходным значением и исходным значением. Количество времени, которое требуется для завершения, определяется этой анимацией. <xref:System.Windows.Media.Animation.Timeline.Duration%2A>  
  
 Вы можете применить анимацию From/To/By к <xref:System.Windows.Media.Animation.Storyboard> свойству с помощью разметки и кода или с помощью метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> в коде. Вы также можете использовать from/To/By <xref:System.Windows.Media.Animation.AnimationClock> Animation для создания и применения его к одному или несколько свойствам. Дополнительные сведения о различных способах применения анимации см. в разделе [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md).  
  
 Анимация From/To/By может иметь не более двух целевых значений. Если требуется анимация, у которой более двух целевых значений, используйте анимацию по ключевым кадрам. Анимация с ключевым имуатором описана в [обзоре анимации Key-Frame.](key-frame-animations-overview.md)  
  
<a name="animation_types"></a>
## <a name="fromtoby-animation-types"></a>Типы анимации From/To/By  
 Так как при анимации создаются значения свойств, существуют различные типы анимаций для различных типов свойств. Чтобы оживить <xref:System.Double>свойство, которое занимает, <xref:System.Windows.FrameworkElement.Width%2A> например свойство элемента, <xref:System.Double> используйте анимацию, которая производит значения. Чтобы оживить <xref:System.Windows.Point>свойство, которое занимает, используйте анимацию, которая производит <xref:System.Windows.Point> значения, и так далее.  
  
 От/До/По классам анимации относятся к пространству <xref:System.Windows.Media.Animation> имен и используются следующие соглашения имен:  
  
 * \<Тип>*`Animation`  
  
 Где * \<тип>* — это тип значения, который оживляет класс.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет следующие классы анимации From/To/By.  
  
|Тип свойства|Соответствующий класс анимации From/To/By|  
|-------------------|------------------------------------------------|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimation>|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimation>|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimation>|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimation>|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16Animation>|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32Animation>|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64Animation>|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimation>|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimation>|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimation>|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimation>|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimation>|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimation>|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimation>|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimation>|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimation>|  
  
<a name="anim_values"></a>
## <a name="target-values"></a>Целевые значения  
 Анимация From/To/By создает переход между двумя целевыми значениями. Обычно указывается исходное значение (установите <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> его с помощью свойства) и <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> конечную величину (установите его с помощью свойства). Но можно также указать только начальное значение, конечное или значение смещения. В таких случаях анимация получает отсутствующее целевое значение из свойства, для которого она выполняется. Ниже описаны различные способы задания целевых значений анимации.  
  
- **Исходное значение**  
  
     Используйте <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство, если требуется указать исходное значение анимации. Вы можете <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> использовать свойство само <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> по <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> себе, или с или собственности. Если указать <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> только свойство, анимация переходит от этого значения к базовому значению анимированного свойства.  
  
- **Конечное значение**  
  
     Чтобы указать конечное значение анимации, используйте ее <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство. Если вы <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> используете свойство само по себе, анимация получает его начальное значение от свойства, которое анимируется или от вывода другой анимации, которая применяется к тому же свойству. Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> можно использовать вместе <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> с свойством для явного указания начальных и заканчивающихся значений для анимации.  
  
- **Значение смещения**  
  
     Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> позволяет указать смещение вместо явного начального или конечного значения для анимации. Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации определяет, насколько анимация изменяет значение в течение своей продолжительности. Вы можете <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> использовать свойство самостоятельно <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> или с собственностью. Если вы указываете только свойство, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимация добавляет смещенное значение к базовому значению свойства или выходу другой анимации.  
  
<a name="examples"></a>
## <a name="using-fromtoby-values"></a>Использование значений From/To/By  
 Следующие разделы описывают, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>как <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>использовать, и свойства вместе или по отдельности.  
  
 Примеры в этом разделе <xref:System.Windows.Media.Animation.DoubleAnimation>каждый использовать , который является одним из типа <xref:System.Windows.FrameworkElement.Width%2A> от / <xref:System.Windows.Shapes.Rectangle> до / По анимации, чтобы оживить свойство, что составляет 10 устройств независимых пикселей высотой и 100 устройств независимых пикселей в ширину.  
  
 Хотя каждый <xref:System.Windows.Media.Animation.DoubleAnimation>пример использует, от, к, и свойства всех от / до / По анимации ведут себя одинаково. Хотя каждый из <xref:System.Windows.Media.Animation.Storyboard>этих примеров использует, вы можете использовать от / до / По анимации в других отношениях. Для получения дополнительной информации, см [Собственности Анимация Методы Обзор](property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>От/кому  
 При объединении <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> значений и <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> значений анимация переходит от <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> значения, указанного свойством, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> к значению, указанному свойством.  
  
 Следующий пример <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> устанавливает свойство <xref:System.Windows.Media.Animation.DoubleAnimation> до 50 и свое <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство до 300. В результате, <xref:System.Windows.FrameworkElement.Width%2A> анимированные <xref:System.Windows.Shapes.Rectangle> от 50 до 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>Чтобы  
 При установке <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> только свойства анимация переходит от базового значения анимированного свойства или от вывода компонимации, которая ранее <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> применялась к тому же свойству, к значению, указанному свойством.  
  
 ("Композиция анимации" <xref:System.Windows.Media.Animation.ClockState.Active> относится к <xref:System.Windows.Media.Animation.ClockState.Filling> или анимации, которая ранее применялась к тому же <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> свойству, которое все еще действует, когда текущая анимация была применена с помощью поведения handoff.)  
  
 Следующий пример устанавливает <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> как <xref:System.Windows.Media.Animation.DoubleAnimation> раз свойство до 300. Поскольку начальное значение <xref:System.Windows.Media.Animation.DoubleAnimation> не было определено, базовое <xref:System.Windows.FrameworkElement.Width%2A> значение (100) свойства используется в качестве исходного значения. Из <xref:System.Windows.FrameworkElement.Width%2A> анимированных <xref:System.Windows.Shapes.Rectangle> от 100 до анимации целевое значение 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>на  
 При установке <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> только свойства анимации анимация переходит от базового значения анимированного свойства или от вывода компоняющей анимации к сумме этого значения и значения, указанного <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойством.  
  
 Следующий пример устанавливает <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> как <xref:System.Windows.Media.Animation.DoubleAnimation> раз свойство до 300. Поскольку в примере не указывается исходное значение, <xref:System.Windows.Media.Animation.DoubleAnimation> в качестве исходного значения используется базовое значение <xref:System.Windows.FrameworkElement.Width%2A> свойства 100. Конечное значение определяется <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> путем добавления значения анимации, 300, к ее начальному значению, 100: 400. В результате, <xref:System.Windows.FrameworkElement.Width%2A> анимированные <xref:System.Windows.Shapes.Rectangle> от 100 до 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 При установке <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> и свойств анимации анимация переходит от значения, <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> указанного свойством, к значению, <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> указанному суммой и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойствами.  
  
 Следующий пример <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> устанавливает свойство <xref:System.Windows.Media.Animation.DoubleAnimation> до 50 и свое <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойство до 300. Конечное значение определяется <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> путем добавления значения анимации, 300, к ее начальному значению, 50: 350. В результате, <xref:System.Windows.FrameworkElement.Width%2A> анимированные <xref:System.Windows.Shapes.Rectangle> от 50 до 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>От  
 Когда вы указываете только <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> значение анимации, анимация переходит от <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> значения, указанного свойством, к базовому значению анимированного свойства или к выходу сочинения анимации.  
  
 Следующий пример устанавливает <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> только <xref:System.Windows.Media.Animation.DoubleAnimation> свойство до 50. Поскольку конечное значение <xref:System.Windows.Media.Animation.DoubleAnimation> не было указано, в качестве исходного значения используется базовое значение <xref:System.Windows.FrameworkElement.Width%2A> свойства 100. Из <xref:System.Windows.FrameworkElement.Width%2A> анимированных <xref:System.Windows.Shapes.Rectangle> от 50 до <xref:System.Windows.FrameworkElement.Width%2A> базовой стоимости имущества, 100.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Если вы установите <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> как свойства, так <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> и свойства анимации, свойство игнорируется.  
  
<a name="otheranimationtypes"></a>
## <a name="other-animation-types"></a>Другие типы анимаций  
 От/до/По анимации не единственный тип [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] анимации, который обеспечивает: он также обеспечивает ключевые кадры анимации и пути анимации.  
  
- Анимация по ключевым кадрам анимирует по любому числу конечных значений, описанных с помощью ключевых кадров. Для получения дополнительной информации смотрите [обзор анимации key-Frame](key-frame-animations-overview.md).  
  
- Анимация пути генерирует значения вывода <xref:System.Windows.Media.PathGeometry>из . Для получения дополнительной [информации](path-animations-overview.md)смотрите обзор анимации пути .  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также позволяет создавать собственные настраиваемые типы анимации. Для получения дополнительной [информации смотрите обзор пользовательских анимаций](custom-animations-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о раскадровке](storyboards-overview.md)
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Общие сведения об анимации с использованием пути](path-animations-overview.md)
- [Общие сведения о пользовательской анимации](custom-animations-overview.md)
- [Пример целевых значений анимации From, To и By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
