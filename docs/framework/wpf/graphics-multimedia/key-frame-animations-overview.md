---
title: "Общие сведения об анимации по ключевым кадрам | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "анимация, ключевой кадр"
  - "ключевые кадры [WPF], сведения об анимации по ключевым кадрам"
  - "несколько целевых значений анимации"
ms.assetid: 10028f97-bb63-41fc-b8ad-663dac7ea203
caps.latest.revision: 29
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# Общие сведения об анимации по ключевым кадрам
Этот раздел посвящен анимации по полным кадрам.  Анимация по полным кадрам позволяет создавать анимацию с использованием более чем двух заданных значений и метода интерполяции.  
  
 В этом разделе содержатся следующие подразделы.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
-   [Предварительные требования](#prerequisites)  
  
-   [Использование анимации по полным кадрам](#keyframeanimations)  
  
-   [Связанные разделы](#seeAlsoToggle)  
  
<a name="prerequisites"></a>   
## Предварительные требования  
 Чтобы понять лучше этот руководство, необходимо ознакомиться с анимацией [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] и шкалами времени.  Общие сведения об анимации см. в разделе [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md). Там же можно ознакомиться с анимацией From\/To\/By.  Дополнительные сведения см. в разделе [Общие сведения об анимациях From\/To\/By](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md).  
  
<a name="whatisakeyframeanimation"></a>   
## Что такое анимация по полным кадрам?  
 Подобно анимации From\/To\/By, анимация по полным кадрам анимирует значение заданного свойства.  Она создает переход между заданными значениями во время его <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  Однако если анимация From\/To\/By создает переход между двумя значениями, то анимация по полным кадрам может создавать переходы между любым числом целевых значений.  В отличие от анимации From\/To\/By, анимация по полным кадрам не содержит свойств From,To или By, с которыми требуется задать ее заданные значения.  Анимация по полным кадрам задает значения, которые описаны с помощью объектов полных кадров \(поэтому и используется термин "анимация по полным кадрам"\).  Чтобы задать целевые значения анимации, создайте объекты полных кадров и добавьте их в коллекцию элементов анимации <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A>.  При запуске анимации она выполняет переход между указанными кадрами.  
  
 В дополнение к поддержке нескольких целевых значений, некоторые методы полных кадров поддерживают даже несколько методов интерполяции.  Метод интерполяции анимации определяет, как она переходит от одного значения к следующему.  Существуют три типа интерполяции: [дискретная](GTMT), [линейная](GTMT) и [сплайновая](GTMT).  
  
 Чтобы создать анимацию по полным кадрам, выполните следующие действия.  
  
-   Объявите анимацию и задайте ее <xref:System.Windows.Media.Animation.Timeline.Duration%2A>, так же как для анимации from\/to\/by.  
  
-   Для каждого значения создайте полный кадр соответствующего типа, задайте его значение и <xref:System.Windows.Media.Animation.KeyTime> и добавьте в коллекцию <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames.KeyFrames%2A> анимации.  
  
-   Свяжите анимацию со свойством так же, как в анимации From\/To\/By.  Дополнительные сведения о применении анимации к свойству с помощью раскадровки см. в разделе [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> используется для анимации элемента <xref:System.Windows.Shapes.Rectangle> в четырех разных местах.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->  
  
 Подобно анимации From\/To\/By, анимация по полным кадрам может применяться к свойству с помощью <xref:System.Windows.Media.Animation.Storyboard> в разметке и коде или с помощью метода <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> в коде.  Также можно использовать анимацию по полным кадрам, чтобы создать <xref:System.Windows.Media.Animation.AnimationClock> и применить его к одному или нескольким свойствам.  Дополнительные сведения о различных способах применения анимации см. в разделе [Общие сведения о методах анимации свойств](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md).  
  
<a name="animation_types"></a>   
## Типы анимации по полным кадрам  
 Поскольку анимация создает значения свойств, для различных типов свойств существуют различные типы анимации.  Для анимации свойства, которое принимает <xref:System.Double> \(как, например, свойство <xref:System.Windows.FrameworkElement.Width%2A> элемента\), используйте анимацию, создающую значения <xref:System.Double>.  Для анимации свойства, которое принимает <xref:System.Windows.Point>, используйте анимацию, создающую значения <xref:System.Windows.Point> и т.д.  
  
 Классы анимации по полным кадрам принадлежат к пространству имен <xref:System.Windows.Media.Animation> и соответствуют следующему соглашению об именах:  
  
 *\<Тип\>* `AnimationUsingKeyFrames`  
  
 *\<Тип\>* ― тип значения, для которого класс выполняет анимацию.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет следующие классы анимации по полным кадрам.  
  
|Тип свойства|Соответствующий класс анимации from\/to\/by|Поддерживаемые методы интерполяции|  
|------------------|-------------------------------------------------|----------------------------------------|  
|<xref:System.Boolean>|<xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>|Дискретный|  
|<xref:System.Byte>|<xref:System.Windows.Media.Animation.ByteAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Windows.Media.Color>|<xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Decimal>|<xref:System.Windows.Media.Animation.DecimalAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Double>|<xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Int16>|<xref:System.Windows.Media.Animation.Int16AnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Int32>|<xref:System.Windows.Media.Animation.Int32AnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Int64>|<xref:System.Windows.Media.Animation.Int64AnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Windows.Media.Matrix>|<xref:System.Windows.Media.Animation.MatrixAnimationUsingKeyFrames>|Дискретный|  
|<xref:System.Object>|<xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>|Дискретный|  
|<xref:System.Windows.Point>|<xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Windows.Media.Media3D.Quaternion>|<xref:System.Windows.Media.Animation.QuaternionAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Windows.Rect>|<xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Windows.Media.Media3D.Rotation3D>|<xref:System.Windows.Media.Animation.Rotation3DAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Single>|<xref:System.Windows.Media.Animation.SingleAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.String>|<xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>|Дискретный|  
|<xref:System.Windows.Size>|<xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Windows.Thickness>|<xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Windows.Media.Media3D.Vector3D>|<xref:System.Windows.Media.Animation.Vector3DAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
|<xref:System.Windows.Vector>|<xref:System.Windows.Media.Animation.VectorAnimationUsingKeyFrames>|Дискретный, линейный, сплайновый|  
  
<a name="animation_target_values"></a>   
## Заданные значения \(полные кадры\) и время полных кадров  
 Как существуют различные типы анимации по полным кадрам для анимации различных типов свойств, существуют и различные типы объектов полных кадров: один для каждого типа анимированного значения и поддерживаемого метода интерполяции.  Типы полных кадров соответствуют следующему соглашению об именах:  
  
 *\<InterpolationMethod\>\<Тип\>* `KeyFrame`  
  
 Где *\<InterpolationMethod\>* — метод интерполяции, который использует полный кадр, а *\<Тип\>* — тип значения, которое класс анимирует.  Анимация по полным кадрам, поддерживающая все три метода интерполяции, будет иметь три типа полных кадров, которые можно использовать.  Например можно использовать три типа полных кадров с <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>: <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>, <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> и <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>.  \(Методы интерполяции описаны подробно в следующих разделах.\)  
  
 Основной целью полного кадра является задание <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> и <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  Каждый тип полного кадра предоставляет эти два свойства.  
  
-   Свойство <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> указывает заданное значение для этого полного кадра.  
  
-   Свойство <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> определяет, когда \(в пределах анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A>\) достигается значение полного кадра <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
 Когда начинается анимация по полным кадрам, итерация полных кадров происходит в порядке, определенном свойствами <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  
  
-   Если в нулевой момент времени нет полного кадра, анимация создает переход между целевым значением свойства и <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> первого полного кадра. В противном случае выходное значение анимации становится первым значением полного кадра.  
  
-   Анимация создает переход между <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> первого и второго полного кадра с помощью метода интерполяции, определяемого вторым полным кадром.  Переход начинается с <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> первого полного кадра и заканчивается при достижении <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> второго полного кадра.  
  
-   Анимация продолжается, при этом создаются переходы между каждым предыдущим и последующим полным кадром.  
  
-   Наконец, анимация переходит к значению полного кадра с наибольшим временем, который меньше или равен значению анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 Если значением анимации <xref:System.Windows.Media.Animation.Timeline.Duration%2A> является <xref:System.Windows.Duration.Automatic%2A> или ее <xref:System.Windows.Media.Animation.Timeline.Duration%2A> равен времени последнего полного кадра, анимация завершается.  В противном случае, если значение анимации <xref:System.Windows.Duration> больше, чем время последнего полного кадра, анимация удерживает значение полного кадра до тех пор, пока оно не достигнет конца его <xref:System.Windows.Duration>.  Как и любая анимация, анимация по полным кадрам использует свойство<xref:System.Windows.Media.Animation.Timeline.FillBehavior%2A> для определения, будет ли она хранить конечное значение после завершения активного периода.  Дополнительные сведения см. в разделе [Общие сведения о характере поведения во времени](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md).  
  
 В следующем примере объект <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>, определенный в предыдущем примере, используется для демонстрации, как работают свойства <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> и <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  
  
-   Первый полный кадр немедленно устанавливает выходное значение анимации в 0.  
  
-   Второй полный кадр анимируется от 0 до 350.  Он запускается после окончания первого полного кадра \(в момент времени 0 секунд\), воспроизводится в течение 2 секунд и заканчивается в момент времени 0:0:2.  
  
-   Третий полный кадр анимируется от 350 до 50.  Он запускается по окончании второго полного кадра \(в момент времени 2 секунды\), воспроизводится в течение 5 секунд и заканчивается в момент времени 0:0:7.  
  
-   Четвертый полный кадр анимируется от 50 до 200.  Он запускается по окончании третьего полного кадра \(в момент времени 7 секунд\), воспроизводится в течение 1 секунды и заканчивается в момент времени 0:0:8.  
  
-   Так как свойство <xref:System.Windows.Media.Animation.Timeline.Duration%2A> было установлено в значение 10 секунд, анимация хранит его конечное значение в течение двух секунд до времени окончания, равного 0:0:10.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#BasicKeyFrameExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyFramesIntroduction.xaml#basickeyframeexamplewholepage)]  -->  
  
<a name="interpolationmethods"></a>   
## Методы интерполяции  
 В предыдущих разделах упоминалось, что некоторые анимации по полным кадрам поддерживают несколько методов интерполяции.  Интерполяция анимации описывает, как анимация выполняет переход между значениями во время ее выполнения.  Выбрав тип полного кадра, который будет использоваться анимацией, можно определить метод интерполяции для этого полного кадра.  Существуют три различных типа методов интерполяции: линейные, дискретные и сплайновые.  
  
### Линейная интерполяция  
 При [линейной интерполяции](GTMT) длительность сегментов при анимации остается постоянной.  Например, если сегмент полного кадра переходит от 0 до 10 в течение 5 секунд, анимация будет выводить следующие значения в указанное время:  
  
|Время|Выходное значение.|  
|-----------|------------------------|  
|0|0|  
|1|2|  
|2|4|  
|3|6|  
|4|8|  
|4.25|8.5|  
|4.5|9|  
|5|10|  
  
### Дискретная интерполяция  
 При [дискретной интерполяции](GTMT) функция анимации переходит от одного значения к следующему без интерполяции.  Если сегмент полного кадра переходит от 0 до 10 в течение 5 секунд, анимация будет выводить следующие значения в указанное время:  
  
|Время|Выходное значение.|  
|-----------|------------------------|  
|0|0|  
|1|0|  
|2|0|  
|3|0|  
|4|0|  
|4.25|0|  
|4.5|0|  
|5|10|  
  
 Обратите внимание, что анимация не изменяет свое выходное значение до окончания продолжительности всего сегмента.  
  
 [Сплайновая интерполяция](GTMT) является более сложной.  Оно описана в следующем разделе.  
  
<a name="anim_spline"></a>   
### Сплайновая интерполяция  
 Сплайновую интерполяцию можно использовать для достижения более реалистичных временных эффектов.  Поскольку анимация часто используются для имитации эффектов, которые возникают в реальных условиях, разработчикам может потребоваться тонкое управление ускорением и замедлением объектов и сегментами времени.  Полные сплайновые кадры позволяют создавать анимацию с помощью сплайновой интерполяции.  Вместе с другими полными кадрами определяются <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> и <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  С полным сплайновым кадром также указывается <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A>.  В следующем примере показан один сплайновый полный кадр для <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.  Обратите внимание на свойство <xref:System.Windows.Media.Animation.KeySpline>; именно этим сплайновый полный кадр отличается от других типов полных кадров.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->  
  
 [Кривая Безье третьего порядка](GTMT) определяется начальной точкой, конечной точкой и двумя контрольными точками.  Свойство <xref:System.Windows.Media.Animation.KeySpline> сплайнового полного кадра определяет две контрольные точки кривой Безье, которая располагается между \(0,0\) и \(1,1\).  Первая контрольная точка определяет коэффициент кривизны первой половины кривой Безье, а вторая контрольная точка определяет коэффициент кривизны второй половины сегмента Безье.  Полученная кривая описывает частоту изменения для этого сплайнового полного кадра.  Чем круче кривая, тем быстрее полный кадр изменяет свои значения.  Чем более плоской становится кривая, тем медленнее изменяет свои значения полный кадр.  
  
 Можно использовать <xref:System.Windows.Media.Animation.KeySpline> для имитации физических траекторий, таких как падающая вода или прыгающий шарик, или применить другие "легко вводимые" и "легко достигаемые" эффекты анимации.  Чтобы добиться эффектов взаимодействия с пользователем, таких как затухание фона или изменение размеров кнопки, может применяться сплайновая интерполяция для увеличения или уменьшения скорости изменения анимации.  
  
 В следующем примере для <xref:System.Windows.Media.Animation.KeySpline> задается значение 0,1 1,0, которое создает следующую кривую Безье.  
  
 ![Кривая Безье](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-0-1-1-0.png "graphicsmm\_keyspline\_0\_1\_1\_0")  
Ключевой сплайн с контрольными точками \(0,0, 1,0\) и \(1,0, 0,0\)  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexample)]  -->  
  
 Этот полный кадр анимируется быстро при запуске, замедляется и затем снова ускоряется перед завершением.  
  
 В следующем примере для <xref:System.Windows.Media.Animation.KeySpline> задается значение 0,5, 0,25 0,75, 1,0, которое создает следующую кривую Безье.  
  
 ![Кривая Безье](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-keyspline-025-050-075-10.png "graphicsmm\_keyspline\_025\_050\_075\_10")  
Ключевой сплайн с контрольными точками \(0,25, 0,5\) и \(0,75, 1,0\)  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SingleSplineKeyFrameExampleInline3](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#singlesplinekeyframeexampleinline3)]  -->  
  
 Поскольку изгиб кривой Безье изменяется незначительно, этот полный кадр анимируется почти с постоянной скоростью; он несколько замедляется перед завершением.  
  
 В следующем примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> используется для анимации положения прямоугольника.  Поскольку <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> использует объекты <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>, для перехода между значениями полного кадра используется сплайновая интерполяция.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SplinedInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#SplinedInterpolationExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#splinedinterpolationexample)]  -->  
  
 Сплайновую интерполяцию достаточно трудно понять. Помочь в этом может эксперимент с различными настройками.  Пример [Key Spline Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160011) \("Анимация ключевого сплайна"\) позволяет изменять значения ключевого сплайна и видеть результаты этих изменений в анимации.  
  
<a name="combininginterpolationmethods"></a>   
### Объединение методов интерполяции  
 Можно использовать полные кадры с различными типами интерполяции в одной анимации по полным кадрам.  Когда две анимации по полным кадрам с различными интерполяциями следуют друг за другом, метод интерполяции второго полного кадра используется для создания перехода от первого значения ко второму.  
  
 В следующем примере создается <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>, который использует линейную, сплайновую и дискретную интерполяцию.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#ComboInterpolationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/InterpolationMethodsExample.xaml#combointerpolationexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#ComboInterpolationExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/InterpolationMethodsExample.xaml#combointerpolationexample)]  -->  
  
<a name="keytimes"></a>   
## Дополнительные сведения о длительности и времени полного кадра  
 Как и другие виды анимации, анимация по полным кадрам имеет свойство <xref:System.Windows.Duration>.  В дополнение к определению <xref:System.Windows.Duration> анимации, необходимо, указать какая часть длительности предоставляется каждому полному кадру.  Это происходит с помощью указания <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> для каждого полного кадра анимации.  Каждый параметр <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> полного кадра указывает момент окончания полного кадра.  
  
 Свойство <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> не указывает продолжительность воспроизведения полного кадра.  Продолжительность воспроизведения полного кадра определяется моментом окончания полного кадра, моментом окончания предыдущего полного кадра и длительностью анимации.  Время полного кадра может быть указано в виде значения времени, в процентах или как специальные значения <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> или <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 В следующем списке описываются различные способы определения времени полного кадра.  
  
### Значения TimeSpan  
 Можно использовать значение <xref:System.TimeSpan> для указания <xref:System.Windows.Media.Animation.KeyTime>.  Значение должно быть больше или равно 0 и меньше или равно длительности анимации.  В следующем примере показана анимация с длительностью 10 секунд и четыре полных кадра, время которых указывается в виде значения времени.  
  
-   Первый полный кадр анимируется от базового значения до 100 в первые 3 секунды и заканчивается в момент времени равный 0:0:03.  
  
-   Второй полный кадр анимируется от 100 до 200.  Он запускается после окончания первого полного кадра \(в момент времени 3 секунды\), воспроизводится в течение 5 секунд и заканчивается в момент времени 0:0:8.  
  
-   Третий полный кадр анимируется от 200 до 500.  Он запускается по окончании второго полного кадра \(в момент времени 8 секунд\), воспроизводится в течение 1 секунды и заканчивается в момент времени 0:0:9.  
  
-   Четвертый полный кадр анимируется от 500 до 600.  Он запускается по окончании третьего полного кадра \(в момент времени 9 секунд\), воспроизводится в течение 1 секунды и заканчивается в момент времени 0:0:10.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#TimeSpanKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#timespankeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#TimeSpanKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#timespankeytimeexample)]  -->  
  
### Значения в процентах  
 Процентное значение указывает, что полный кадр заканчивается по истечении некоторого процента от <xref:System.Windows.Media.Animation.Timeline.Duration%2A> анимации.  В [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] задайте процент в виде числа за которым следует символ `%`.  В коде используйте метод <xref:System.Windows.Media.Animation.KeyTime.FromPercent%2A> и передайте его <xref:System.Double>, указав процент.  Значение должно быть больше или равно 0 и меньше или равно 100%.  В следующем примере показана анимация длительностью 10 секунд и четыре полных кадра, время которых указывается в виде процентов.  
  
-   Первый полный кадр анимируется от базового значения до 100 в первые 3 секунды и заканчивается в момент времени равный 0:0:3.  
  
-   Второй полный кадр анимируется от 100 до 200.  Он запускается по окончании первого полного кадра \(в момент времени 3 секунды\), воспроизводится в течение 5 секунд и заканчивается в момент времени 0:0:8 \(0,8 \* 10 \= 8\).  
  
-   Третий полный кадр анимируется от 200 до 500.  Он запускается по окончании второго полного кадра \(в момент времени 8 секунд\), воспроизводится в течение 1 секунды и заканчивается в момент времени 0:0:9 \(0,9 \* 10 \= 9\).  
  
-   Четвертый полный кадр анимируется от 500 до 600.  Он запускается по окончании третьего полного кадра \(в момент времени 9 секунд\), воспроизводится в течение 1 секунды и заканчивается в момент времени 0:0:10 \(1 \* 10 \= 10\).  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PercentageKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#percentagekeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PercentageKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#percentagekeytimeexample)]  -->  
  
### Специальные значения, унифицирование  
 Используйте расчет времени <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>, если необходимо, чтобы каждый полный кадр продолжался одно и то же количество времени.  
  
 Время полного кадра <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> делит доступное время между всеми полными кадрами для определения времени окончания каждого из них.  В следующем примере показана анимация длительностью 10 секунд и четыре полных кадра, время которых задается как <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>.  
  
-   Первый полный кадр анимируется от базового значения до 100 в первые 2,5 секунды и заканчивается в момент времени равный 0:0:2.5.  
  
-   Второй полный кадр анимируется от 100 до 200.  Он запускается по окончании первого полного кадра \(в момент времени 2,5 секунды\), воспроизводится в течение 2,5 секунд и заканчивается в момент времени 0:0:5.  
  
-   Третий полный кадр анимируется от 200 до 500.  Он запускается по окончании второго полного кадра \(в момент времени 5 секунд\), воспроизводится в течение 2,5 секунд и заканчивается в момент времени 0:0:7.5.  
  
-   Четвертый полный кадр анимируется от 500 до 600.  Он запускается по окончании второго полного кадра \(в момент времени 7,5 секунды\), воспроизводится в течение 2,5 секунд и заканчивается в момент времени 0:0:1.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#UniformKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#uniformkeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#UniformKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#uniformkeytimeexample)]  -->  
  
### Специальные значения, скорость  
 Используйте расчет времени <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, если требуется анимация с постоянной скоростью.  
  
 Время полного кадра <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> выделяет доступное время в соответствии с длиной каждого из полных кадров для определения длительности каждого кадра.  Это приведет к тому, что скорость или темп анимации остаются постоянными.  В следующем примере показана анимация длительностью 10 секунд и три полных кадра, время которых задается как <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>.  
  
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PacedKeyTimeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_ovw_snip/CS/KeyTimesExample.xaml#pacedkeytimeexample)]  -->
 <!-- TODO: review snippet reference [!code-xml[keyframes_ovw_snip#PacedKeyTimeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_ovw_snip/XAML/KeyTimesExample.xaml#pacedkeytimeexample)]  -->  
  
 Обратите внимание, что если временем последнего полного кадра является <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> или <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A>, его определяемое время будет установлено в 100 процентов.  Если первый полный кадр в мультикадровой анимации является процентным, его полное время будет равным 0.  \(Если в коллекции полных кадров содержится лишь один полный кадр, являющийся процентным, его полное время будет равным 100 %\).  
  
 Различные полные кадры в пределах одной анимации по полным кадрам могут использовать различные типы полного времени.  
  
<a name="combiningkeytimes"></a>   
## Объединение типов полного времени, поврежденные полные кадры  
 Можно использовать полные кадры с различными типами значений <xref:System.Windows.Media.Animation.KeyTime> в одной анимации.  Хотя рекомендуется добавлять полные кадры в том порядке, в котором они должны воспроизводиться, это не является необходимым.  Анимация и система расчета времени способны определить порядок полных кадров.  Полные кадры с недопустимым полным временем игнорируются.  
  
 В следующем списке описывается процедура, по которой полное время определяется для полного кадра анимации по полным кадрам.  
  
1.  Определите значения <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime>.  
  
2.  Определите *общее время интерполяции* анимации, то есть общее время, затрачиваемое на анимацию по полным кадрам на выполнение прямой итерации.  
  
    1.  Если <xref:System.Windows.Media.Animation.Timeline.Duration%2A> анимации не является <xref:System.Windows.Duration.Automatic%2A> или <xref:System.Windows.Duration.Forever%2A>, общим временем интерполяции является значение свойства <xref:System.Windows.Media.Animation.Timeline.Duration%2A> анимации.  
  
    2.  В противном случае временем интерполяции будет являться наибольшее значение <xref:System.TimeSpan> <xref:System.Windows.Media.Animation.KeyTime>, которое указано полными кадрами \(если таковое имеется\).  
  
    3.  Если нет — общим временем интерполяции будет являться 1 секунда.  
  
3.  Используйте значение общего времени интерполяции для определения значений <xref:System.Windows.Media.Animation.KeyTimeType> <xref:System.Windows.Media.Animation.KeyTime>.  
  
4.  Определите последний полный кадр, если он не был еще определен на предыдущих этапах.  Если <xref:System.Windows.Media.Animation.KeyTime> последнего полного кадра является <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> или <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, его определенное время будет совпадать с общим временем интерполяции.  
  
     Если <xref:System.Windows.Media.Animation.KeyTime> первого полного кадра является <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> и эта анимация имеет более чем один кадр, установите значение <xref:System.Windows.Media.Animation.KeyTime> в 0. Если имеется только один полный кадр и для его параметра <xref:System.Windows.Media.Animation.KeyTime> установлено значение <xref:System.Windows.Media.Animation.KeyTime.Paced%2A>, оно определяет общее время интерполяции, как описано в предыдущем шаге.  
  
5.  Определите оставшиеся значения <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime>: каждое из них получает равную долю доступного времени.  В ходе этого процесса неопределенные значения <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> временно рассматриваются как значения <xref:System.Windows.Media.Animation.KeyTime.Uniform%2A> <xref:System.Windows.Media.Animation.KeyTime> и получают временно определенное время.  
  
6.  Определите значение <xref:System.Windows.Media.Animation.KeyTime> для полных кадров с неопределенным полным временем с помощью полных кадров, объявленных рядом с ними, которые имеют определенные значения <xref:System.Windows.Media.Animation.KeyTime>.  
  
7.  Определите оставшиеся значения <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime>.  <xref:System.Windows.Media.Animation.KeyTime.Paced%2A> <xref:System.Windows.Media.Animation.KeyTime> используют значения <xref:System.Windows.Media.Animation.KeyTime> соседних полных кадров, чтобы определить их определенное время.  Это необходимо, убедиться в том, что скорость анимации является постоянной во время этих полных кадров.  
  
8.  Отсортируйте полные кадры в порядке определенного времени \(первичный ключ\), и в порядке объявления \(вторичный ключ\), то есть используйте строгую сортировку на основе определенных значений <xref:System.Windows.Media.Animation.KeyTime> полных кадров.  
  
## См. также  
 <xref:System.Windows.Media.Animation.KeyTime>   
 <xref:System.Windows.Media.Animation.KeySpline>   
 <xref:System.Windows.Media.Animation.Timeline>   
 [Key Spline Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160011)   
 [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012)   
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Общие сведения о Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Практические руководства, посвященные анимации по полным кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)   
 [Общие сведения о характере поведения во времени](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)