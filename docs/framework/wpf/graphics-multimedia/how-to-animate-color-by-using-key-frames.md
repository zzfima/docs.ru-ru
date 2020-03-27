---
title: Практическое руководство. Анимация цвета с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
ms.openlocfilehash: 8a444706f7541b52722ab8257a88e76c3e1b0938
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344751"
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Практическое руководство. Анимация цвета с помощью ключевых кадров
Этот пример показывает, как <xref:System.Windows.Media.SolidColorBrush.Color%2A> оживить <xref:System.Windows.Media.SolidColorBrush> кадры ключей.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> используется класс <xref:System.Windows.Media.SolidColorBrush.Color%2A> для анимировать свойство <xref:System.Windows.Media.SolidColorBrush>. Эта анимация использует три ключевых кадра следующим образом:  
  
1. В течение первых двух секунд используется <xref:System.Windows.Media.Animation.LinearColorKeyFrame> экземпляр класса для постепенного изменения цвета с зеленого на красный. Линейные ключевые <xref:System.Windows.Media.Animation.LinearColorKeyFrame> кадры, такие как создание плавного линейного перехода между значениями.  
  
2. В конце следующей половины секунды используется <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> экземпляр класса, чтобы быстро изменить цвет с красного на желтый. Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> кадры, такие как создают внезапные изменения между значениями, то есть изменение цвета в этой части анимации происходит быстро и не является тонким.  
  
3. В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplineColorKeyFrame> использует экземпляр класса, чтобы изменить цвет снова- на этот раз с желтого на зеленый. Сплайс-ключевые кадры, такие как <xref:System.Windows.Media.Animation.SplineColorKeyFrame> создание переменного <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> перехода между значениями в зависимости от значений свойства. В этом примере изменение цвета начинается медленно и ускоряется экспоненциально к концу временного сегмента.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.SolidColorBrush.Color%2A>
- <xref:System.Windows.Media.SolidColorBrush>
- <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
