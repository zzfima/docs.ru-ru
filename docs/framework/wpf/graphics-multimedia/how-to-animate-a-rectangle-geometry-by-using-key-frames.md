---
title: Практическое руководство. Анимация прямоугольника с помощью ключевых кадров
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- key frames [WPF], animating RectangleGeometry objects with
- RectangleGeometry objects [WPF], animating with key frames
- animation [WPF], RectangleGeometry objects with key frames
ms.assetid: a8b45ceb-0e32-4ba1-928f-df6d30db17c6
ms.openlocfilehash: 9b4a620ea58026c3be1b09d01a595e965e4c2b45
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2018
ms.locfileid: "44365177"
---
# <a name="how-to-animate-a-rectangle-geometry-by-using-key-frames"></a><span data-ttu-id="9e703-102">Практическое руководство. Анимация прямоугольника с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="9e703-102">How to: Animate a Rectangle Geometry by Using Key Frames</span></span>
<span data-ttu-id="9e703-103">В этом примере демонстрируется анимация <xref:System.Windows.Media.RectangleGeometry.Rect%2A> свойство <xref:System.Windows.Media.RectangleGeometry> с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="9e703-103">This example shows how to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry> by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e703-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9e703-104">Example</span></span>  
 <span data-ttu-id="9e703-105">В следующем примере используется <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> класс для анимации <xref:System.Windows.Media.RectangleGeometry.Rect%2A> свойство <xref:System.Windows.Media.RectangleGeometry>.</span><span class="sxs-lookup"><span data-stu-id="9e703-105">The following example uses the <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Media.RectangleGeometry.Rect%2A> property of a <xref:System.Windows.Media.RectangleGeometry>.</span></span> <span data-ttu-id="9e703-106">Эта анимация использует три ключевых кадра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9e703-106">This animation uses three key frames in the following manner:</span></span>  
  
1.  <span data-ttu-id="9e703-107">В течение первых двух секунд используется экземпляр <xref:System.Windows.Media.Animation.LinearRectKeyFrame> класс для анимации к плавному изменению в позицию, ширину и высоту прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="9e703-107">During the first two seconds, uses an instance of the <xref:System.Windows.Media.Animation.LinearRectKeyFrame> class to animate a gradual change in the position, width, and height of a rectangle.</span></span> <span data-ttu-id="9e703-108">Линейные ключевые кадры, например <xref:System.Windows.Media.Animation.LinearRectKeyFrame> создать плавный линейный переход между значениями.</span><span class="sxs-lookup"><span data-stu-id="9e703-108">Linear key frames like <xref:System.Windows.Media.Animation.LinearRectKeyFrame> create a smooth linear transition between values.</span></span>  
  
2.  <span data-ttu-id="9e703-109">В конце следующей половины секунды используется экземпляр <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> класс для резкого уменьшения высоты прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="9e703-109">During the end of the next half second, uses an instance of the <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> class to suddenly decrease the height of the rectangle.</span></span> <span data-ttu-id="9e703-110">Дискретные ключевые кадры, например <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> создают резкие изменения значений, то есть, уменьшение высоты происходит быстро и не плавно.</span><span class="sxs-lookup"><span data-stu-id="9e703-110">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteRectKeyFrame> create sudden changes between values, that is, the decrease in height occurs quickly and is not subtle.</span></span>  
  
3.  <span data-ttu-id="9e703-111">В течение последних двух секунд используется экземпляр <xref:System.Windows.Media.Animation.SplineRectKeyFrame> класс, чтобы изменить прямоугольника обратно на исходный размер и положение.</span><span class="sxs-lookup"><span data-stu-id="9e703-111">During the final two seconds, uses an instance of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame> class to change the rectangle back to its original size and position.</span></span> <span data-ttu-id="9e703-112">Ключевые кадры сплайна, например <xref:System.Windows.Media.Animation.SplineRectKeyFrame> , создают переменный переход между значениями в соответствии со значениями из <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="9e703-112">Spline key frames like <xref:System.Windows.Media.Animation.SplineRectKeyFrame> create a variable transition between values according to the values of the <xref:System.Windows.Media.Animation.SplineRectKeyFrame.KeySpline%2A> property.</span></span> <span data-ttu-id="9e703-113">В этом примере изменение начинается медленно и ускоряется экспоненциально к концу временного сегмента.</span><span class="sxs-lookup"><span data-stu-id="9e703-113">In this example, the change begins slowly and speeds up exponentially toward the end of the time segment.</span></span>  
  
 [!code-csharp[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/RectAnimationUsingKeyFramesExample.cs#rectanimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/rectanimationusingkeyframesexample.vb#rectanimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#RectAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/RectAnimationUsingKeyFramesExample.xaml#rectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="9e703-114">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="9e703-114">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e703-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9e703-115">See Also</span></span>  
 <xref:System.Windows.Media.RectangleGeometry>  
 <xref:System.Windows.Media.RectangleGeometry.Rect%2A>  
 <xref:System.Windows.Media.Animation.RectAnimationUsingKeyFrames>  
 [<span data-ttu-id="9e703-116">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="9e703-116">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="9e703-117">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="9e703-117">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
