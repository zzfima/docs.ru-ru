---
title: Практическое руководство. Анимация объекта с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], objects with key frames
- key frames [WPF], animating objects with
ms.assetid: b1f15ba9-cac7-4cea-8699-5c6b55c05c5e
ms.openlocfilehash: 7dc49bc6b3f9156507cb821bfc32b269365b206c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33558544"
---
# <a name="how-to-animate-an-object-by-using-key-frames"></a>Практическое руководство. Анимация объекта с помощью ключевых кадров
В этом примере показано, как анимация объекта, который в данном примере — <xref:System.Windows.Controls.Page.Background%2A> свойства <xref:System.Windows.Controls.Page> элемента управления с помощью ключевых кадров.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> изменяет класс анимация цвета для <xref:System.Windows.Controls.Page.Background%2A> свойства <xref:System.Windows.Controls.Page> элемента управления. Пример времени изменяется цвет кисти фона через регулярные интервалы. Эта анимация использует <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> класса, чтобы создать три различных ключевых кадров. Анимация использует ключевые кадры следующим образом:  
  
1.  В конце первой секунды происходит анимация экземпляра <xref:System.Windows.Media.LinearGradientBrush> класса. В этом разделе примере применяется линейного градиента фоновый цвет, чтобы переход от желтого цвета на оранжевый, красный.  
  
2.  В конце следующей секунды происходит анимация экземпляра <xref:System.Windows.Media.RadialGradientBrush> класса. В этом разделе Пример применяется радиального градиента для цвета фона, чтобы переход от белого синего черного цвета.  
  
3.  В конце третьей секунды происходит анимация экземпляра <xref:System.Windows.Media.DrawingBrush> класса. В этом разделе примере применяется шаблон шахматной доски в фоновом режиме.  
  
4.  Анимация начинается снова и повторяется бесконечно.  
  
> [!NOTE]
>  <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> представляет собой единственный тип ключевого кадра, который можно использовать с <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> класса. Полные кадры, например <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> создают внезапные изменения в значениях, то есть, изменения цвета в этом примере происходит внезапное.  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.Page.Background%2A>  
 <xref:System.Windows.Controls.Page>  
 <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>  
 <xref:System.Windows.Media.LinearGradientBrush>  
 <xref:System.Windows.Media.RadialGradientBrush>  
 <xref:System.Windows.Media.DrawingBrush>  
 [Общие сведения об анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Практические руководства, посвященные анимации по ключевым кадрам](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
