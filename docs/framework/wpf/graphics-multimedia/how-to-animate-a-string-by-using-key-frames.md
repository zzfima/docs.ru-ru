---
title: Практическое руководство. Анимация строки с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344672"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Практическое руководство. Анимация строки с помощью ключевых кадров
В этом примере показано, как анимировать строку, которая в данном примере является <xref:System.Windows.Controls.ContentControl.Content%2A> свойством <xref:System.Windows.Controls.Button> элемента управления, используя ключевые кадры.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> используется класс <xref:System.Windows.Controls.ContentControl.Content%2A> для анимировать свойство <xref:System.Windows.Controls.Button>.  
  
 Все ключевые кадры в этом примере используют экземпляр <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> класса, потому что струнная анимация, созданная с помощью ключевых кадров, может использовать только дискретные ключевые кадры. Дискретные ключевые <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> кадры, такие как создают резкие скачки между значениями, то есть изменения в анимации происходят быстро и не являются тонкими.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
