---
title: Практическое руководство. Создание элемента Spin
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], spinning elements
- spinning elements [WPF]
ms.assetid: 1f011976-8b07-4c31-9faf-019e0ddaa24c
ms.openlocfilehash: a1b515822391de08ec8ed8ff0ff1f0086874dc02
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112080"
---
# <a name="how-to-make-an-element-spin-in-place"></a><span data-ttu-id="d5026-102">Практическое руководство. Создание элемента Spin</span><span class="sxs-lookup"><span data-stu-id="d5026-102">How to: Make an Element Spin in Place</span></span>
<span data-ttu-id="d5026-103">Этот пример показывает, как сделать <xref:System.Windows.Media.RotateTransform> элемент <xref:System.Windows.Media.Animation.DoubleAnimation>спина с помощью и .</span><span class="sxs-lookup"><span data-stu-id="d5026-103">This example shows how to make an element spin by using a <xref:System.Windows.Media.RotateTransform> and a <xref:System.Windows.Media.Animation.DoubleAnimation>.</span></span>  
  
 <span data-ttu-id="d5026-104">Следующий пример <xref:System.Windows.Media.RotateTransform> применяется <xref:System.Windows.UIElement.RenderTransform%2A> к свойству элемента.</span><span class="sxs-lookup"><span data-stu-id="d5026-104">The following example applies the <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span> <span data-ttu-id="d5026-105">Пример использует <xref:System.Windows.Media.Animation.DoubleAnimation> для анимировать <xref:System.Windows.Media.RotateTransform.Angle%2A> <xref:System.Windows.Media.RotateTransform>.</span><span class="sxs-lookup"><span data-stu-id="d5026-105">The example uses a <xref:System.Windows.Media.Animation.DoubleAnimation> to animate the <xref:System.Windows.Media.RotateTransform.Angle%2A> of the <xref:System.Windows.Media.RotateTransform>.</span></span> <span data-ttu-id="d5026-106">Чтобы элемент вращаться на месте, <xref:System.Windows.UIElement.RenderTransformOrigin%2A> пример устанавливает свойство элемента в точку (0,5, 0,5).</span><span class="sxs-lookup"><span data-stu-id="d5026-106">To make the element spin in place, the example sets the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property of the element to the point (0.5, 0.5).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5026-107">Пример</span><span class="sxs-lookup"><span data-stu-id="d5026-107">Example</span></span>  
 [!code-xaml[transformanimations_snip#11](~/samples/snippets/xaml/VS_Snippets_Wpf/transformanimations_snip/XAML/RotateAboutCenterExample.xaml#11)]  
  
 <span data-ttu-id="d5026-108">Для полного образца, который включает в себя больше примеров [трансформации, см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)</span><span class="sxs-lookup"><span data-stu-id="d5026-108">For the complete sample, which includes more transformation examples, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5026-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d5026-109">See also</span></span>

- [<span data-ttu-id="d5026-110">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="d5026-110">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="d5026-111">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="d5026-111">Transforms Overview</span></span>](transforms-overview.md)
