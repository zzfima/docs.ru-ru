---
title: "Общие сведения об анимации по ключевым кадрам"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], key-frame
- key frames [WPF], about key-frame animations
- multiple animation target values [WPF]
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c4f4179087679ff891c705cf16693fc69c808d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="key-frame-animations-overview"></a>Общие сведения об анимации по ключевым кадрам
В этом разделе рассказывается об анимации по ключевым кадрам. Методика анимации по ключевым кадрам позволяет использовать более двух целевых значений и контролировать применяемый метод интерполяции.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания предлагаемого материала необходимо знакомство с принципами анимации [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и понятием временной шкалы. Общие сведения об анимации см. в разделе [Общие сведения об анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Также полезно иметь знания по анимации From/To/By. Дополнительные сведения см. в разделе "Общие сведения об анимации From/To/By".  
  
<a name="whatisakeyframeanimation"></a>   
## <a name="what-is-a-key-frame-animation"></a>Что такое анимации по ключевым кадрам?  
 Так же как при анимации From/To/By при анимации по ключевым кадрам выполняется анимация значения целевого свойства. Она создает переход между заданными значениями в ее <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. Но в отличие от анимации From/To/By, при которой создается переход между двумя значениями, при анимации по ключевым кадрам можно создавать переходы между любым числом целевых значений за один раз. В анимации по ключевым кадрам не используются свойства From, To и By для задания целевых значений. Целевые значения для анимации по ключевым кадрам описываются с помощью объектов ключевых кадров (отсюда термин — "анимация по ключевым кадрам"). Чтобы задать значения для анимации, опорного кадра объекты создаются и добавляются в область анимации <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> коллекции. При выполнении анимации создаются переходы между заданными кадрами.  
  
 Кроме того, что при анимации по ключевым кадрам поддерживается обработка нескольких целевых значений, некоторые методы анимации по ключевым кадрам поддерживают использование нескольких методов интерполяции. Метод интерполяции анимации определяет, как выполняется переход от одного значения к другому. Существует три типа интерполяции: дискретная, линейная и интерполяция сплайнами.  
  
 Чтобы выполнить анимацию по ключевым кадрам, сделайте следующее.  
  
-   Объявите анимации и укажите его <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, так же, как для анимации from/to/by.  
  
-   Для каждого значения, создайте ключевого кадра, соответствующего типа, установите его значение и <xref:System.Windows.Media.Animation.KeyTime>и добавьте его в анимации <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> коллекции.  
  
-   Свяжите анимацию со свойством так же как при анимации From/To/By. Дополнительные сведения о применении анимации к свойству с помощью раскадровки см. в разделе [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> для анимации <xref:System.Windows.Shapes.Rectangle> элемент для четырех разных местах.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
 Как и From/To/By анимации, анимацию кадрам может применяться к свойству с помощью <xref:System.Windows.Media.Animation.Storyboard> в разметке и коде или с помощью <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метода в коде. Можно также использовать для создания анимации кадрам <xref:System.Windows.Media.Animation.AnimationClock> и применить его к одному или нескольким свойствам. Дополнительные сведения о различных способах применения анимации см. в разделе [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## <a name="key-frame-animation-types"></a>Типы анимации по ключевым кадрам  
 Так как при анимации создаются значения свойств, существуют различные типы анимаций для различных типов свойств. Для анимации свойства, которое принимает <xref:System.Double> (например, элемент <xref:System.Windows.FrameworkElement.Width%2A> свойства), используйте анимацию, создающую <xref:System.Double> значения. Для анимации свойства, которое принимает <xref:System.Windows.Point>, используйте анимацию, создающую <xref:System.Windows.Point> значения и т. д.  
  
 Классы опорный кадр анимации принадлежат к <xref:System.Windows.Media.Animation> пространства имен и соответствовать следующее соглашение об именовании:  
  
 *\<Тип>* `AnimationUsingKeyFrames`  
  
 Где *\<Type>* — тип значения, которое выполняет анимацию класса.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет следующие классы анимации по ключевым кадрам.  
  
|Тип свойства|Соответствующий класс анимации From/To/By|Поддерживаемые методы интерполяции|  
|-------------------|------------------------------------------------|-------------------------------------|  
|<xref:System.Boolean>|<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>|Дискретная|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16AnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32AnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64AnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>|Дискретная|  
|<xref:System.Object>|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>|Дискретная|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.String>|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Дискретная|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
  
<a name="animation_target_values"></a>   
## <a name="target-values-key-frames-and-key-times"></a>Целевые значения (ключевые кадры) и временная шкала  
 Для анимации различных типов свойств существуют различные типы анимации по ключевым кадрам и, соответственно, различные типы объектов ключевых кадров — по одному для каждого типа анимированного значения и поддерживаемого метода интерполяции. Типы ключевых кадров удовлетворяют требованиям следующего соглашения об именах.  
  
 *\<InterpolationMethod>\<Type>* `KeyFrame`  
  
 Где *\<InterpolationMethod>* — метод интерполяции, используемый при анимации по ключевым кадрам, а *\<Type>* — тип значения, анимируемый классом. Метод анимации по ключевым кадрам, поддерживающий все три метода интерполяции, будет включать в себя три типа ключевых кадров, которые можно использовать. Например, можно использовать три типа опорного кадра с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>: <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>, и <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>. (Методы интерполяции подробно описаны в следующем разделе.)  
  
 Основная цель ключевого кадра является указание <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> и <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>. Все типы ключевых кадров предоставляют эти два свойства.  
  
-   <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> Свойство указывает целевое значение для этого полного кадра.  
  
-   <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> Свойство указывает, когда (в пределах анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A>) опорного кадра <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> достигается.  
  
 Когда начинается анимации ключевого кадра, перебор кадрами в порядке, определенном их <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> свойства.  
  
-   Если в момент времени 0 не ключевого кадра, анимация создает переход между текущее значение целевого свойства и <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> первого кадра; в противном случае анимация выходных значение становится значением первого кадра.  
  
-   Анимация создает переход между <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> первого и второго ключевых кадров, с помощью метода интерполяции, указанного в второй опорного кадра. Переход начинается с первого полного кадра <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> и заканчивается, когда второй опорного кадра <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> достигается.  
  
-   Анимация продолжается, создавая переходы от каждого предыдущего ключевого кадра к последующему.  
  
-   Наконец, анимация переходит к значению ключевого кадра с наибольшим временем, меньше или равно анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 Если анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A> — <xref:System.Windows.Duration.Automatic%2A> или его <xref:System.Windows.Media.Animation.Timeline.Duration%2A> равно времени последнего ключевого кадра, анимация завершается. В противном случае, если анимация <xref:System.Windows.Duration> больше, чем время последнего ключевого кадра, анимация удерживает значение ключевого кадра, пока он не достигнет конца его <xref:System.Windows.Duration>. Как и любая анимация использует анимацию кадрам его <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> свойства, чтобы определить, является ли она хранить конечное значение при достижении конца активного периода. Дополнительные сведения см. в разделе [Общие сведения о характере поведения во времени](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> объект, определенный в предыдущем примере для демонстрации как <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> и <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> работают свойства.  
  
-   Первый кадр немедленно устанавливает выходное значение анимации равное 0.  
  
-   Второй ключевой кадр выполняет анимацию от 0 до 350. Она запускается после окончания первого ключевого кадра (в момент времени 0 секунд), выполняется в течение 2 секунд и заканчивается в момент времени = 0:0:2.  
  
-   Третий ключевой кадр выполняет анимацию от 350 до 50. Она запускается после окончания второго ключевого кадра (в момент времени 2 секунды), выполняется в течение 5 секунд и заканчивается в момент времени = 0:0:7.  
  
-   Четвертый ключевой кадр выполняет анимацию от 50 до 200. Она запускается после окончания третьего ключевого кадра (в момент времени 7 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:8.  
  
-   Поскольку <xref:System.Windows.Media.Animation.Timeline.Duration%2A> анимации было задано значение 10 секунд, анимация хранит его конечное значение для двух секунд до конца во время = 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
<a name="interpolationmethods"></a>   
## <a name="interpolation-methods"></a>Методы интерполяции  
 В предыдущих разделах упоминалось, что некоторые методы анимации по ключевым кадрам поддерживают несколько методов интерполяции. Метод интерполяции определяет, как должен выполняться переход от одного значения к другому во время анимации. Выбрав тип ключевого кадра, используемого при анимации, можно определить метод интерполяции для этого сегмента ключевого кадра. Существуют три метода интерполяции: линейная интерполяция, дискретная и интерполяция сплайнами.  
  
### <a name="linear-interpolation"></a>Линейная интерполяция  
 При линейной интерполяции переход выполняется с постоянной скоростью на протяжении сегмента. Например, если в сегменте ключевого кадра происходит переход от 0 до 10 в течение 5 секунд, выходные данные анимации будут принимать следующие значения в указанные моменты времени.  
  
|Время|Выходное значение|  
|----------|------------------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5|9|  
|5|10|  
  
### <a name="discrete-interpolation"></a>Дискретная интерполяция  
 При дискретной интерполяции функция анимации выполняет переходы от одного значения к другому без интерполяции. Если в сегменте ключевого кадра происходит переход от 0 до 10 в течение 5 секунд, выходные данные анимации будут принимать следующие значения в указанные моменты времени.  
  
|Время|Выходное значение|  
|----------|------------------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5|0|  
|5|10|  
  
 Обратите внимание на то, что выходное значение не изменяется до окончания длительности сегмента.  
  
 Интерполяция сплайнами более сложная. Она описана в следующем разделе.  
  
<a name="anim_spline"></a>   
### <a name="splined-interpolation"></a>Интерполяция сплайнами  
 Интерполяция сплайнами может использоваться для достижения более реалистичных временных эффектов. Так как анимация часто используется для имитации эффектов, возникающих в реальном мире, разработчикам могут потребоваться полный контроль над ускорением и замедлением объектов и точная манипуляция временными сегментами. Ключевые кадры-сплайны позволяют выполнять анимацию с интерполяцией сплайнами. С помощью других ключевых кадров, укажите <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> и <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>. С помощью опорных кадров сплайна, также следует указать <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>. В следующем примере показан один дискретным опорным кадром для <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. Обратите внимание <xref:System.Windows.Media.Animation.KeySpline> свойства; что делает дискретным опорным кадром отличается от других типов ключевых кадров.  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Кривая Безье третьего порядка определяется начальной точкой, конечной точкой и двумя контрольными точками. <xref:System.Windows.Media.Animation.KeySpline> Свойство дискретным опорным кадром определяет две контрольные точки кривой Безье, которая располагается между (0,0) и (1,1). Первая контрольная точка управляет коэффициентом кривизны первой половины кривой Безье, а вторая контрольная точка — коэффициентом кривизны второй половины сегмента. Полученная кривая описывает скорость изменения для этого ключевого кадра-сплайна. Чем круче кривая, тем быстрее ключевой кадр изменяет свои значения. Когда кривая становится более пологой, ключевой кадр медленнее изменяет свои значения.  
  
 Можно использовать <xref:System.Windows.Media.Animation.KeySpline> для имитации физических траекторий, таких как падают вода или прыгающий шарик, или применить другие «замедление» и «замедления» эффекты анимации. Для реализации эффектов взаимодействия с пользователем, таких как затухание фона или отпускание кнопки элемента управления, можно применять интерполяцию сплайнами, чтобы ускорить или замедлить скорость изменения при анимации конкретных движений.  
  
 В следующем примере задается <xref:System.Windows.Media.Animation.KeySpline> 0,1 1,0, которое создает следующую кривую Безье.  
  
 ![Кривая Безье](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm_keyspline_0_1_1_0")  
Ключевой сплайн с контрольными точками (0,0, 1,0) и (1,0, 0,0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Этот ключевой кадр вначале выполняет быстрое движение, затем замедляется и снова ускоряется перед завершением.  
  
 В следующем примере задается <xref:System.Windows.Media.Animation.KeySpline> из 0.75,1.0 0.5,0.25, который создает следующую кривую Безье.  
  
 ![Кривая Безье](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm_keyspline_025_050_075_10")  
Ключевой сплайн с контрольными точками (0,25, 0,5) и (0,75, 1,0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  
  
 Так как кривизна кривой Безье изменяется незначительно, этот ключевой кадр выполняет движение почти с постоянной скоростью, несколько замедляясь перед завершением.  
  
 В следующем примере используется <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> для анимации положения прямоугольника. Поскольку <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> использует <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> объектов переход между каждое значение ключевого кадра использует интерполяцию сплайнами.  
  
 [!code-xaml[keyframes_ovw_snippet#SplinedInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  
  
 Интерполяцию сплайнами не так просто понять. Попробуйте поэкспериментировать с различными параметрами. [Пример анимации по ключевым сплайнам](http://go.microsoft.com/fwlink/?LinkID=160011) позволяет, изменяя значения ключевого сплайна, просмотреть результат на анимации.  
  
<a name="combininginterpolationmethods"></a>   
### <a name="combining-interpolation-methods"></a>Комбинирование методов интерполяции  
 Можно использовать ключевые кадры с различными типами интерполяции в одной операции анимации. Если два ключевых кадра анимации с различными методами интерполяции следуют друг за другом, то для создания перехода от первого значения ко второму используется метод интерполяции второго ключевого кадра.  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> создается, использует линейную, сплайнами и дискретную интерполяцию.  
  
 [!code-xaml[keyframes_ovw_snippet#ComboInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]  
  
<a name="keytimes"></a>   
## <a name="more-about-duration-and-key-times"></a>Дополнительные сведения о длительности и временной шкале  
 Как и другие виды анимации, имеют кадрам <xref:System.Windows.Duration> свойство. Помимо указания анимации <xref:System.Windows.Duration>, необходимо указать, какая часть длительности предоставляется для каждого ключевого кадра. Это можно сделать с описанием <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> для каждого из ключевых кадров анимации. Каждый ключевой кадр <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> указывает окончания этого ключевого кадра.  
  
 <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> Свойство не указывает продолжительность воспроизведения ключевого времени. Продолжительность выполнения ключевого кадра определяется моментом окончания ключевого кадра, моментом окончания предыдущего ключевого кадра и длительностью анимации. Время может быть указан как значение времени, в процентах, или как специальные значения <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> или <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 Ниже описаны различные способы определения времени ключевого кадра.  
  
### <a name="timespan-values"></a>Значения временного диапазона  
 Вы можете использовать <xref:System.TimeSpan> значения с целью указания <xref:System.Windows.Media.Animation.KeyTime>. Значение должно быть больше или равно 0 и меньше или равно длительности анимации. В следующем примере показана анимация длительностью 10 секунд с четырьмя ключевыми кадрами, время которых указывается в виде значений времени.  
  
-   Первый ключевой кадр выполняет анимацию от базового значения до 100 в течение первых 3 секунд и заканчивает в момент времени = 0:0:03.  
  
-   Второй ключевой кадр выполняет анимацию от 100 до 200. Она запускается после окончания первого ключевого кадра (в момент времени 3 секунды), выполняется в течение 5 секунд и заканчивается в момент времени = 0:0:8.  
  
-   Третий ключевой кадр выполняет анимацию от 200 до 500. Она запускается после окончания второго ключевого кадра (в момент времени 8 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:9.  
  
-   Четвертый ключевой кадр выполняет анимацию от 500 до 600. Она запускается после окончания третьего ключевого кадра (в момент времени 9 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#TimeSpanKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#timespankeytimeexample)]  
  
### <a name="percentage-values"></a>Значения в процентах  
 Указывает процентное значение ключевого кадра, которое в некоторых процент анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A>. В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] значение в процентах указывается как число, за которым следует символ `%`. В коде используйте <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A> метод и передать его <xref:System.Double> в процентах. Значение должно быть больше или равно 0 и меньше или равно 100 %. В следующем примере показана анимация длительностью 10 секунд с четырьмя ключевыми кадрами, время которых указывается в виде значений в процентах.  
  
-   Первый ключевой кадр выполняет анимацию от базового значения до 100 в течение первых 3 секунд и заканчивает в момент времени = 0:0:3.  
  
-   Второй ключевой кадр выполняет анимацию от 100 до 200. Она запускается после окончания первого ключевого кадра (в момент времени 3 секунды), выполняется в течение 5 секунд и заканчивается в момент времени = 0:0:8 (0,8 * 10 = 8).  
  
-   Третий ключевой кадр выполняет анимацию от 200 до 500. Она запускается после окончания второго ключевого кадра (в момент времени 8 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:9 (0,9 * 10 = 9).  
  
-   Четвертый ключевой кадр выполняет анимацию от 500 до 600. Она запускается после окончания третьего ключевого кадра (в момент времени 9 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:10 (1 * 10 = 10).  
  
 [!code-xaml[keyframes_ovw_snippet#PercentageKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#percentagekeytimeexample)]  
  
### <a name="special-value-uniform"></a>Специальное значение, равномерный метод  
 Используйте <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> времени при необходимости каждого ключевого кадра, чтобы воспользоваться одинаковое количество времени.  
  
 Объект <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> делит доступное время столь же число ключевых кадров для определения времени окончания каждого ключевого кадра. В следующем примере показано анимации длительностью 10 секунд и четыре ключевых кадров, время задаются в виде <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>.  
  
-   Первый ключевой кадр выполняет анимацию от базового значения до 100 в течение первых 2,5 секунды и заканчивает в момент времени = 0:0:2,5.  
  
-   Второй ключевой кадр выполняет анимацию от 100 до 200. Она запускается после окончания первого ключевого кадра (в момент времени 2,5 секунды), выполняется в течение примерно 2,5 секунды и заканчивается в момент времени = 0:0:5.  
  
-   Третий ключевой кадр выполняет анимацию от 200 до 500. Она запускается после окончания второго ключевого кадра (в момент времени 5 секунд), выполняется в течение 2,5 секунды и заканчивается в момент времени = 0:0:7,5.  
  
-   Четвертый ключевой кадр выполняет анимацию от 500 до 600. Она запускается после окончания второго ключевого кадра (в момент времени 7,5 секунды), выполняется в течение 2,5 секунд и заканчивается в момент времени = 0:0:1.  
  
 [!code-xaml[keyframes_ovw_snippet#UniformKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#uniformkeytimeexample)]  
  
### <a name="special-value-paced"></a>Определенное значение, пошаговый метод  
 Используйте <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> определяет время, когда необходимо анимировать с постоянной скоростью.  
  
 Объект <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> ключевой столбец времени выделяет доступное время в соответствии с длина каждого из ключевых кадров для определения длительности каждого кадра.  Это приводит к тому, что скорость или темп анимации остается постоянной.  В следующем примере показано анимации длительностью 10 секунд и три ключевых кадров, время задаются в виде <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 [!code-xaml[keyframes_ovw_snippet#PacedKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#pacedkeytimeexample)]  
  
 Обратите внимание, что, если последний ключевой кадр ключевой столбец времени <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> или <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>, его полное время будет равным 100 процентов. Если первый ключевой кадр в многокадровой анимации является пошаговым, его расчетное время будет задано в размере 0. (Если коллекция ключевых кадров содержит только один кадр и этот кадр пошаговый, его расчетное время будет задано в размере 100 %.)  
  
 Разные ключевые кадры в однокадровой анимации могут использовать разные типы времени кадра.  
  
<a name="combiningkeytimes"></a>   
## <a name="combining-key-times-out-of-order-key-frames"></a>Объединение времени ключевых кадров, неупорядоченные ключевые кадры  
 Можно использовать полные кадры с различными <xref:System.Windows.Media.Animation.KeyTime> типы значений в той же анимации. И хотя рекомендуется добавлять ключевые кадры в том порядке, в каком они должны выполняться, в этом нет необходимости. Система выполнения анимации и расчета времени способна обрабатывать неупорядоченные ключевые кадры. Ключевые кадры с недопустимым временем игнорируются.  
  
 Ниже приводятся процедуры, с помощью которых рассчитывается время кадра при анимации по ключевым кадрам.  
  
1.  Разрешить <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> значения.  
  
2.  Определение *общего времени интерполяции* анимации (общего времени, необходимого для выполнения прямой итерации при анимации по ключевым кадрам).  
  
    1.  Если анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A> не <xref:System.Windows.Duration.Automatic%2A> или <xref:System.Windows.Duration.Forever%2A>, общее время интерполяции является значение анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство.  
  
    2.  В противном случае — самое большое общее время интерполяции <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> значение между кадрами, если они существуют.  
  
    3.  В остальных случаях общее время интерполяции равно 1 секунде.  
  
3.  Использование значения времени интерполяции для устранения <xref:System.Windows.Media.Animation.KeyTimeType.Percent> <xref:System.Windows.Media.Animation.KeyTime> значения.  
  
4.  Расчет времени последнего кадра в случае, если оно не было рассчитано на предыдущих шагах. Если <xref:System.Windows.Media.Animation.KeyTime> последней ключевой кадр — <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> или <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, его определенное время будет совпадать с общим временем интерполяции.  
  
     Если <xref:System.Windows.Media.Animation.KeyTime> первого кадра является <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> и анимации имеет более чем на ключевых кадров, устраните ее <xref:System.Windows.Media.Animation.KeyTime> значение равно нулю; в том случае, если имеется только один опорного кадра и его <xref:System.Windows.Media.Animation.KeyTime> значение <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, он разрешен в общую сумму время интерполяции, как описано в предыдущем шаге.  
  
5.  Определите оставшиеся <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> значения: каждое из них получает равную долю доступного времени.  Во время этого процесса неразрешенных <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> временно значения рассматриваются как <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> значения и получают временно определенное время.  
  
6.  Разрешить <xref:System.Windows.Media.Animation.KeyTime> значения ключевых кадров с неопределенным полным временем с помощью ключевых кадров, объявленных рядом с ними, которые были устранены <xref:System.Windows.Media.Animation.KeyTime> значения.  
  
7.  Определите оставшиеся <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> значения. <xref:System.Windows.Media.Animation.KeyTime.Paced%2A><xref:System.Windows.Media.Animation.KeyTime> использовать <xref:System.Windows.Media.Animation.KeyTime> значений соседних полных кадров, чтобы определить их определенное время.  Цель — убедиться, что скорость анимации является постоянной в течение расчетного времени этого ключевого кадра.  
  
8.  Отсортируйте полные кадры в порядке определенного времени (первичный ключ) и в порядке объявления (вторичный ключ), т. е., используйте строгую сортировку на основании полных кадров <xref:System.Windows.Media.Animation.KeyTime> значения.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.KeyTime>  
 <xref:System.Windows.Media.Animation.KeySpline>  
 <xref:System.Windows.Media.Animation.Timeline>  
 [Пример анимации Ключевой сплайн](http://go.microsoft.com/fwlink/?LinkID=160011)  
 [Пример ключевой кадр анимации](http://go.microsoft.com/fwlink/?LinkID=160012)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)  
 [Общие сведения о характере поведения во времени](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
