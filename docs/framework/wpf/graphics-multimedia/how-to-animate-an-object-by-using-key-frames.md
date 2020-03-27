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
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="e6694-102">Практическое руководство. Анимация объекта с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="e6694-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="e6694-103">Этот пример показывает, как оживить объект, который в <xref:System.Windows.Controls.Page.Background%2A> этом <xref:System.Windows.Controls.Page> примере является свойством элемента управления, с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="e6694-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6694-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e6694-104">Example</span></span>  
 <span data-ttu-id="e6694-105">В следующем примере <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> используется класс для анимировать изменения цвета для <xref:System.Windows.Controls.Page.Background%2A> свойства элемента <xref:System.Windows.Controls.Page> управления.</span><span class="sxs-lookup"><span data-stu-id="e6694-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="e6694-106">Пример анимации меняется на другую фоновом уистику через регулярные промежутки времени.</span><span class="sxs-lookup"><span data-stu-id="e6694-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="e6694-107">Эта анимация <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> использует класс для создания трех различных ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="e6694-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="e6694-108">Анимация использует ключевые кадры следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e6694-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="e6694-109">В конце первой секунды, анимирует экземпляр <xref:System.Windows.Media.LinearGradientBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="e6694-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="e6694-110">В этом разделе пример применяется линейный градиент к цвету фона, так что цвет переходит от желтого к оранжевому на красный.</span><span class="sxs-lookup"><span data-stu-id="e6694-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="e6694-111">В конце следующей секунды, анимирует <xref:System.Windows.Media.RadialGradientBrush> экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="e6694-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="e6694-112">В этом разделе пример применяется радиальный градиент к цвету фона, так что цвет переходит от белого к белому к черному.</span><span class="sxs-lookup"><span data-stu-id="e6694-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="e6694-113">В конце третьей секунды, оживляет <xref:System.Windows.Media.DrawingBrush> экземпляр класса.</span><span class="sxs-lookup"><span data-stu-id="e6694-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="e6694-114">В этом разделе пример применяется шаблон зачекане.</span><span class="sxs-lookup"><span data-stu-id="e6694-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="e6694-115">Анимация начинается снова и повторяется бесконечно.</span><span class="sxs-lookup"><span data-stu-id="e6694-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e6694-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>является единственным типом ключа кадра, <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> который можно использовать с классом.</span><span class="sxs-lookup"><span data-stu-id="e6694-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="e6694-117">Ключевые кадры, такие как <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> создают внезапные изменения значений, то есть изменения цвета в этом примере происходят внезапно.</span><span class="sxs-lookup"><span data-stu-id="e6694-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="e6694-118">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span><span class="sxs-lookup"><span data-stu-id="e6694-118">For the complete sample, see [KeyFrame Animation Sample](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6694-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e6694-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="e6694-120">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="e6694-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="e6694-121">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="e6694-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
