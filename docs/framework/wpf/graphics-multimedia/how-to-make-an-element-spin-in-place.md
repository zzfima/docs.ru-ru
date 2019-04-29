---
title: Практическое руководство. Создание элемента Spin
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: aca9bd577f2882e31e8d49abe5eeb5ade86f95f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947258"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="0952a-102">Практическое руководство. Создание элемента Spin</span><span class="sxs-lookup"><span data-stu-id="0952a-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="0952a-103">В этом примере показано, как создать элемент spin с помощью <xref:System.Windows.Media.RotateTransform> и <xref:System.Windows.Media.Animation.DoubleAnimation>.</span><span class="sxs-lookup"><span data-stu-id="0952a-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="0952a-104">В следующем примере применяется <xref:System.Windows.Media.RotateTransform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойство элемента.</span><span class="sxs-lookup"><span data-stu-id="0952a-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="0952a-105">В примере используется <xref:System.Windows.Media.Animation.DoubleAnimation> для анимации <xref:System.Windows.Media.RotateTransform.Angle%2A> из <xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="0952a-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="0952a-106">Чтобы сделать элемент spin на месте, в этом примере <xref:System.Windows.UIElement.RenderTransformOrigin%2A> свойство элемента до точки (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="0952a-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0952a-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0952a-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="0952a-108">Полный пример, который включает дополнительные примеры преобразования, см. в разделе [2 примеров](https://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="0952a-108">For the complete sample, which includes more transformation examples, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0952a-109">См. также</span><span class="sxs-lookup"><span data-stu-id="0952a-109">See also</span></span>

- [<span data-ttu-id="0952a-110">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="0952a-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="0952a-111">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="0952a-111">Transforms Overview</span></span>](transforms-overview.md)
