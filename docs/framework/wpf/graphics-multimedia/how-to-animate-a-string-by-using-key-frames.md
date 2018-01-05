---
title: "Практическое руководство. Анимация строки с помощью ключевых кадров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1692777a97754fb7f6481b2d9cb8942dcb62df77
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a><span data-ttu-id="85f35-102">Практическое руководство. Анимация строки с помощью ключевых кадров</span><span class="sxs-lookup"><span data-stu-id="85f35-102">How to: Animate a String by Using Key Frames</span></span>
<span data-ttu-id="85f35-103">В этом примере показано, как анимация строки, который в данном примере — <xref:System.Windows.Controls.ContentControl.Content%2A> свойства <xref:System.Windows.Controls.Button> элемента управления с помощью ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="85f35-103">This example shows how to animate a string, which in this example is the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button> control, by using key frames.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85f35-104">Пример</span><span class="sxs-lookup"><span data-stu-id="85f35-104">Example</span></span>  
 <span data-ttu-id="85f35-105">В следующем примере используется <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> класса для анимации <xref:System.Windows.Controls.ContentControl.Content%2A> свойство <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="85f35-105">The following example uses the <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> class to animate the <xref:System.Windows.Controls.ContentControl.Content%2A> property of a <xref:System.Windows.Controls.Button>.</span></span>  
  
 <span data-ttu-id="85f35-106">Все ключевые кадры в этом примере используется экземпляр <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> класса, поскольку строка анимации, которая создается с помощью ключевых кадров может использовать только дискретные ключевых кадров.</span><span class="sxs-lookup"><span data-stu-id="85f35-106">All the key frames in this example use an instance of the <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> class because a string animation that is created with key frames can only use discrete key frames.</span></span> <span data-ttu-id="85f35-107">Дискретные полные кадры типа <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> создают резкие переходы между значениями, то есть, примет анимации происходят быстро, но заметно.</span><span class="sxs-lookup"><span data-stu-id="85f35-107">Discrete key frames like <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> create sudden jumps between values, that is, changes to the animation occur quickly and are not subtle.</span></span>  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 <span data-ttu-id="85f35-108">Описание полного примера см. в разделе [Пример анимации по ключевым кадрам](http://go.microsoft.com/fwlink/?LinkID=160012).</span><span class="sxs-lookup"><span data-stu-id="85f35-108">For the complete sample, see [KeyFrame Animation Sample](http://go.microsoft.com/fwlink/?LinkID=160012).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85f35-109">См. также</span><span class="sxs-lookup"><span data-stu-id="85f35-109">See Also</span></span>  
 <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>  
 <xref:System.Windows.Controls.ContentControl.Content%2A>  
 <xref:System.Windows.Controls.Button>  
 <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>  
 [<span data-ttu-id="85f35-110">Общие сведения об анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="85f35-110">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="85f35-111">Практические руководства, посвященные анимации по ключевым кадрам</span><span class="sxs-lookup"><span data-stu-id="85f35-111">Key-Frame How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animation-how-to-topics.md)
