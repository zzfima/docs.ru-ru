---
title: Обзор анимаций From-To-By
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 3095ec2c6307faaaa8049f23fffb5909cb3042d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fromtoby-animations-overview"></a>Общие сведения об анимациях From/To/By
В этом разделе описываются способы использования анимаций From/To/By для свойств зависимостей. Анимация From/To/By создает переход между двумя целевыми значениями.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы разобраться в этом разделе, необходимо ознакомиться с [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] возможностями анимаций. Общие сведения о функциональных возможностях анимации см. в разделе [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>Что такое анимация From/To/By?  
 From/To/By анимации — это тип <xref:System.Windows.Media.Animation.AnimationTimeline> , создает переход между начальным и конечным значением. Количество времени, переход завершается, определяется <xref:System.Windows.Media.Animation.Timeline.Duration%2A> этой анимации.  
  
 Можно применить From/To/By анимации к свойству с помощью <xref:System.Windows.Media.Animation.Storyboard> в разметке и коде или с помощью <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода в коде. Можно также использовать анимацию для создания <xref:System.Windows.Media.Animation.AnimationClock> и применить его к одному или нескольким свойствам. Дополнительные сведения о различных способах применения анимации см. в разделе [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
 Анимация From/To/By может иметь не более двух целевых значений. Если требуется анимация, у которой более двух целевых значений, используйте анимацию по ключевым кадрам. Кадрам описаны в разделе [кадрами ключ](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>Типы анимации From/To/By  
 Так как при анимации создаются значения свойств, существуют различные типы анимаций для различных типов свойств. Для анимации свойства, которое принимает <xref:System.Double>, такие как <xref:System.Windows.FrameworkElement.Width%2A> свойства элемента, используйте анимацию, создающую <xref:System.Double> значения. Для анимации свойства, которое принимает <xref:System.Windows.Point>, используйте анимацию, создающую <xref:System.Windows.Point> значения и т. д.  
  
 Классы анимации From/To/By принадлежат к <xref:System.Windows.Media.Animation> пространства имен и используется следующее соглашение об именовании:  
  
 *\<Тип>* `Animation`  
  
 Где *\<Type>* — тип значения, которое выполняет анимацию класса.  
  
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
 Анимация From/To/By создает переход между двумя целевыми значениями. Обычно задается начальное значение (с помощью <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойства) и конечное значение (с помощью <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство). Но можно также указать только начальное значение, конечное или значение смещения. В таких случаях анимация получает отсутствующее целевое значение из свойства, для которого она выполняется. Ниже описаны различные способы задания целевых значений анимации.  
  
-   **Начальное значение**  
  
     Используйте <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство, если требуется явно указать начальное значение анимации. Можно использовать <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство отдельно или с <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> или <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства. Если указать только <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойством, анимация переходит от этого значения к базовому значению анимируемого свойства.  
  
-   **Конечное значение**  
  
     Чтобы указать конечное значение анимации, используйте его <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство. Если вы используете <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> само свойство, анимация получает начальное значение анимируемого свойства или выходные данные другой анимации, которая применяется к данному свойству. Можно использовать <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство вместе с <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство, чтобы явно указать начальное и конечное значения для анимации.  
  
-   **Значение смещения**  
  
     <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Свойство позволяет указать смещение вместо явного начального или конечное значение для анимации. <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> Анимации указывает, сколько анимация изменяет значение на протяжении своего времени. Можно использовать <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойство отдельно или с <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство. Если указать только <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства, анимация добавляет значение сдвига к базовому значению свойства или к выходу из другой анимации.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>Использование значений From/To/By  
 В следующих разделах описаны способы использования <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства вместе или по отдельности.  
  
 В примерах этого раздела используется <xref:System.Windows.Media.Animation.DoubleAnimation>, который является типом анимации From/To/By, для которого должна начаться анимация <xref:System.Windows.FrameworkElement.Width%2A> свойство <xref:System.Windows.Shapes.Rectangle> то есть 10 аппаратно-независимых пикселях в высокого уровня и 100 аппаратно-независимых пикселей в ширину.  
  
 Несмотря на то, что в каждом примере использует <xref:System.Windows.Media.Animation.DoubleAnimation>, From, To и By свойства всех From/To/By анимации ведут себя одинаково. Несмотря на то, что каждый из этих примеров использует <xref:System.Windows.Media.Animation.Storyboard>, анимаций From/To/By можно использовать в других целях. Дополнительные сведения см. в разделе [Общие сведения о методах анимации свойства](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>От/кому  
 При задании <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> значения одновременно, анимация продвигается от значения, который задается параметром <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> значение, который задается параметром свойства <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство.  
  
 В следующем примере задается <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство <xref:System.Windows.Media.Animation.DoubleAnimation> 50 и его <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> присваивается значение 300. В результате <xref:System.Windows.FrameworkElement.Width%2A> из <xref:System.Windows.Shapes.Rectangle> анимация от 50 до 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>Кому  
 Если задано только <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство, в процессе анимации к базовому значению анимируемого свойства, или из выходных данных составной анимации, которая ранее была применена к одному свойству задается значение <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство.  
  
 («Составная анимация» ссылается на <xref:System.Windows.Media.Animation.ClockState.Active> или <xref:System.Windows.Media.Animation.ClockState.Filling> анимации, которая ранее примененные к то же свойство, оно по-прежнему действует при применении текущей анимации с помощью <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> поведение перемещения.)  
  
 В следующем примере задается просто <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> свойство <xref:System.Windows.Media.Animation.DoubleAnimation> до 300. Так как начальное значение не указано, <xref:System.Windows.Media.Animation.DoubleAnimation> использует базовое значение (100) <xref:System.Windows.FrameworkElement.Width%2A> свойство в качестве начального значения. <xref:System.Windows.FrameworkElement.Width%2A> Из <xref:System.Windows.Shapes.Rectangle> выполняется анимация от 100 анимации целевое значение 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>На  
 Если задано только <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойство анимации, в процессе анимации к базовому значению анимируемого свойства, или из выходных данных составной анимации к сумме этого значения и значения, который задается параметром <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойство.  
  
 В следующем примере задается просто <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойство <xref:System.Windows.Media.Animation.DoubleAnimation> до 300. Так как в примере указывается начальное значение, <xref:System.Windows.Media.Animation.DoubleAnimation> использует к базовому значению <xref:System.Windows.FrameworkElement.Width%2A> 100 свойства, как начальное значение. Конечное значение определяется путем добавления <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> значение анимации, 300, к его начальному значению 100:400. В результате <xref:System.Windows.FrameworkElement.Width%2A> из <xref:System.Windows.Shapes.Rectangle> анимируется от 100 до 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 При задании <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации, то анимация продвигается от значения, который задается параметром <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство в значение, которое указано на сумму <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойства.  
  
 В следующем примере задается <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство <xref:System.Windows.Media.Animation.DoubleAnimation> 50 и его <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> присваивается значение 300. Конечное значение определяется путем добавления <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> значение анимации 300 к начальному значению, 50 350. В результате <xref:System.Windows.FrameworkElement.Width%2A> из <xref:System.Windows.Shapes.Rectangle> анимация от 50 до 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>Исходный тип  
 Если указано только <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> значения анимации, то анимация продвигается от значения, который задается параметром <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойства, к базовому значению анимируемого свойства или к выходу составной анимации.  
  
 В следующем примере задается просто <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> свойство <xref:System.Windows.Media.Animation.DoubleAnimation> до 50. Так как конечное значение не указано, <xref:System.Windows.Media.Animation.DoubleAnimation> использует к базовому значению <xref:System.Windows.FrameworkElement.Width%2A> 100 свойства, в качестве конечного значения. <xref:System.Windows.FrameworkElement.Width%2A> Из <xref:System.Windows.Shapes.Rectangle> анимация от 50 до базового значения <xref:System.Windows.FrameworkElement.Width%2A> 100 свойства.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Если заданы оба <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации, <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> свойство игнорируется.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>Другие типы анимаций  
 From/To/By ― не единственный тип анимации, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет: он также предоставляет кадрам и анимация по пути.  
  
-   Анимация по ключевым кадрам анимирует по любому числу конечных значений, описанных с помощью ключевых кадров. Дополнительные сведения см. в разделе [кадрами ключ](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   Анимация по пути создает выходные значения <xref:System.Windows.Media.PathGeometry>. Дополнительные сведения см. в разделе [Обзор анимации пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также позволяет создавать собственные настраиваемые типы анимации. Дополнительные сведения см. в разделе [Общие сведения о настраиваемых анимации](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.Timeline>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Общие сведения об анимации с использованием пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)  
 [Общие сведения о пользовательской анимации](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)  
 [Пример целевых значений анимации From, To и By](http://go.microsoft.com/fwlink/?LinkID=159988)
