---
title: Практическое руководство. Анимация прямоугольника с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: bcc9e7f198b8a20ffe13daf6508fb8a735937652
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344668"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Практическое руководство. Анимация прямоугольника с помощью ключевых кадров
В этом примере показано, <xref:System.Windows.Media.RectangleGeometry.Rect%2A> как <xref:System.Windows.Media.RectangleGeometry> оживить свойство элемента с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> используется класс <xref:System.Windows.Media.RectangleGeometry.Rect%2A> для анимировать свойство <xref:System.Windows.Media.RectangleGeometry>. Эта анимация использует три ключевых кадра следующим образом:  
  
1. В течение первых двух секунд используется <xref:System.Windows.Media.Animation.LinearRectKeyFrame> экземпляр класса для анимирования постепенного изменения положения, ширины и высоты прямоугольника. Линейные ключевые <xref:System.Windows.Media.Animation.LinearRectKeyFrame> кадры, такие как создание плавного линейного перехода между значениями.  
  
2. В конце следующей половины секунды, <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> использует экземпляр класса, чтобы внезапно уменьшить высоту прямоугольника. Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> кадры, такие как создают внезапные изменения между значениями, то есть снижение высоты происходит быстро и не является тонким.  
  
3. В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplineRectKeyFrame> использует экземпляр класса, чтобы изменить прямоугольник обратно в свой первоначальный размер и положение. Сплайс-ключевые кадры, такие как <xref:System.Windows.Media.Animation.SplineRectKeyFrame> создание переменного <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> перехода между значениями в зависимости от значений свойства. В этом примере изменение начинается медленно и ускоряется экспоненциально к концу временного сегмента.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.RectangleGeometry>
- <xref:System.Windows.Media.RectangleGeometry.Rect%2A>
- <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
