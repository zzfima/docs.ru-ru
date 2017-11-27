---
title: "Практическое руководство. Анимация цвета с помощью ключевых кадров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors [WPF], animating with key frames
- animation [WPF], colors with key frames
- key frames [WPF], animating colors with
ms.assetid: ab04ffa6-4de9-4d5b-a3b4-4e35d5b2ef35
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d117d57e5cc761aa2f31fd6531bff8d96ea30dc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-animate-color-by-using-key-frames"></a>Практическое руководство. Анимация цвета с помощью ключевых кадров
В этом примере демонстрируется анимация <xref:System.Windows.Media.SolidColorBrush.Color%2A> из <xref:System.Windows.Media.SolidColorBrush> с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Media.SolidColorBrush.Color%2A> свойство <xref:System.Windows.Media.SolidColorBrush>. Эта анимация использует три ключевых кадра следующим образом:  
  
1.  В течение первых двух секунд используется экземпляр <xref:System.Windows.Media.Animation.LinearColorKeyFrame> класс постепенно изменение цвета зеленый или красный. Линейный ключевые кадры, такие как <xref:System.Windows.Media.Animation.LinearColorKeyFrame> Создание линейной плавный переход между значениями.  
  
2.  Во время окончания следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> класса для быстрого изменения цвета с красного на желтый. Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> создают внезапные изменения между значениями, то есть, изменение цвета в этой части анимации происходит быстро, но заметно.  
  
3.  В течение последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineColorKeyFrame> классе, чтобы изменить цвет снова — времени с момента обратной желтый зеленый цвет. Как и опорных кадров сплайна <xref:System.Windows.Media.Animation.SplineColorKeyFrame> создания переменного перехода между значениями согласно значениям <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> свойство. В этом примере изменение цвета начинается медленно и ускоряется экспоненциально к концу временного сегмента.  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
