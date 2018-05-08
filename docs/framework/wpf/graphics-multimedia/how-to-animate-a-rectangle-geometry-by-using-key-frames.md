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
ms.openlocfilehash: 581dc89d21091ad0ce856d7a7ced84fd7bcea9d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a>Практическое руководство. Анимация прямоугольника с помощью ключевых кадров
В этом примере демонстрируется анимация <xref:System.Windows.Media.RectangleGeometry.Rect%2A> свойство <xref:System.Windows.Media.RectangleGeometry> с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Media.RectangleGeometry.Rect%2A> свойство <xref:System.Windows.Media.RectangleGeometry>. Эта анимация использует три ключевых кадра следующим образом:  
  
1.  В течение первых двух секунд используется экземпляр <xref:System.Windows.Media.Animation.LinearRectKeyFrame> класса для анимации постепенного изменения положение, ширину и высоту прямоугольника. Линейный ключевые кадры, такие как <xref:System.Windows.Media.Animation.LinearRectKeyFrame> Создание линейной плавный переход между значениями.  
  
2.  Во время окончания следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> класс неожиданно уменьшить высоту прямоугольника. Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> создают внезапные изменения между значениями, то есть, уменьшение высоты происходит быстро, но заметно.  
  
3.  В течение последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineRectKeyFrame> классе, чтобы изменить прямоугольник обратно в исходный размер и положение. Как и опорных кадров сплайна <xref:System.Windows.Media.Animation.SplineRectKeyFrame> создания переменного перехода между значениями согласно значениям <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> свойство. В этом примере изменение начинается медленно и ускоряется экспоненциально к концу временного сегмента.  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
