---
title: Как выполнить Анимация толщины границы с помощью ключевых кадров
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], border thickness with key frames
- key frames [WPF], animating border thickness with
- border thickness [WPF], animating with key frames
ms.assetid: 3a9cb463-0a63-407d-aae7-3fbb1a559947
ms.openlocfilehash: d30e414dd83e596da6415cc455c599820a22f3e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689959"
---
# <a name="how-to-animate-the-thickness-of-a-border-by-using-key-frames"></a><span data-ttu-id="0338c-102">Как выполнить Анимация толщины границы с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="0338c-102">How to: Animate the Thickness of a Border by Using Key Frames</span></span>
<span data-ttu-id="0338c-103">В этом примере демонстрируется анимация <xref:System.Windows.Controls.Control.BorderThickness%2A> свойство <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="0338c-103">This example shows how to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0338c-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0338c-104">Example</span></span>  
 <span data-ttu-id="0338c-105">В следующем примере используется <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Controls.Control.BorderThickness%2A> свойство <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="0338c-105">The following example uses the <xref:System.Windows.Media.Animation.ThicknessAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.Control.BorderThickness%2A> property of a <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="0338c-106">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0338c-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="0338c-107">В течение первой половины секунды используется экземпляр <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> класс для постепенного увеличения толщины границы.</span><span class="sxs-lookup"><span data-stu-id="0338c-107">During the first half second, uses an instance of the <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> class to gradually increase the thickness of the border.</span></span> <span data-ttu-id="0338c-108">В примере используется <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> для создания гладкого линейного увеличения между значениями.</span><span class="sxs-lookup"><span data-stu-id="0338c-108">The example uses <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame> to create a smooth linear increase between values.</span></span>  
  
2.  <span data-ttu-id="0338c-109">В конце следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> класс для резкого увеличения толщины границы.</span><span class="sxs-lookup"><span data-stu-id="0338c-109">At the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> class to suddenly increase the thickness of the border.</span></span> <span data-ttu-id="0338c-110">Дискретные ключевые кадры, подобные производным от <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> , создают скачкообразные переходы между значениями, то есть, перемещение анимация выполняется рывками.</span><span class="sxs-lookup"><span data-stu-id="0338c-110">Discrete key frames like those derived from <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame> create sudden jumps between values, that is, the movement of the animation is jerky.</span></span>  
  
3.  <span data-ttu-id="0338c-111">В течение последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> класс для уменьшения толщины границы.</span><span class="sxs-lookup"><span data-stu-id="0338c-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> class to decrease the thickness of the border.</span></span> <span data-ttu-id="0338c-112">Ключевые кадры сплайна, подобные производным от <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> , создают переменный переход между значениями в соответствии со значениями из <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0338c-112">Spline key frames like those derived from <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="0338c-113">В этом опорном кадре анимация начинается медленно и экспоненциально ускоряется к концу временного сегмента.</span><span class="sxs-lookup"><span data-stu-id="0338c-113">In this key frame, the animation starts off slow and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-xaml[keyframes_snip#ThicknessAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ThicknessAnimationUsingKeyFramesExample.xaml#thicknessanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="0338c-114">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="0338c-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0338c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="0338c-115">See also</span></span>
- <xref:System.Windows.Media.Animation.LinearThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteThicknessKeyFrame>
- <xref:System.Windows.Media.Animation.SplineThicknessKeyFrame>
- [<span data-ttu-id="0338c-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="0338c-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)
- [<span data-ttu-id="0338c-117">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="0338c-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
- [<span data-ttu-id="0338c-118">Анимирование значения BorderThickness</span><span class="sxs-lookup"><span data-stu-id="0338c-118">Animate a BorderThickness Value</span></span>](../../../../docs/framework/wpf/controls/how-to-animate-a-borderthickness-value.md)
