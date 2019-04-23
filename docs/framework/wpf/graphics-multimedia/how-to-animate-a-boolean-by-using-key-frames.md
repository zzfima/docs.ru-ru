---
title: Практическое руководство. Анимация логического значения с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 59a72916721cccbe66f704253f148828fa8cd418
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175036"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a><span data-ttu-id="130cb-102">Практическое руководство. Анимация логического значения с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="130cb-102">How to: Animate a Boolean by Using Key Frames</span></span>
<span data-ttu-id="130cb-103">В этом примере показано, как анимировать значение логического свойства <xref:System.Windows.Controls.Button> элемента управления с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="130cb-103">This example shows how to animate the Boolean property value of a <xref:System.Windows.Controls.Button> control by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="130cb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="130cb-104">Example</span></span>  
 <span data-ttu-id="130cb-105">В следующем примере используется <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.UIElement.IsEnabled%2A> свойство <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="130cb-105">The following example uses the <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> class to animate the <xref:System.Windows.UIElement.IsEnabled%2A> property of a <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="130cb-106">Все ключевые кадры в этом примере использует экземпляр <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> класса.</span><span class="sxs-lookup"><span data-stu-id="130cb-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> class.</span></span> <span data-ttu-id="130cb-107">Дискретные ключевые кадры, например <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> , создают скачкообразные переходы между значениями, то есть, перемещение анимация выполняется рывками.</span><span class="sxs-lookup"><span data-stu-id="130cb-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="130cb-108">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="130cb-108">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="130cb-109">См. также</span><span class="sxs-lookup"><span data-stu-id="130cb-109">See also</span></span>

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="130cb-110">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="130cb-110">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="130cb-111">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="130cb-111">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
