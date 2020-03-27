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
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="a33e8-102">Инструкция по Анимации толщины границы с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="a33e8-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="a33e8-103">Этот пример показывает, как <xref:System.Windows.Controls.Control.BorderThickness%2A> оживить свойство <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="a33e8-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a33e8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a33e8-104">Example</span></span>  
 <span data-ttu-id="a33e8-105">В следующем примере <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> используется класс <xref:System.Windows.Controls.Control.BorderThickness%2A> для анимировать свойство <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="a33e8-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="a33e8-106">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a33e8-106">This animation uses three key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="a33e8-107">В течение первой половины второй, <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> использует экземпляр класса постепенно увеличивать толщину границы.</span><span class="sxs-lookup"><span data-stu-id="a33e8-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="a33e8-108">Пример использует <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> для создания плавного линейного увеличения между значениями.</span><span class="sxs-lookup"><span data-stu-id="a33e8-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2. <span data-ttu-id="a33e8-109">В конце следующей половины секунды, <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> использует экземпляр класса, чтобы внезапно увеличить толщину границы.</span><span class="sxs-lookup"><span data-stu-id="a33e8-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="a33e8-110">Дискретные ключевые кадры, <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> подобные тем, которые получены в ходе создания резких скачков между значениями, то есть движение анимации отрывисто.</span><span class="sxs-lookup"><span data-stu-id="a33e8-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3. <span data-ttu-id="a33e8-111">В течение последних двух секунд, <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> использует экземпляр класса, чтобы уменьшить толщину границы.</span><span class="sxs-lookup"><span data-stu-id="a33e8-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="a33e8-112">Ключевые кадры Spline, <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> подобные тем, которые получены из создания <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> переменного перехода между значениями в соответствии со значениями свойства.</span><span class="sxs-lookup"><span data-stu-id="a33e8-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="a33e8-113">В этом опорном кадре анимация начинается медленно и экспоненциально ускоряется к концу временного сегмента.</span><span class="sxs-lookup"><span data-stu-id="a33e8-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="a33e8-114">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="a33e8-114">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a33e8-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a33e8-115">See also</span></span>

- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="a33e8-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="a33e8-116">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="a33e8-117">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="a33e8-117">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="a33e8-118">Анимирование значения BorderThickness</span><span class="sxs-lookup"><span data-stu-id="a33e8-118">Animate a BorderThickness Value</span></span>](../controls/how-to-animate-a-borderthickness-value.md)
