---
title: Общие сведения об анимации по ключевым кадрам
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], key-frame
- key frames [WPF], about key-frame animations
- multiple animation target values [WPF]
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
ms.openlocfilehash: be815ca522cf18ea2403ea7af5549ceaf922854e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186684"
---
# <a name="key-frame-animations-overview"></a>Общие сведения об анимации по ключевым кадрам
В этом разделе рассказывается об анимации по ключевым кадрам. Методика анимации по ключевым кадрам позволяет использовать более двух целевых значений и контролировать применяемый метод интерполяции.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания предлагаемого материала необходимо знакомство с принципами анимации [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и понятием временной шкалы. Общие сведения об анимации см. в разделе [Общие сведения об анимации](animation-overview.md). Также полезно иметь знания по анимации From/To/By. Дополнительные сведения см. в разделе "Общие сведения об анимации From/To/By".  
  
<a name="whatisakeyframeanimation"></a>
## <a name="what-is-a-key-frame-animation"></a>Что такое анимации по ключевым кадрам?  
 Так же как при анимации From/To/By при анимации по ключевым кадрам выполняется анимация значения целевого свойства. Оно создает переход между своими <xref:System.Windows.Media.Animation.Timeline.Duration%2A>значениями цели над своим . Но в отличие от анимации From/To/By, при которой создается переход между двумя значениями, при анимации по ключевым кадрам можно создавать переходы между любым числом целевых значений за один раз. В анимации по ключевым кадрам не используются свойства From, To и By для задания целевых значений. Целевые значения для анимации по ключевым кадрам описываются с помощью объектов ключевых кадров (отсюда термин — "анимация по ключевым кадрам"). Чтобы указать целевые значения анимации, необходимо создать объекты ключевых <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> кадров и добавить их в коллекцию анимации. При выполнении анимации создаются переходы между заданными кадрами.  
  
 Кроме того, что при анимации по ключевым кадрам поддерживается обработка нескольких целевых значений, некоторые методы анимации по ключевым кадрам поддерживают использование нескольких методов интерполяции. Метод интерполяции анимации определяет, как выполняется переход от одного значения к другому. Существует три типа интерполяции: дискретная, линейная и интерполяция сплайнами.  
  
 Чтобы выполнить анимацию по ключевым кадрам, сделайте следующее.  
  
- Объявить анимацию <xref:System.Windows.Media.Animation.Timeline.Duration%2A>и указать его , так же, как вы бы для от / / анимации.  
  
- Для каждого целевого значения создайте ключевой кадр соответствующего <xref:System.Windows.Media.Animation.KeyTime>типа, установите его <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> значение и добавьте его в коллекцию анимации.  
  
- Свяжите анимацию со свойством так же как при анимации From/To/By. Дополнительные сведения о применении анимации к свойству с помощью раскадровки см. в разделе [Общие сведения о раскадровке](storyboards-overview.md).  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> используется для <xref:System.Windows.Shapes.Rectangle> анимировать элемент в четырех разных местах.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
 Как и анимация From/To/By, анимация с ключевым кадром <xref:System.Windows.Media.Animation.Storyboard> может быть применена к <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> свойству с помощью разметки и кода или с помощью метода в коде. Вы также можете использовать анимацию в <xref:System.Windows.Media.Animation.AnimationClock> кадре ключей для создания и применения ее к одному или несколько свойствам. Дополнительные сведения о различных способах применения анимации см. в разделе [Общие сведения о методах анимации свойств](property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>
## <a name="key-frame-animation-types"></a>Типы анимации по ключевым кадрам  
 Так как при анимации создаются значения свойств, существуют различные типы анимаций для различных типов свойств. Чтобы оживить <xref:System.Double> свойство, которое принимает (например, свойство элемента), <xref:System.Double> <xref:System.Windows.FrameworkElement.Width%2A> вы используете анимацию, которая производит значения. Чтобы оживить <xref:System.Windows.Point>свойство, которое занимает, вы <xref:System.Windows.Point> используете анимацию, которая производит значения, и так далее.  
  
 Классы анимации в ключевых кадрах относятся к пространству <xref:System.Windows.Media.Animation> имен и придерживаются следующей конвенции имен:  
  
 * \<Тип>*`AnimationUsingKeyFrames`  
  
 Где * \<тип>* — это тип значения, который оживляет класс.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет следующие классы анимации по ключевым кадрам.  
  
|Тип свойства|Соответствующий класс анимации From/To/By|Поддерживаемые методы интерполяции|  
|-------------------|------------------------------------------------|-------------------------------------|  
|<xref:System.Boolean>|<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>|Discrete|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16AnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32AnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64AnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>|Discrete|  
|<xref:System.Object>|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>|Discrete|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.String>|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Discrete|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimationUsingKeyFrames>|Дискретная, линейная, сплайнами|  
  
<a name="animation_target_values"></a>
## <a name="target-values-key-frames-and-key-times"></a>Целевые значения (ключевые кадры) и временная шкала  
 Для анимации различных типов свойств существуют различные типы анимации по ключевым кадрам и, соответственно, различные типы объектов ключевых кадров — по одному для каждого типа анимированного значения и поддерживаемого метода интерполяции. Типы ключевых кадров удовлетворяют требованиям следующего соглашения об именах.  
  
 *ИнтерполяцияМетод>\<тип>\<*`KeyFrame`  
  
 В тех случаях, * \<когда ИнтерполяцияМетод>* методом интерполяции, используемым ключевым кадром, и * \<типом>* является тип значения, который оживляет класс. Метод анимации по ключевым кадрам, поддерживающий все три метода интерполяции, будет включать в себя три типа ключевых кадров, которые можно использовать. Например, можно использовать три ключевых <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>типа <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>кадра с :, и <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>. (Методы интерполяции подробно описаны в следующем разделе.)  
  
 Основная цель ключевой кадра заключается <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>в указании a <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> и a . Все типы ключевых кадров предоставляют эти два свойства.  
  
- Свойство <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> определяет целевое значение для этого ключевого кадра.  
  
- Свойство <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> определяет, когда (в пределах <xref:System.Windows.Media.Animation.Timeline.Duration%2A>анимации) ключ <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> кадра достигается.  
  
 Когда начинается анимация ключевой кадра, итерируется через <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> его ключевые кадры в порядке, определяемом их свойствами.  
  
- Если в момент 0 нет ключевого элемента, анимация создает переход между <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> текущим значением целевого свойства и первым ключевым кадром; в противном случае выходное значение анимации становится значением первого ключевого кадра.  
  
- Анимация создает переход <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> между первым и вторым ключевыми кадрами с помощью метода интерполяции, указанного вторым ключевым кадром. Переход начинается в первом ключевом кадре <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> и заканчивается, когда второй ключевой <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> кадр достигается.  
  
- Анимация продолжается, создавая переходы от каждого предыдущего ключевого кадра к последующему.  
  
- Наконец, анимация переходит к значению ключевого кадра <xref:System.Windows.Media.Animation.Timeline.Duration%2A>с наибольшим ключевым временем, равным или меньше, чем анимация.  
  
 Если анимация <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Duration.Automatic%2A> равна <xref:System.Windows.Media.Animation.Timeline.Duration%2A> времени последнего ключевого кадра, анимация заканчивается. В противном случае, <xref:System.Windows.Duration> если анимация больше, чем ключевое время последнего ключевого кадра, <xref:System.Windows.Duration>анимация удерживает значение ключевой кадра, пока не достигнет конца. Как и все анимации, анимация <xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> с ключевым кадром использует свое свойство, чтобы определить, сохраняет ли она окончательное значение, когда достигает конца своего активного периода. Дополнительные сведения см. в разделе [Общие сведения о характере поведения во времени](timing-behaviors-overview.md).  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> используется объект, определенный <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> в <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> предыдущем примере, чтобы продемонстрировать, как работают и как работают свойства.  
  
- Первый кадр немедленно устанавливает выходное значение анимации равное 0.  
  
- Второй ключевой кадр выполняет анимацию от 0 до 350. Она запускается после окончания первого ключевого кадра (в момент времени 0 секунд), выполняется в течение 2 секунд и заканчивается в момент времени = 0:0:2.  
  
- Третий ключевой кадр выполняет анимацию от 350 до 50. Она запускается после окончания второго ключевого кадра (в момент времени 2 секунды), выполняется в течение 5 секунд и заканчивается в момент времени = 0:0:7.  
  
- Четвертый ключевой кадр выполняет анимацию от 50 до 200. Она запускается после окончания третьего ключевого кадра (в момент времени 7 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:8.  
  
- Поскольку <xref:System.Windows.Media.Animation.Timeline.Duration%2A> свойство анимации было установлено на 10 секунд, анимация удерживает свое окончательное значение в течение двух секунд, прежде чем закончиться во время 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#BasicKeyFrameExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  
  
<a name="interpolationmethods"></a>
## <a name="interpolation-methods"></a>Методы интерполяции  
 В предыдущих разделах упоминалось, что некоторые методы анимации по ключевым кадрам поддерживают несколько методов интерполяции. Метод интерполяции определяет, как должен выполняться переход от одного значения к другому во время анимации. Выбрав тип ключевого кадра, используемого при анимации, можно определить метод интерполяции для этого сегмента ключевого кадра. Существуют три метода интерполяции: линейная интерполяция, дискретная и интерполяция сплайнами.  
  
### <a name="linear-interpolation"></a>Линейная интерполяция  
 При линейной интерполяции переход выполняется с постоянной скоростью на протяжении сегмента. Например, если в сегменте ключевого кадра происходит переход от 0 до 10 в течение 5 секунд, выходные данные анимации будут принимать следующие значения в указанные моменты времени.  
  
|Time|Выходное значение|  
|----------|------------------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5.|9|  
|5|10|  
  
### <a name="discrete-interpolation"></a>Дискретная интерполяция  
 При дискретной интерполяции функция анимации выполняет переходы от одного значения к другому без интерполяции. Если в сегменте ключевого кадра происходит переход от 0 до 10 в течение 5 секунд, выходные данные анимации будут принимать следующие значения в указанные моменты времени.  
  
|Time|Выходное значение|  
|----------|------------------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5.|0|  
|5|10|  
  
 Обратите внимание на то, что выходное значение не изменяется до окончания длительности сегмента.  
  
 Интерполяция сплайнами более сложная. Она описана в следующем разделе.  
  
<a name="anim_spline"></a>
### <a name="splined-interpolation"></a>Интерполяция сплайнами  
 Интерполяция сплайнами может использоваться для достижения более реалистичных временных эффектов. Так как анимация часто используется для имитации эффектов, возникающих в реальном мире, разработчикам могут потребоваться полный контроль над ускорением и замедлением объектов и точная манипуляция временными сегментами. Ключевые кадры-сплайны позволяют выполнять анимацию с интерполяцией сплайнами. С другими ключевыми кадрами вы указываете a <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> и <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>. С помощью сплайс-ключа <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>также указано. В следующем примере показан афера <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>с одним ключом сплайна для . Обратите <xref:System.Windows.Media.Animation.KeySpline> внимание на свойство; это то, что делает сплайн ключевых кадров отличается от других типов ключевых кадров.  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Кривая Безье третьего порядка определяется начальной точкой, конечной точкой и двумя контрольными точками. Свойство <xref:System.Windows.Media.Animation.KeySpline> сплайна ключевой кадр аопределяет две точки управления кривой Безье, которая простирается от (0,0) до (1,1). Первая контрольная точка управляет коэффициентом кривизны первой половины кривой Безье, а вторая контрольная точка — коэффициентом кривизны второй половины сегмента. Полученная кривая описывает скорость изменения для этого ключевого кадра-сплайна. Чем круче кривая, тем быстрее ключевой кадр изменяет свои значения. Когда кривая становится более пологой, ключевой кадр медленнее изменяет свои значения.  
  
 Вы можете <xref:System.Windows.Media.Animation.KeySpline> использовать для имитации физических траекторий, таких как падающая вода или подпрыгивая шары, или применять другие эффекты "легкость" и "легкость" для анимации движения. Для реализации эффектов взаимодействия с пользователем, таких как затухание фона или отпускание кнопки элемента управления, можно применять интерполяцию сплайнами, чтобы ускорить или замедлить скорость изменения при анимации конкретных движений.  
  
 Следующий пример указывает <xref:System.Windows.Media.Animation.KeySpline> 0,1 1,0, что создает следующую кривую Безье.  
  
 ![Кривая Безье](./media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm_keyspline_0_1_1_0")  
Ключевой сплайн с контрольными точками (0,0, 1,0) и (1,0, 0,0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  
  
 Этот ключевой кадр вначале выполняет быстрое движение, затем замедляется и снова ускоряется перед завершением.  
  
 Следующий пример указывает <xref:System.Windows.Media.Animation.KeySpline> на 0.5,0.25 0.75,1.0, что создает следующую кривую Безье.  
  
 ![Кривая Безье](./media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm_keyspline_025_050_075_10")  
Ключевой сплайн с контрольными точками (0,25, 0,5) и (0,75, 1,0)  
  
 [!code-xaml[keyframes_ovw_snippet#SingleSplineKeyFrameExampleInline3](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  
  
 Так как кривизна кривой Безье изменяется незначительно, этот ключевой кадр выполняет движение почти с постоянной скоростью, несколько замедляясь перед завершением.  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> используется для анимировать положение прямоугольника. Поскольку <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> объекты используются, переход между значением каждого ключевого кадра использует спутанное интерполяции.  
  
 [!code-xaml[keyframes_ovw_snippet#SplinedInterpolationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  
  
 Интерполяцию сплайнами не так просто понять. Попробуйте поэкспериментировать с различными параметрами. [Пример анимации по ключевым сплайнам](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/KeySplineAnimations) позволяет, изменяя значения ключевого сплайна, просмотреть результат на анимации.  
  
<a name="combininginterpolationmethods"></a>
### <a name="combining-interpolation-methods"></a>Комбинирование методов интерполяции  
 Можно использовать ключевые кадры с различными типами интерполяции в одной операции анимации. Если два ключевых кадра анимации с различными методами интерполяции следуют друг за другом, то для создания перехода от первого значения ко второму используется метод интерполяции второго ключевого кадра.  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> создается линейная, скрытая и дискретная интерполяция.  
  
 [!code-xaml[keyframes_ovw_snippet#ComboInterpolationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]  
  
<a name="keytimes"></a>
## <a name="more-about-duration-and-key-times"></a>Дополнительные сведения о длительности и временной шкале  
 Как и другие анимации, анимация ключей-кадров имеет свойство. <xref:System.Windows.Duration> В дополнение к указанию <xref:System.Windows.Duration>анимации, необходимо указать, какая часть этой продолжительности дается каждому ключевому кадру. Вы делаете это, <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> описывая для каждого из ключевых кадров анимации. Каждый ключевой <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> кадр определяет, когда заканчивается эта ключевая рамка.  
  
 Свойство <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> не указывает, как долго играет ключевое время. Продолжительность выполнения ключевого кадра определяется моментом окончания ключевого кадра, моментом окончания предыдущего ключевого кадра и длительностью анимации. Ключевые времена могут быть указаны как значение времени, <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> процент, или как специальные значения или <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 Ниже описаны различные способы определения времени ключевого кадра.  
  
### <a name="timespan-values"></a>Значения временного диапазона  
 Вы можете <xref:System.TimeSpan> использовать значения <xref:System.Windows.Media.Animation.KeyTime>для указания . Значение должно быть больше или равно 0 и меньше или равно длительности анимации. В следующем примере показана анимация длительностью 10 секунд с четырьмя ключевыми кадрами, время которых указывается в виде значений времени.  
  
- Первый ключевой кадр выполняет анимацию от базового значения до 100 в течение первых 3 секунд и заканчивает в момент времени = 0:0:03.  
  
- Второй ключевой кадр выполняет анимацию от 100 до 200. Она запускается после окончания первого ключевого кадра (в момент времени 3 секунды), выполняется в течение 5 секунд и заканчивается в момент времени = 0:0:8.  
  
- Третий ключевой кадр выполняет анимацию от 200 до 500. Она запускается после окончания второго ключевого кадра (в момент времени 8 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:9.  
  
- Четвертый ключевой кадр выполняет анимацию от 500 до 600. Она запускается после окончания третьего ключевого кадра (в момент времени 9 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:10.  
  
 [!code-xaml[keyframes_ovw_snippet#TimeSpanKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#timespankeytimeexample)]  
  
### <a name="percentage-values"></a>Значения в процентах  
 Процентное значение указывает на то, что ключевой кадр заканчивается на какой-то процент от анимации. <xref:System.Windows.Media.Animation.Timeline.Duration%2A> В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] значение в процентах указывается как число, за которым следует символ `%`. В коде <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A> используется метод и <xref:System.Double> передаете его с указанием процента. Значение должно быть больше или равно 0 и меньше или равно 100 %. В следующем примере показана анимация длительностью 10 секунд с четырьмя ключевыми кадрами, время которых указывается в виде значений в процентах.  
  
- Первый ключевой кадр выполняет анимацию от базового значения до 100 в течение первых 3 секунд и заканчивает в момент времени = 0:0:3.  
  
- Второй ключевой кадр выполняет анимацию от 100 до 200. Она запускается после окончания первого ключевого кадра (в момент времени 3 секунды), выполняется в течение 5 секунд и заканчивается в момент времени = 0:0:8 (0,8 * 10 = 8).  
  
- Третий ключевой кадр выполняет анимацию от 200 до 500. Она запускается после окончания второго ключевого кадра (в момент времени 8 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:9 (0,9 * 10 = 9).  
  
- Четвертый ключевой кадр выполняет анимацию от 500 до 600. Она запускается после окончания третьего ключевого кадра (в момент времени 9 секунд), выполняется в течение 1 секунды и заканчивается в момент времени = 0:0:10 (1 * 10 = 10).  
  
 [!code-xaml[keyframes_ovw_snippet#PercentageKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#percentagekeytimeexample)]  
  
### <a name="special-value-uniform"></a>Специальное значение, равномерный метод  
 Используйте время, <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> когда вы хотите, чтобы каждый ключевой кадр занимает одинаковое количество времени.  
  
 Ключевое <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> время делит имеющееся время поровну на количество ключевых кадров для определения времени окончания каждого ключевого кадра. В следующем примере показана анимация продолжительностью 10 секунд и четырьмя ключевыми кадрами, ключевые времена которых указаны как. <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>  
  
- Первый ключевой кадр выполняет анимацию от базового значения до 100 в течение первых 2,5 секунды и заканчивает в момент времени = 0:0:2,5.  
  
- Второй ключевой кадр выполняет анимацию от 100 до 200. Она запускается после окончания первого ключевого кадра (в момент времени 2,5 секунды), выполняется в течение примерно 2,5 секунды и заканчивается в момент времени = 0:0:5.  
  
- Третий ключевой кадр выполняет анимацию от 200 до 500. Она запускается после окончания второго ключевого кадра (в момент времени 5 секунд), выполняется в течение 2,5 секунды и заканчивается в момент времени = 0:0:7,5.  
  
- Четвертый ключевой кадр выполняет анимацию от 500 до 600. Она запускается после окончания второго ключевого кадра (в момент времени 7,5 секунды), выполняется в течение 2,5 секунд и заканчивается в момент времени = 0:0:1.  
  
 [!code-xaml[keyframes_ovw_snippet#UniformKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#uniformkeytimeexample)]  
  
### <a name="special-value-paced"></a>Определенное значение, пошаговый метод  
 Используйте <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> время, когда вы хотите, чтобы оживить с постоянной скоростью.  
  
 Ключевое <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> время выделяет имеющееся время в зависимости от длины каждого из ключевых кадров для определения продолжительности каждого кадра.  Это приводит к тому, что скорость или темп анимации остается постоянной.  В следующем примере показана анимация продолжительностью 10 секунд и тремя <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>ключевыми кадрами, ключевые времена которых указаны как.  
  
 [!code-xaml[keyframes_ovw_snippet#PacedKeyTimeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snippet/CS/KeyTimesExample.xaml#pacedkeytimeexample)]  
  
 Обратите внимание, что, если ключевое <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> время <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>последнего ключевого кадра или, его разрешенное ключевое время будет установлено на 100 процентов. Если первый ключевой кадр в многокадровой анимации является пошаговым, его расчетное время будет задано в размере 0. (Если коллекция ключевых кадров содержит только один кадр и этот кадр пошаговый, его расчетное время будет задано в размере 100 %.)  
  
 Разные ключевые кадры в однокадровой анимации могут использовать разные типы времени кадра.  
  
<a name="combiningkeytimes"></a>
## <a name="combining-key-times-out-of-order-key-frames"></a>Объединение времени ключевых кадров, неупорядоченные ключевые кадры  
 В одной и той <xref:System.Windows.Media.Animation.KeyTime> же анимации можно использовать ключевые кадры с различными типами значений. И хотя рекомендуется добавлять ключевые кадры в том порядке, в каком они должны выполняться, в этом нет необходимости. Система выполнения анимации и расчета времени способна обрабатывать неупорядоченные ключевые кадры. Ключевые кадры с недопустимым временем игнорируются.  
  
 Ниже приводятся процедуры, с помощью которых рассчитывается время кадра при анимации по ключевым кадрам.  
  
1. Разрешите <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> значения.  
  
2. Определение *общего времени интерполяции* анимации (общего времени, необходимого для выполнения прямой итерации при анимации по ключевым кадрам).  
  
    1. Если <xref:System.Windows.Media.Animation.Timeline.Duration%2A> анимация <xref:System.Windows.Duration.Automatic%2A> не является <xref:System.Windows.Duration.Forever%2A>или, общее время интерполяции является <xref:System.Windows.Media.Animation.Timeline.Duration%2A> значение свойства анимации.  
  
    2. В противном случае общее время <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime> интерполяции является самым большим значением, указанным среди его ключевых кадров, если таковые имеются.  
  
    3. В остальных случаях общее время интерполяции равно 1 секунде.  
  
3. Используйте общее значение времени <xref:System.Windows.Media.Animation.KeyTimeType.Percent> <xref:System.Windows.Media.Animation.KeyTime> интерполяции для решения значений.  
  
4. Расчет времени последнего кадра в случае, если оно не было рассчитано на предыдущих шагах. Если <xref:System.Windows.Media.Animation.KeyTime> последний ключевой <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> кадр <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>или, его разрешенное время будет равно общему времени интерполяции.  
  
     Если <xref:System.Windows.Media.Animation.KeyTime> первый ключевой <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> кадр есть и эта анимация имеет <xref:System.Windows.Media.Animation.KeyTime> больше, чем на ключевых кадрах, разрешите его значение к нулю; если есть только один ключевой кадр и его <xref:System.Windows.Media.Animation.KeyTime> значение, <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>он решается на общее время интерполяции, как описано в предыдущем этапе.  
  
5. Решите <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> оставшиеся значения: каждому из них предоставляется равная доля имеющегося времени.  Во время этого <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> процесса нерешенные значения <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> временно рассматриваются как значения и получают временное время.  
  
6. Разрешите <xref:System.Windows.Media.Animation.KeyTime> значения ключевых кадров с неопределенными ключевыми временами, используя <xref:System.Windows.Media.Animation.KeyTime> ключевые кадры, объявленные ближайшими к ним, которые разрешили значения.  
  
7. Разрешите оставшиеся <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> значения. <xref:System.Windows.Media.Animation.KeyTime.Paced%2A><xref:System.Windows.Media.Animation.KeyTime> использовать <xref:System.Windows.Media.Animation.KeyTime> значения соседних ключевых кадров для определения их разрешенного времени.  Цель — убедиться, что скорость анимации является постоянной в течение расчетного времени этого ключевого кадра.  
  
8. Сортируйте ключевые кадры в порядке разрешенного времени (основной ключ) и порядке декларирования (вторичный ключ), т.е. используйте стабильный сорт, основанный на разрешенных значениях ключевой кадра. <xref:System.Windows.Media.Animation.KeyTime>  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Animation.KeyTime>
- <xref:System.Windows.Media.Animation.KeySpline>
- <xref:System.Windows.Media.Animation.Timeline>
- [Пример анимации по ключевым кадрами сплайнами](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/KeySplineAnimations)
- [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о раскадровке](storyboards-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
- [Общие сведения о характере поведения во времени](timing-behaviors-overview.md)
