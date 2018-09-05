---
title: Практическое руководство. Анимация изменений размера с использованием ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 69845d1d75f81042bbeb20ee6b1015f5c2f53b81
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43672562"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Практическое руководство. Анимация изменений размера с использованием ключевых кадров
В этом примере показано, как можно анимировать изменения размера с использованием ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Media.ArcSegment.Size%2A> свойство <xref:System.Windows.Media.ArcSegment>. Эта анимация использует три ключевых кадра следующим образом:  
  
1.  В течение первой половины секунды анимации используется экземпляр <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> класс для постепенного увеличения размера дуги. Линейные ключевые кадры, например <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> создать плавный линейный переход между значениями.  
  
2.  В конце следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> класс для резкого увеличения размера дуги. Дискретные ключевые кадры, например <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> , создают скачкообразные переходы между значениями, то есть, изменения размера происходят внезапно и не плавно.  
  
3.  За последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> класс для увеличения размера дуги. Ключевые кадры сплайна, например <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> , создают переменный переход между значениями в соответствии со значениями из <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> свойство. В этом примере размер дуги сначала увеличивается медленно, а ближе к концу временного сегмента — экспоненциально.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.ArcSegment.Size%2A>  
 <xref:System.Windows.Media.ArcSegment>  
 <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
