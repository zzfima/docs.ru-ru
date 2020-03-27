---
title: Практическое руководство. Анимация изменений размера с использованием ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344655"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Практическое руководство. Анимация изменений размера с использованием ключевых кадров
В этом примере показано, как можно анимировать изменения размера с использованием ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> используется класс <xref:System.Windows.Media.ArcSegment.Size%2A> для анимировать свойство <xref:System.Windows.Media.ArcSegment>. Эта анимация использует три ключевых кадра следующим образом:  
  
1. В первой половине второй анимации, использует <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> экземпляр класса постепенно увеличивать размер дуги. Линейные ключевые <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> кадры, такие как создание плавного линейного перехода между значениями.  
  
2. В конце следующей половины секунды, <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> использует экземпляр класса, чтобы внезапно увеличить размер дуги. Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> кадры, такие как создают внезапные скачки между значениями, то есть изменения размера происходят внезапно и не являются тонкими.  
  
3. В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> использует экземпляр класса, чтобы увеличить размер дуги. Сплайс-ключевые кадры, такие как <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> создание переменного <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> перехода между значениями в зависимости от значений свойства. В этом примере размер дуги сначала увеличивается медленно, а ближе к концу временного сегмента — экспоненциально.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
