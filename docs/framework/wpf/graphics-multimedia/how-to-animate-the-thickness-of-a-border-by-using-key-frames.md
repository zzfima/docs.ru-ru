---
title: Инструкция по Анимации толщины границы с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: 884b62e88c347449ae39caa9c028d09db39b9f4b
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344692"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a>Инструкция по Анимации толщины границы с помощью ключевых кадров
Этот пример показывает, как <xref:System.Windows.Controls.Control.BorderThickness%2A> оживить свойство <xref:System.Windows.Controls.Border>.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> используется класс <xref:System.Windows.Controls.Control.BorderThickness%2A> для анимировать свойство <xref:System.Windows.Controls.Border>. Эта анимация использует три ключевых кадра следующим образом:  
  
1. В течение первой половины второй, <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> использует экземпляр класса постепенно увеличивать толщину границы. Пример использует <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> для создания плавного линейного увеличения между значениями.  
  
2. В конце следующей половины секунды, <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> использует экземпляр класса, чтобы внезапно увеличить толщину границы. Дискретные ключевые кадры, <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> подобные тем, которые получены в ходе создания резких скачков между значениями, то есть движение анимации отрывисто.  
  
3. В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> использует экземпляр класса, чтобы уменьшить толщину границы. Ключевые кадры Spline, <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> подобные тем, которые получены из создания <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> переменного перехода между значениями в соответствии со значениями свойства. В этом опорном кадре анимация начинается медленно и экспоненциально ускоряется к концу временного сегмента.  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
- [Анимирование значения BorderThickness](../controls/how-to-animate-a-borderthickness-value.md)
