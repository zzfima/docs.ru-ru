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
# <a name="how-to-animate-an-object-by-using-key-frames"></a><span data-ttu-id="d1770-102">Практическое руководство. Анимация объекта с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="d1770-102">How to: Animate an Object by Using Key Frames</span></span>
<span data-ttu-id="d1770-103">В этом примере показано, как анимировать объект, который в этом примере является <xref:System.Windows.Controls.Page.Background%2A> свойством <xref:System.Windows.Controls.Page> элемента управления, с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="d1770-103">This example shows how to animate an object, which in this example is the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1770-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d1770-104">Example</span></span>  
 <span data-ttu-id="d1770-105">В следующем примере <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> класс используется для анимации изменений цвета <xref:System.Windows.Controls.Page.Background%2A> для свойства <xref:System.Windows.Controls.Page> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d1770-105">The following example uses the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class to animate color changes for the <xref:System.Windows.Controls.Page.Background%2A> property of a <xref:System.Windows.Controls.Page> control.</span></span> <span data-ttu-id="d1770-106">В примере анимация изменяется на другую фоновую кисть через регулярные интервалы.</span><span class="sxs-lookup"><span data-stu-id="d1770-106">The example animation changes to a different background brush at regular intervals.</span></span> <span data-ttu-id="d1770-107">Эта анимация использует <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> класс для создания трех разных ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="d1770-107">This animation uses the <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> class to create three different key frames.</span></span> <span data-ttu-id="d1770-108">Анимация использует ключевые кадры следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d1770-108">The animation uses key frames in the following manner:</span></span>  
  
1. <span data-ttu-id="d1770-109">В конце первой секунды анимируется экземпляр <xref:System.Windows.Media.LinearGradientBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="d1770-109">At the end of the first second, animates an instance of the <xref:System.Windows.Media.LinearGradientBrush> class.</span></span> <span data-ttu-id="d1770-110">В этом разделе примера к цвету фона применяется линейный градиент, что позволяет цвету переходить от желтого к оранжевый к красному.</span><span class="sxs-lookup"><span data-stu-id="d1770-110">This section of the example applies a linear gradient to the background color so that the color transitions from yellow to orange to red.</span></span>  
  
2. <span data-ttu-id="d1770-111">В конце следующей секунды анимируется экземпляр <xref:System.Windows.Media.RadialGradientBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="d1770-111">At the end of the next second, animates an instance of the <xref:System.Windows.Media.RadialGradientBrush> class.</span></span> <span data-ttu-id="d1770-112">В этом разделе примера к цвету фона применяется радиальный градиент, чтобы цвет переменялся с белого на синий.</span><span class="sxs-lookup"><span data-stu-id="d1770-112">This section of the example applies a radial gradient to the background color so that the color transitions from white to blue to black.</span></span>  
  
3. <span data-ttu-id="d1770-113">В конце третьей секунды анимируется экземпляр <xref:System.Windows.Media.DrawingBrush> класса.</span><span class="sxs-lookup"><span data-stu-id="d1770-113">At the end of the third second, animates an instance of the <xref:System.Windows.Media.DrawingBrush> class.</span></span> <span data-ttu-id="d1770-114">В этом разделе примера к фону применяется шаблон шахматной доски.</span><span class="sxs-lookup"><span data-stu-id="d1770-114">This section of the example applies a checkerboard pattern to the background.</span></span>  
  
4. <span data-ttu-id="d1770-115">Анимация начинается снова и повторяется неограниченное время.</span><span class="sxs-lookup"><span data-stu-id="d1770-115">The animation begins again and repeats indefinitely.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d1770-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>— единственный тип ключевого кадра, который можно использовать с <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> классом.</span><span class="sxs-lookup"><span data-stu-id="d1770-116"><xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> is the only type of key frame that you can use with the <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> class.</span></span> <span data-ttu-id="d1770-117">Ключевые кадры, <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> такие как создание неожиданных изменений в значениях, то есть изменения цвета в этом примере происходят внезапно.</span><span class="sxs-lookup"><span data-stu-id="d1770-117">Key frames like <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame> create sudden changes in values, that is, the color changes in this example occur suddenly.</span></span>  
  
 [!code-xaml[keyframes_snip#ObjectAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/ObjectAnimationUsingKeyFramesExample.xaml#objectanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="d1770-118">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](https://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="d1770-118">For the complete sample, see [KeyFrame Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1770-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d1770-119">See also</span></span>

- <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.Page.Background%2A>
- <xref:System.Windows.Controls.Page>
- <xref:System.Windows.Media.Animation.DiscreteObjectKeyFrame>
- <xref:System.Windows.Media.LinearGradientBrush>
- <xref:System.Windows.Media.RadialGradientBrush>
- <xref:System.Windows.Media.DrawingBrush>
- [<span data-ttu-id="d1770-120">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="d1770-120">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="d1770-121">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="d1770-121">Key-Frame How-to Topics</span></span>](key-frame-animation-how-to-topics.md)
