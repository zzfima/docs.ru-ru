---
title: Практическое руководство. Закраска области с применением радиального градиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], painting with radial gradients
- radial gradients [WPF], painting with
- painting [WPF], with radial gradients
ms.assetid: b5d0fc8a-8986-4796-b003-a75b41a48928
ms.openlocfilehash: 75c28cd19ec0423589b6485884842468b89b5e8c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526795"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="b52df-102">Практическое руководство. Закраска области с применением радиального градиента</span><span class="sxs-lookup"><span data-stu-id="b52df-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="b52df-103">В этом примере показано, как использовать <xref:System.Windows.Media.RadialGradientBrush> класс для закраски области с применением радиального градиента.</span><span class="sxs-lookup"><span data-stu-id="b52df-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b52df-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b52df-104">Example</span></span>  
 <span data-ttu-id="b52df-105">В следующем примере используется <xref:System.Windows.Media.RadialGradientBrush> для закрашивания прямоугольника с применением радиального градиента, которая переходит с желтого красного, синего и зеленого.</span><span class="sxs-lookup"><span data-stu-id="b52df-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="b52df-106">На рисунке показан градиент из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="b52df-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="b52df-107">Выделены градиента.</span><span class="sxs-lookup"><span data-stu-id="b52df-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="b52df-108">![Ограничения градиента в радиальном градиенте](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="b52df-108">![Gradient stops in a radial gradient](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b52df-109">В примерах в этом разделе используется система координат по умолчанию для задания точек управления.</span><span class="sxs-lookup"><span data-stu-id="b52df-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="b52df-110">По умолчанию система координат определяется относительно ограничивающего прямоугольника: 0 указывает 0 процентов ограничивающего прямоугольника, а 1 указывает 100 процентов ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="b52df-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="b52df-111">Эту систему координат можно изменить, задав <xref:System.Windows.Media.GradientBrush.MappingMode%2A> в соответствии с значением <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="b52df-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="b52df-112">Абсолютная система координат не привязана к ограничивающему прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="b52df-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="b52df-113">Значения интерпретируются непосредственно в локальной области.</span><span class="sxs-lookup"><span data-stu-id="b52df-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="b52df-114">Для дополнительных <xref:System.Windows.Media.RadialGradientBrush> примеры, см. в разделе [пример использования кистей](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="b52df-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="b52df-115">Дополнительные сведения о градиенты и других типов кистей см. в разделе [закраске сплошным цветом и градиентом Обзор](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b52df-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md).</span></span>
