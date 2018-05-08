---
title: Практическое руководство. Анимация строки с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 5219ce11667c84d3ceca380d5a4ddd52695736b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Практическое руководство. Анимация строки с помощью ключевых кадров
В этом примере показано, как анимация строки, который в данном примере — <xref:System.Windows.Controls.ContentControl.Content%2A> свойства <xref:System.Windows.Controls.Button> элемента управления с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Controls.ContentControl.Content%2A> свойство <xref:System.Windows.Controls.Button>.  
  
 Все ключевые кадры в этом примере используется экземпляр <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> класса, поскольку строка анимации, которая создается с помощью ключевых кадров может использовать только дискретные ключевых кадров. Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> создают резкие переходы между значениями, то есть, примет анимации происходят быстро, но заметно.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
