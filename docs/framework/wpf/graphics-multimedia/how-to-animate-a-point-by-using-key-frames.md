---
title: Практическое руководство. Анимация точки с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating Points with
- Points [WPF], animating with key frames
- animation [WPF], Points with key frames
ms.assetid: d2e2ef10-0773-4133-856e-d41c09f60ded
ms.openlocfilehash: edcba36644cf78d6e98f934d9bd8b593af38b328
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344883"
---
# <a name="how-to-animate-a-point-by-using-key-frames"></a>Практическое руководство. Анимация точки с помощью ключевых кадров
В этом примере <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> показано, как использовать <xref:System.Windows.Point>класс для анимировать элемент .  
  
## <a name="example"></a>Пример  
 В следующем примере эллипс перемещается по треугольному пути. Пример использует <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames> класс для анимировать свойство <xref:System.Windows.Media.EllipseGeometry.Center%2A> . <xref:System.Windows.Media.EllipseGeometry> Эта анимация использует три ключевых кадра следующим образом:  
  
1. В течение первой половины второй, <xref:System.Windows.Media.Animation.LinearPointKeyFrame> использует экземпляр класса для перемещения эллипса по пути с постоянной скоростью от его исходного положения. Линейные ключевые <xref:System.Windows.Media.Animation.LinearPointKeyFrame> кадры, такие как создание плавной линейной интерполяции между значениями.  
  
2. В конце следующей половины секунды используется <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> экземпляр класса, чтобы внезапно переместить эллипс по пути в следующую позицию. Дискретные ключевые <xref:System.Windows.Media.Animation.DiscretePointKeyFrame> кадры, такие как создают внезапные скачки между значениями.  
  
3. В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplinePointKeyFrame> использует экземпляр класса для перемещения эллипса обратно в исходное положение. Сплайс-ключевые кадры, такие как <xref:System.Windows.Media.Animation.SplinePointKeyFrame> создание переменного <xref:System.Windows.Media.Animation.SplinePointKeyFrame.KeySpline%2A> перехода между значениями в зависимости от значений свойства. В этом примере анимация начинается медленно и ускоряется экспоненциально к концу временного отрезка.  
  
 [!code-csharp[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/PointAnimationUsingKeyFramesExample.cs#pointanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/pointanimationusingkeyframesexample.vb#pointanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#PointAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/PointAnimationUsingKeyFramesExample.xaml#pointanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
 Для согласованности с другими примерами анимации <xref:System.Windows.Media.Animation.Storyboard> в кодовых <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>версиях этого примера используется объект для применения . Однако при применении одной анимации в коде <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> проще использовать метод <xref:System.Windows.Media.Animation.Storyboard>вместо использования . Например, [см. Animate a Property без использования раскадровки.](how-to-animate-a-property-without-using-a-storyboard.md)  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Animation.PointAnimationUsingKeyFrames>
- <xref:System.Windows.Media.EllipseGeometry.Center%2A?displayProperty=nameWithType>
- <xref:System.Windows.Media.EllipseGeometry>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
