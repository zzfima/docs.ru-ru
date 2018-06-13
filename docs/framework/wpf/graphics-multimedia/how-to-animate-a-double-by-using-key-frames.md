---
title: Инструкция по Анимации типа Double с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
ms.openlocfilehash: 4adeb858ab1b69ef1b00f7bf3b6868dbcbbc4154
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557437"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Инструкция по Анимации типа Double с помощью ключевых кадров
В этом примере показано, как анимация значения свойства, которое принимает <xref:System.Double> с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере прямоугольник перемещается по экрану. В этом примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Media.TranslateTransform.X%2A> свойство <xref:System.Windows.Media.TranslateTransform> применены к <xref:System.Windows.Shapes.Rectangle>. Эта анимация, которая бесконечно повторяется, использует три ключевых кадра следующим образом:  
  
1.  В течение первых трех секунд используется экземпляр <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> класс, чтобы переместить прямоугольник в пути с постоянной скоростью из его начальной позиции в позиции 500. Линейный ключевые кадры, такие как <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> Создание линейной плавный переход между значениями.  
  
2.  В конце четвертый второй используется экземпляр <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> класс внезапно Перемещение прямоугольника до следующей позиции. Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> создают резкие переходы между значениями. В этом примере прямоугольник находится в начальной позиции, а затем внезапно появляется в позиции 500.  
  
3.  В последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> класса, чтобы переместить прямоугольник обратно в исходное положение. Как и опорных кадров сплайна <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> создания переменного перехода между значениями в соответствии со значением <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> свойство. В этом примере прямоугольник начинает двигаться медленно и ускоряется экспоненциально к концу временного отрезка.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
 Для совместимости с другими примерами анимации версии кода этого примера используют <xref:System.Windows.Media.Animation.Storyboard> объекта для применения <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>. Кроме того, при применении одной анимации в коде, проще использовать <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод вместо <xref:System.Windows.Media.Animation.Storyboard>. Пример см. в разделе [Анимация свойства без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
