---
title: "Общие сведения об анимациях From/To/By | Microsoft Docs"
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
  - "анимация, From, To, By"
  - "анимация From, To, By"
ms.assetid: 516fce0a-e7f8-49b8-b018-53b3d409a8a3
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Общие сведения об анимациях From/To/By
В этом разделе описываются способы использования анимаций From\/To\/By для анимации [свойств зависимостей](GTMT).  Анимация From\/To\/By создает переход между двумя значениями.  
  
 В этом разделе содержатся следующие подразделы.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prereq"></a>   
## Предварительные требования  
 Для понимания этого раздела требуется знакомство с возможностями анимаций [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Вводные сведения о функциональных возможностях анимации см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
<a name="whatisanimation"></a>   
## Анимация From\/To\/By  
 Анимация From\/To\/By ― это тип анимации <xref:System.Windows.Media.Animation.AnimationTimeline>, которая создает переход между начальным и конечным значением.  Временной интервал, по истечении которого переход завершается, определяется с помощью свойства <xref:System.Windows.Media.Animation.Timeline.Duration%2A> этой анимации.  
  
 Можно применять анимацию From\/To\/By к свойству, используя <xref:System.Windows.Media.Animation.Storyboard> в разметке и коде, или с помощью метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> в коде.  Анимацию From\/To\/By можно также использовать для создания <xref:System.Windows.Media.Animation.AnimationClock> и применения к одному или нескольким свойствам.  Дополнительные сведения о различных способах применения анимации см. в разделе [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
 Анимации From\/To\/By могут иметь не более двух конечных значений.  Если требуется анимация, которая имеет более двух конечных значений, используйте анимацию по полным кадрам.  Анимация по полным кадрам описана в разделе [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
<a name="animation_types"></a>   
## Типы анимаций From\/To\/By  
 Поскольку анимация создает значения свойств, для различных типов свойств существуют различные типы анимации.  Для анимации свойства, которое принимает значение <xref:System.Double>, например свойства <xref:System.Windows.FrameworkElement.Width%2A> элемента, необходимо использовать анимацию, создающую значения <xref:System.Double>.  Для анимации свойства, которое принимает значение <xref:System.Windows.Point>, необходимо использовать анимацию, создающую значения <xref:System.Windows.Point>, и т. д.  
  
 Классы анимации From\/To\/By принадлежат к пространству имен <xref:System.Windows.Media.Animation> и используют следующие правила именования:  
  
 *\<Тип\>* `Animation`  
  
 *\<Тип\>* ― тип значения, для которого класс выполняет анимацию.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет следующие классы анимации From\/To\/By.  
  
|Тип свойства|Соответствующий класс анимации From\/To\/By|  
|------------------|-------------------------------------------------|  
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
## Целевые значения  
 Анимация From\/To\/By создает переход между двумя целевыми значениями.  Обычно задается начальное значение \(с помощью свойства <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>\) и конечное значение \(с помощью свойства <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>\).  Однако можно также указать что\-то одно: начальное значение, конечное значение или значение сдвига.  В таких случаях анимация получает отсутствующее целевое значение из свойства, для которого выполняется анимация.  В следующем списке приведены различные способы задания целевых значений анимации.  
  
-   **Начальное значение**  
  
     Если требуется явно указать начальное значение анимации, то используется свойство <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>.  Можно использовать свойство <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> отдельно, вместе со свойством <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> или свойством <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  Если указано только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, анимация переходит от этого значения к базовому значению свойства, для которого она выполняется.  
  
-   **Конечное значение**  
  
     Чтобы указать конечное значения анимации, используется свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  Если свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> используется отдельно, анимация получает начальное значение из свойства, для которого она выполняется, или из выходных данных другой анимации, которая применяется к тому же свойству.  Можно использовать свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> вместе со свойством <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, чтобы явно указать начальное и конечное значения для анимации.  
  
-   **Значение сдвига**  
  
     Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> позволяет указать для анимации сдвиг вместо явного начального или конечного значения.  Свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации указывает, на сколько анимация изменяет значение за то время, пока она продолжается.  Можно использовать свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> отдельно или вместе со свойством <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>.  Если задано только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, анимация добавляет значение сдвига к базовому значению свойства или к выходным данным другой анимации.  
  
<a name="examples"></a>   
## Использование значений From\/To\/By  
 В следующих разделах даются сведения по использованию свойств <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> вместе или по отдельности.  
  
 Во всех примерах этого раздела используется тип <xref:System.Windows.Media.Animation.DoubleAnimation>, который является типом анимации From\/To\/By, для анимации свойства <xref:System.Windows.FrameworkElement.Width%2A> элемента <xref:System.Windows.Shapes.Rectangle>, который имеет 10 [аппаратно\-независимых пикселей](GTMT) в высоту и 100 [аппаратно\-независимых пикселей](GTMT) в ширину.  
  
 Хотя в каждом примере используется тип анимации <xref:System.Windows.Media.Animation.DoubleAnimation>, свойства From, To и By всех анимаций From\/To\/By ведут себя одинаково.  Хотя в каждом из этих примеров используется тип анимации <xref:System.Windows.Media.Animation.Storyboard>, можно использовать анимации From\/To\/By другими способами.  Дополнительные сведения см. в разделе [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
### From\/To  
 Если заданы значения двух атрибутов <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, то анимация выполняется от значения свойства <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> к значению свойства <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 В следующем примере свойству <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> класса <xref:System.Windows.Media.Animation.DoubleAnimation> присваивается значение 50 и свойству <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> присваивается значение 300.  В результате выполняется анимация свойства <xref:System.Windows.FrameworkElement.Width%2A> класса <xref:System.Windows.Shapes.Rectangle> от 50 до 300.  
  
 [!code-csharp[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromtoanimationinline)]
 [!code-vb[basicvalues_snip#FromToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromtoanimationinline)]  
  
### Целевой тип  
 Если задано только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, то анимация продвигается от базового значения анимируемого свойства либо от выходных данных составной анимации, которая ранее применялась к тому же свойству, к значению, заданному свойством <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>.  
  
 \("Составная анимация" ссылается на анимацию <xref:System.Windows.Media.Animation.ClockState> или на анимацию <xref:System.Windows.Media.Animation.ClockState>, ранее применявшуюся к тому же свойству, которое все еще действует, пока применяется текущая анимация посредством поведения переадресации <xref:System.Windows.Media.Animation.HandoffBehavior>.\)  
  
 В следующем примере свойству <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A> класса <xref:System.Windows.Media.Animation.DoubleAnimation> присваивается значение 300.  Так как начальное значение не было указано, <xref:System.Windows.Media.Animation.DoubleAnimation> использует в качестве начального значения базовое значение \(100\) свойства <xref:System.Windows.FrameworkElement.Width%2A>.  Анимация свойства <xref:System.Windows.FrameworkElement.Width%2A> элемента <xref:System.Windows.Shapes.Rectangle> выполняется от значения 100 к целевому значению анимации 300.  
  
 [!code-csharp[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#toanimationinline)]
 [!code-vb[basicvalues_snip#ToAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#toanimationinline)]  
  
### By  
 Если установлено только свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации, то анимация продвигается от базового значения свойства, к которому она применяется, либо от выходных данных составной анимации к сумме этого значения и значения свойства <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
 В следующем примере свойству <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> класса <xref:System.Windows.Media.Animation.DoubleAnimation> присваивается значение 300.  Поскольку начальное значение не задается, <xref:System.Windows.Media.Animation.DoubleAnimation> использует в качестве начального значения базовое значение свойства <xref:System.Windows.FrameworkElement.Width%2A>, равное 100.  Конечное значение определяется путем добавления значения 300 свойства <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации к ее начальному значению 100, и получается значение 400.  В результате выполняется анимация свойства <xref:System.Windows.FrameworkElement.Width%2A> класса <xref:System.Windows.Shapes.Rectangle> от 100 до 400.  
  
 [!code-csharp[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#byanimationinline)]
 [!code-vb[basicvalues_snip#ByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#byanimationinline)]  
  
### From\/By  
 Если задаются свойства <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации, то анимация продвигается от значения свойства <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> к значению, которое определяется суммой свойств <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>.  
  
 В следующем примере свойству <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> класса <xref:System.Windows.Media.Animation.DoubleAnimation> присваивается значение 50 и свойству <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> присваивается значение 300.  Конечное значение определяется путем добавления значения 300 свойства <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> анимации к ее начальному значению 50, и получается значение 350.  В результате выполняется анимация свойства <xref:System.Windows.FrameworkElement.Width%2A> класса <xref:System.Windows.Shapes.Rectangle> от 50 до 350.  
  
 [!code-csharp[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#frombyanimationinline)]
 [!code-vb[basicvalues_snip#FromByAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#frombyanimationinline)]  
  
### Исходный тип  
 Если указано только значение <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> анимации, то анимация продвигается от значения, заданного свойством <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A>, к базовому значению свойства, для которого выполняется анимация, или к выходным данным составной анимации.  
  
 В следующем примере свойству <xref:System.Windows.Media.Animation.DoubleAnimation.From%2A> класса <xref:System.Windows.Media.Animation.DoubleAnimation> присваивается значение 50.  Поскольку конечное значение не было задано, <xref:System.Windows.Media.Animation.DoubleAnimation> использует базовое значение свойства <xref:System.Windows.FrameworkElement.Width%2A>, равное 100, в качестве конечного значения.  Для свойства <xref:System.Windows.FrameworkElement.Width%2A> элемента <xref:System.Windows.Shapes.Rectangle> выполняется анимация от 50 до базового значения 100 свойства <xref:System.Windows.FrameworkElement.Width%2A>.  
  
 [!code-csharp[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicvalues_snip/CSharp/AnimationTargetValuesExample.cs#fromanimationinline)]
 [!code-vb[basicvalues_snip#FromAnimationInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicvalues_snip/VisualBasic/AnimationTargetValuesExample.vb#fromanimationinline)]  
  
### To\/By  
 Если заданы два свойства анимации, и <xref:System.Windows.Media.Animation.DoubleAnimation.To%2A>, и <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>, то свойство <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> будет проигнорировано.  
  
<a name="otheranimationtypes"></a>   
## Другие типы анимации  
 Анимации From\/To\/By ― не единственный тип анимации, имеющийся в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: предоставляются также анимация по полным кадрам и анимация по пути.  
  
-   Анимация по полным кадрам выполняется по любому числу целевых значений, описанных с помощью полных кадров.  Дополнительные сведения см. в разделе [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md).  
  
-   Анимация по пути создает выходные значения из <xref:System.Windows.Media.PathGeometry>.  Дополнительные сведения см. в разделе [Общие сведения об анимация с использованием пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] также позволяет создавать собственные настраиваемые типы анимации.  Дополнительные сведения см. в разделе [Общие сведения о пользовательской анимации](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md).  
  
## См. также  
 <xref:System.Windows.Media.Animation.Timeline>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Общие сведения об анимация с использованием пути](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)   
 [Общие сведения о пользовательской анимации](../../../../docs/framework/wpf/graphics-multimedia/custom-animations-overview.md)   
 [From, To, and By Animation Target Values Sample](http://go.microsoft.com/fwlink/?LinkID=159988)