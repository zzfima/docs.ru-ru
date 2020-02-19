---
title: Общие сведения об анимации от-to-by
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], From/to/by
- From/to/by animation
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
ms.openlocfilehash: 661c035f55ba1fb550726d75921cd01a72b2eecc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449014"
---
# <a name="fromtoby-animations-overview"></a>Общие сведения об анимациях From/To/By
В этом разделе описываются способы использования анимаций From/To/By для свойств зависимостей. Анимация From/To/By создает переход между двумя целевыми значениями.  
  
<a name="prereq"></a>   
## <a name="prerequisites"></a>предварительные требования  
 Чтобы понять этот раздел, необходимо ознакомиться с возможностями анимации [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Общие сведения о функциях анимации см. в разделе [Обзор анимации](animation-overview.md).  
  
<a name="whatisanimation"></a>   
## <a name="what-is-a-fromtoby-animation"></a>Что такое анимация From/To/By?  
 Анимация From/To/By — это тип <xref:System.Windows.Media.Animation.AnimationTimeline>, который создает переход между начальным и конечным значениями. Количество времени, затрачиваемого на завершение перехода, определяется <xref:System.Windows.Media.Animation.Timeline.Duration%2A> этой анимации.  
  
 Анимацию From/To/By можно применить к свойству с помощью <xref:System.Windows.Media.Animation.Storyboard> в разметке и коде или с помощью метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> в коде. Вы также можете использовать анимацию From/To/By, чтобы создать <xref:System.Windows.Media.Animation.AnimationClock> и применить ее к одному или нескольким свойствам. Дополнительные сведения о различных способах применения анимации см. в разделе [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md).  
  
 Анимация From/To/By может иметь не более двух целевых значений. Если требуется анимация, у которой более двух целевых значений, используйте анимацию по ключевым кадрам. Анимация по ключевым кадрам описывается в разделе [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## <a name="fromtoby-animation-types"></a>Типы анимации From/To/By  
 Так как при анимации создаются значения свойств, существуют различные типы анимаций для различных типов свойств. Чтобы анимировать свойство, которое принимает <xref:System.Double>, например свойство <xref:System.Windows.FrameworkElement.Width%2A> элемента, используйте анимацию, которая создает значения <xref:System.Double>. Чтобы анимировать свойство, которое принимает <xref:System.Windows.Point>, используйте анимацию, создающую <xref:System.Windows.Point> значения и т. д.  
  
 Классы анимации From/To/By относятся к пространству имен <xref:System.Windows.Media.Animation> и используют следующее соглашение об именовании:  
  
 *> типа\<* `Animation`  
  
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
 Анимация From/To/By создает переход между двумя целевыми значениями. Обычно можно указать начальное значение (задать его с помощью свойства <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>) и конечное значение (задать его с помощью свойства <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>). Но можно также указать только начальное значение, конечное или значение смещения. В таких случаях анимация получает отсутствующее целевое значение из свойства, для которого она выполняется. Ниже описаны различные способы задания целевых значений анимации.  
  
- **Начальное значение**  
  
     Используйте свойство <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, если необходимо явно указать начальное значение анимации. Можно использовать свойство <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> само по себе или со свойством <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> или <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>. Если указать только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, анимация переходит от этого значения к базовому значению анимированного свойства.  
  
- **Конечное значение**  
  
     Чтобы указать конечное значение анимации, используйте свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>. При использовании свойства <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> само по себе анимация получает свое начальное значение из анимируемого свойства или из выходных данных другой анимации, примененной к тому же самому свойству. Можно использовать свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> вместе со свойством <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, чтобы явно указать начальные и конечные значения для анимации.  
  
- **Значение смещения**  
  
     Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> позволяет указать смещение, а не явное начальное или конечное значение для анимации. Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации определяет, сколько времени анимация изменяет значение в течение ее длительности. Можно использовать свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> само по себе или со свойством <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>. Если указано только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, то анимация добавляет значение смещения к базовому значению свойства или к выходу другой анимации.  
  
<a name="examples"></a>   
## <a name="using-fromtoby-values"></a>Использование значений From/To/By  
 В следующих разделах описано, как использовать свойства <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> вместе или по отдельности.  
  
 В примерах в этом разделе используется <xref:System.Windows.Media.Animation.DoubleAnimation>, который является типом анимации From/To/By, для анимации свойства <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle>, которое имеет 10 аппаратно-независимые пикселя высокого уровня и 100 аппаратно независимых пикселей в ширину.  
  
 Хотя в каждом примере используется <xref:System.Windows.Media.Animation.DoubleAnimation>, свойства From, to и by всех анимаций from/to/by ведут себя одинаково. Хотя в каждом из этих примеров используется <xref:System.Windows.Media.Animation.Storyboard>, можно использовать анимацию from/to/с другими способами. Дополнительные сведения см. в разделе [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md).  
  
### <a name="fromto"></a>От кого/Кому  
 При одновременном задании значений <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> анимация выполняется от значения, указанного в свойстве <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, к значению, заданному свойством <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 В следующем примере свойству <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> присваивается значение 50, а свойству <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> — значение 300. В результате <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> анимируется от 50 до 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### <a name="to"></a>Чтобы  
 Когда вы устанавливаете только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, анимация выполняется от базового значения анимированного свойства или из выходных данных составной анимации, которая ранее была применена к тому же свойству, к значению, заданному свойством <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 ("Составление анимации" означает <xref:System.Windows.Media.Animation.ClockState.Active> или <xref:System.Windows.Media.Animation.ClockState.Filling> анимацию, которая ранее применялась к тому же свойству, которое по-прежнему действует при применении текущей анимации с помощью <xref:System.Windows.Media.Animation.HandoffBehavior.Compose> поведения передачи.)  
  
 В следующем примере задается только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> <xref:System.Windows.Media.Animation.DoubleAnimation>, равное 300. Поскольку начальное значение не указано, <xref:System.Windows.Media.Animation.DoubleAnimation> использует базовое значение (100) свойства <xref:System.Windows.FrameworkElement.Width%2A> в качестве его начального значения. <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> анимируется от 100 до целевого значения анимации 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### <a name="by"></a>на  
 Когда вы устанавливаете только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации, анимация выполняется от базового значения анимируемого свойства или от выходных данных составной анимации до суммы этого значения и значения, заданного свойством <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>а.  
  
 В следующем примере задается только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> <xref:System.Windows.Media.Animation.DoubleAnimation>, равное 300. Так как в примере не указывается начальное значение, <xref:System.Windows.Media.Animation.DoubleAnimation> использует базовое значение свойства <xref:System.Windows.FrameworkElement.Width%2A> 100 в качестве начального значения. Конечное значение определяется путем добавления <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> значения анимации 300, к ее начальному значению 100:400. В результате <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> анимируется от 100 до 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### <a name="fromby"></a>From/By  
 При задании свойств <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации анимация выполняется от значения, указанного в свойстве <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, к значению, заданному в сумме свойств <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
 В следующем примере свойству <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation> присваивается значение 50, а свойству <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> — значение 300. Конечное значение определяется путем добавления <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> значения анимации 300, к ее начальному значению 50:350. В результате <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> анимируется от 50 до 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### <a name="from"></a>От  
 При указании только <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> значения анимации анимация выполняется от значения, указанного свойством <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, к базовому значению анимируемого свойства или к выходным данным анимированной анимации.  
  
 В следующем примере задается только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> <xref:System.Windows.Media.Animation.DoubleAnimation>, равное 50. Поскольку конечное значение не указано, <xref:System.Windows.Media.Animation.DoubleAnimation> использует базовое значение свойства <xref:System.Windows.FrameworkElement.Width%2A> 100 в качестве конечного значения. <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.Shapes.Rectangle> анимируется от 50 к базовому значению свойства <xref:System.Windows.FrameworkElement.Width%2A> 100.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](~/samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](~/samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### <a name="toby"></a>To/By  
 Если заданы свойства <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации, свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> игнорируется.  
  
<a name="otheranimationtypes"></a>   
## <a name="other-animation-types"></a>Другие типы анимаций  
 Анимации From/To/By не являются единственным типом анимации, которую [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет: он также обеспечивает анимацию по ключевым кадрам и анимацию по путям.  
  
- Анимация по ключевым кадрам анимирует по любому числу конечных значений, описанных с помощью ключевых кадров. Дополнительные сведения см. в статье [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md).  
  
- Анимация по контуру создает выходные значения из <xref:System.Windows.Media.PathGeometry>. Дополнительные сведения см. в разделе [Общие сведения об анимации по путям](path-animations-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также позволяет создавать собственные настраиваемые типы анимации. Дополнительные сведения см. в разделе [Общие сведения о пользовательской анимации](custom-animations-overview.md).  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Animation.Timeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о раскадровке](storyboards-overview.md)
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Общие сведения об анимации с использованием пути](path-animations-overview.md)
- [Общие сведения о пользовательской анимации](custom-animations-overview.md)
- [Пример целевых значений анимации From, To, By](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/TargetValues)
