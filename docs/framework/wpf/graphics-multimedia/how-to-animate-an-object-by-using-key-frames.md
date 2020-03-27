---
title: Практическое руководство. Анимация объекта с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 0bc33b189fd856dbe8106c1db35bc18e27ea131e
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344709"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Практическое руководство. Анимация объекта с помощью ключевых кадров
Этот пример показывает, как оживить объект, который в <xref:System.Windows.Controls.Page.Background%2A> этом <xref:System.Windows.Controls.Page> примере является свойством элемента управления, с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> используется класс для анимировать изменения цвета для <xref:System.Windows.Controls.Page.Background%2A> свойства элемента <xref:System.Windows.Controls.Page> управления. Пример анимации меняется на другую фоновом уистику через регулярные промежутки времени. Эта анимация <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> использует класс для создания трех различных ключевых кадров. Анимация использует ключевые кадры следующим образом:  
  
1. В конце первой секунды, анимирует экземпляр <xref:System.Windows.Media.LinearGradientBrush> класса. В этом разделе пример применяется линейный градиент к цвету фона, так что цвет переходит от желтого к оранжевому на красный.  
  
2. В конце следующей секунды, анимирует <xref:System.Windows.Media.RadialGradientBrush> экземпляр класса. В этом разделе пример применяется радиальный градиент к цвету фона, так что цвет переходит от белого к белому к черному.  
  
3. В конце третьей секунды, оживляет <xref:System.Windows.Media.DrawingBrush> экземпляр класса. В этом разделе пример применяется шаблон зачекане.  
  
4. Анимация начинается снова и повторяется бесконечно.  
  
> [!NOTE]
> <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>является единственным типом ключа кадра, <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> который можно использовать с классом. Ключевые кадры, такие как <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> создают внезапные изменения значений, то есть изменения цвета в этом примере происходят внезапно.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
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
