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
ms.workload: dotnet
ms.openlocfilehash: 4c6b4dc6ee04b20f47599bad84dda4648da255ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-color-by-using-key-frames"></a><span data-ttu-id="e0da2-102">Практическое руководство. Анимация цвета с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="e0da2-102">How to: Animate Color by Using Key Frames</span></span>
<span data-ttu-id="e0da2-103">В этом примере демонстрируется анимация <xref:System.Windows.Media.SolidColorBrush.Color%2A> из <xref:System.Windows.Media.SolidColorBrush> с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="e0da2-103">This example shows how to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> of a <xref:System.Windows.Media.SolidColorBrush> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0da2-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e0da2-104">Example</span></span>  
 <span data-ttu-id="e0da2-105">В следующем примере используется <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Media.SolidColorBrush.Color%2A> свойство <xref:System.Windows.Media.SolidColorBrush>.</span><span class="sxs-lookup"><span data-stu-id="e0da2-105">The following example uses the <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.SolidColorBrush.Color%2A> property of a <xref:System.Windows.Media.SolidColorBrush>.</span></span> <span data-ttu-id="e0da2-106">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e0da2-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="e0da2-107">В течение первых двух секунд используется экземпляр <xref:System.Windows.Media.Animation.LinearColorKeyFrame> класс постепенно изменение цвета зеленый или красный.</span><span class="sxs-lookup"><span data-stu-id="e0da2-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearColorKeyFrame> class to gradually change the color from green to red.</span></span> <span data-ttu-id="e0da2-108">Линейный ключевые кадры, такие как <xref:System.Windows.Media.Animation.LinearColorKeyFrame> Создание линейной плавный переход между значениями.</span><span class="sxs-lookup"><span data-stu-id="e0da2-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearColorKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="e0da2-109">Во время окончания следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> класса для быстрого изменения цвета с красного на желтый.</span><span class="sxs-lookup"><span data-stu-id="e0da2-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> class to quickly change the color from red to yellow.</span></span> <span data-ttu-id="e0da2-110">Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> создают внезапные изменения между значениями, то есть, изменение цвета в этой части анимации происходит быстро, но заметно.</span><span class="sxs-lookup"><span data-stu-id="e0da2-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteColorKeyFrame> create sudden changes between values, that is, the color change in this part of the animation occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="e0da2-111">В течение последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineColorKeyFrame> классе, чтобы изменить цвет снова — времени с момента обратной желтый зеленый цвет.</span><span class="sxs-lookup"><span data-stu-id="e0da2-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame> class to change the color again—this time from yellow back to green.</span></span> <span data-ttu-id="e0da2-112">Как и опорных кадров сплайна <xref:System.Windows.Media.Animation.SplineColorKeyFrame> создания переменного перехода между значениями согласно значениям <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e0da2-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineColorKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineColorKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="e0da2-113">В этом примере изменение цвета начинается медленно и ускоряется экспоненциально к концу временного сегмента.</span><span class="sxs-lookup"><span data-stu-id="e0da2-113">In this example, the change in color begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/ColorAnimationUsingKeyFramesExample.cs#coloranimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/coloranimationusingkeyframesexample.vb#coloranimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#ColorAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ColorAnimationUsingKeyFramesExample.xaml#coloranimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="e0da2-114">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="e0da2-114">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0da2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e0da2-115">See Also</span></span>  
 <xref:System.Windows.Media.SolidColorBrush.Color%2A>  
 <xref:System.Windows.Media.SolidColorBrush>  
 <xref:System.Windows.Media.Animation.ColorAnimationUsingKeyFrames>  
 [<span data-ttu-id="e0da2-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="e0da2-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="e0da2-117">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="e0da2-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
