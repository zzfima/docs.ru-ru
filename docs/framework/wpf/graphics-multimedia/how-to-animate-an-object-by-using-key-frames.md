---
title: Практическое руководство. Анимация объекта с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: ffbe1845b634c8f94eb6a10dfa44fcf9903e0cd5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933911"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Практическое руководство. Анимация объекта с помощью ключевых кадров
В этом примере показано, как анимировать объект, который в этом примере является <xref:System.Windows.Controls.Page.Background%2A> свойством <xref:System.Windows.Controls.Page> элемента управления, с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> класс используется для анимации изменений цвета <xref:System.Windows.Controls.Page.Background%2A> для свойства <xref:System.Windows.Controls.Page> элемента управления. В примере анимация изменяется на другую фоновую кисть через регулярные интервалы. Эта анимация использует <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> класс для создания трех разных ключевых кадров. Анимация использует ключевые кадры следующим образом:  
  
1. В конце первой секунды анимируется экземпляр <xref:System.Windows.Media.LinearGradientBrush> класса. В этом разделе примера к цвету фона применяется линейный градиент, что позволяет цвету переходить от желтого к оранжевый к красному.  
  
2. В конце следующей секунды анимируется экземпляр <xref:System.Windows.Media.RadialGradientBrush> класса. В этом разделе примера к цвету фона применяется радиальный градиент, чтобы цвет переменялся с белого на синий.  
  
3. В конце третьей секунды анимируется экземпляр <xref:System.Windows.Media.DrawingBrush> класса. В этом разделе примера к фону применяется шаблон шахматной доски.  
  
4. Анимация начинается снова и повторяется неограниченное время.  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>— единственный тип ключевого кадра, который можно использовать с <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> классом. Ключевые кадры, <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> такие как создание неожиданных изменений в значениях, то есть изменения цвета в этом примере происходят внезапно.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [Общие сведения об анимации по ключевым кадрам](key-frame-animations-overview.md)
- [Практические руководства, посвященные анимации по ключевым кадрам](key-frame-animation-how-to-topics.md)
