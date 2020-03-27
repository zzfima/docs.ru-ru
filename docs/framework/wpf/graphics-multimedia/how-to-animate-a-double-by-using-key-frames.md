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
ms.openlocfilehash: 9eab794cc8411230226cddc97beaa13c1bdd9405
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344937"
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a>Инструкция по Анимации типа Double с помощью ключевых кадров
В этом примере показано, как оживить значение <xref:System.Double> свойства, которое принимается с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере прямоугольник перемещается по экрану. Пример использует <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> класс для анимировать свойство <xref:System.Windows.Media.TranslateTransform.X%2A> <xref:System.Windows.Media.TranslateTransform> прикладного к . <xref:System.Windows.Shapes.Rectangle> Эта анимация, которая бесконечно повторяется, использует три ключевых кадра следующим образом:  
  
1. В течение первых трех секунд используется <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> экземпляр класса для перемещения прямоугольника по пути с постоянной скоростью от исходного положения до положения 500. Линейные ключевые <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> кадры, такие как создание плавного линейного перехода между значениями.  
  
2. В конце четвертой секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> класса для внезапного перемещения прямоугольника в следующую позицию. Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> кадры, такие как создают внезапные скачки между значениями. В этом примере прямоугольник находится в начальной позиции, а затем внезапно появляется в позиции 500.  
  
3. В последние две секунды используется <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> экземпляр класса для перемещения прямоугольника обратно в исходное положение. Сплайс-ключевые кадры, такие как <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> создание переменного перехода между значениями в зависимости от значения <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> свойства. В этом примере прямоугольник начинает двигаться медленно и ускоряется экспоненциально к концу временного отрезка.  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Для согласованности с другими примерами анимации <xref:System.Windows.Media.Animation.Storyboard> в кодовых <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>версиях этого примера используется объект для применения . Кроме того, при применении одной анимации в коде проще <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> использовать <xref:System.Windows.Media.Animation.Storyboard>метод вместо использования . Например, [см. Animate a Property без использования раскадровки.](how-to-animate-a-property-without-using-a-storyboard.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Shapes.Rectangle>
- <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>
- <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
