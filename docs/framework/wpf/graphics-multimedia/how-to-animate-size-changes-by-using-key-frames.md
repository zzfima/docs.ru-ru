---
title: Практическое руководство. Анимация изменений размера с использованием ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 0c2828215527a285943a79920de51fa42fe7a8a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559896"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Практическое руководство. Анимация изменений размера с использованием ключевых кадров
В этом примере показано, как можно анимировать изменения размера с использованием ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Media.ArcSegment.Size%2A> свойство <xref:System.Windows.Media.ArcSegment>. Эта анимация использует три ключевых кадра следующим образом:  
  
1.  Во время первого полсекунды анимации, используется экземпляр <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> класс постепенно увеличить размер дуги. Линейный ключевые кадры, такие как <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> Создание линейной плавный переход между значениями.  
  
2.  В конце следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> класс внезапно увеличение размера дуги. Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> создают резкие переходы между значениями, то есть, изменения размера происходят внезапно и не остаются незамеченными.  
  
3.  Через последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> класса, чтобы увеличить размер дуги. Как и опорных кадров сплайна <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> создания переменного перехода между значениями согласно значениям <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> свойство. В этом примере размер дуги сначала увеличивается медленно, а ближе к концу временного сегмента — экспоненциально.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
