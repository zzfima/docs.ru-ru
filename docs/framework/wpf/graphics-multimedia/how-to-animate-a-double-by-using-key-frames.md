---
title: "Инструкция по Анимации типа Double с помощью ключевых кадров"
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
- Doubles [WPF], animating with key frames
- animation [WPF], Doubles with key frames
- key frames [WPF], animating Doubles with
ms.assetid: 3a1a7dba-7694-4907-8a2f-3408baebfa82
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e87717f6e2691142efa54a7e363f1038f8b74c1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-double-by-using-key-frames"></a><span data-ttu-id="5c116-102">Инструкция по Анимации типа Double с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="5c116-102">How to: Animate a Double by Using Key Frames</span></span>
<span data-ttu-id="5c116-103">В этом примере показано, как анимация значения свойства, которое принимает <xref:System.Double> с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="5c116-103">This example shows how to animate the value of a property that takes a <xref:System.Double> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c116-104">Пример</span><span class="sxs-lookup"><span data-stu-id="5c116-104">Example</span></span>  
 <span data-ttu-id="5c116-105">В следующем примере прямоугольник перемещается по экрану.</span><span class="sxs-lookup"><span data-stu-id="5c116-105">The following example moves a rectangle across a screen.</span></span> <span data-ttu-id="5c116-106">В этом примере <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Media.TranslateTransform.X%2A> свойство <xref:System.Windows.Media.TranslateTransform> применены к <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="5c116-106">The example uses the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.TranslateTransform.X%2A> property of a <xref:System.Windows.Media.TranslateTransform> applied to a <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="5c116-107">Эта анимация, которая бесконечно повторяется, использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5c116-107">This animation, which repeats indefinitely, uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="5c116-108">В течение первых трех секунд используется экземпляр <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> класс, чтобы переместить прямоугольник в пути с постоянной скоростью из его начальной позиции в позиции 500.</span><span class="sxs-lookup"><span data-stu-id="5c116-108">During the first three seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> class to move the rectangle along a path at a steady rate from its starting position to the 500 position.</span></span> <span data-ttu-id="5c116-109">Линейный ключевые кадры, такие как <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> Создание линейной плавный переход между значениями.</span><span class="sxs-lookup"><span data-stu-id="5c116-109">Linear key frames like <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="5c116-110">В конце четвертый второй используется экземпляр <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> класс внезапно Перемещение прямоугольника до следующей позиции.</span><span class="sxs-lookup"><span data-stu-id="5c116-110">At the end of the fourth second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> class to suddenly move the rectangle to the next position.</span></span> <span data-ttu-id="5c116-111">Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> создают резкие переходы между значениями.</span><span class="sxs-lookup"><span data-stu-id="5c116-111">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame> create sudden jumps between values.</span></span> <span data-ttu-id="5c116-112">В этом примере прямоугольник находится в начальной позиции, а затем внезапно появляется в позиции 500.</span><span class="sxs-lookup"><span data-stu-id="5c116-112">In this example, the rectangle is at the starting position and then suddenly appears at the 500 position.</span></span>  
  
3.  <span data-ttu-id="5c116-113">В последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> класса, чтобы переместить прямоугольник обратно в исходное положение.</span><span class="sxs-lookup"><span data-stu-id="5c116-113">In the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> class to move the rectangle back to its starting position.</span></span> <span data-ttu-id="5c116-114">Как и опорных кадров сплайна <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> создания переменного перехода между значениями в соответствии со значением <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="5c116-114">Spline key frames like <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame> create a variable transition between values according to the value of the <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="5c116-115">В этом примере прямоугольник начинает двигаться медленно и ускоряется экспоненциально к концу временного отрезка.</span><span class="sxs-lookup"><span data-stu-id="5c116-115">In this example, the rectangle begins by moving slowly and then speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/AltDoubleAnimationUsingKeyFramesExample.cs#altdoubleanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/altdoubleanimationusingkeyframesexample.vb#altdoubleanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#AltDoubleAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/AltDoubleAnimationUsingKeyFramesExample.xaml#altdoubleanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="5c116-116">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="5c116-116">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
 <span data-ttu-id="5c116-117">Для совместимости с другими примерами анимации версии кода этого примера используют <xref:System.Windows.Media.Animation.Storyboard> объекта для применения <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span><span class="sxs-lookup"><span data-stu-id="5c116-117">For consistency with other animation examples, the code versions of this example use a <xref:System.Windows.Media.Animation.Storyboard> object to apply the <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>.</span></span> <span data-ttu-id="5c116-118">Кроме того, при применении одной анимации в коде, проще использовать <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> метод вместо <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="5c116-118">Alternatively, when applying a single animation in code, it is simpler to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method instead of using a <xref:System.Windows.Media.Animation.Storyboard>.</span></span> <span data-ttu-id="5c116-119">Пример см. в разделе [Анимация свойства без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span><span class="sxs-lookup"><span data-stu-id="5c116-119">For an example, see [Animate a Property Without Using a Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c116-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5c116-120">See Also</span></span>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Shapes.Rectangle>  
 <xref:System.Windows.Media.Animation.LinearDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.DiscreteDoubleKeyFrame>  
 <xref:System.Windows.Media.Animation.SplineDoubleKeyFrame>  
 [<span data-ttu-id="5c116-121">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="5c116-121">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="5c116-122">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="5c116-122">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
