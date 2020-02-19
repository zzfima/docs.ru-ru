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
ms.openlocfilehash: 8a53d5d7247f82905816265f7c92b22f287591c5
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452757"
---
# <a name="how-to-paint-an-area-with-a-radial-gradient"></a><span data-ttu-id="9b399-102">Практическое руководство. Закраска области с применением радиального градиента</span><span class="sxs-lookup"><span data-stu-id="9b399-102">How to: Paint an Area with a Radial Gradient</span></span>
<span data-ttu-id="9b399-103">В этом примере показано, как использовать класс <xref:System.Windows.Media.RadialGradientBrush> для заливки области с радиальным градиентом.</span><span class="sxs-lookup"><span data-stu-id="9b399-103">This example shows how to use the <xref:System.Windows.Media.RadialGradientBrush> class to paint an area with a radial gradient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b399-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9b399-104">Example</span></span>  
 <span data-ttu-id="9b399-105">В следующем примере используется <xref:System.Windows.Media.RadialGradientBrush> для рисования прямоугольника с радиальным градиентом, который переходит от желтого к красному к темному зеленому.</span><span class="sxs-lookup"><span data-stu-id="9b399-105">The following example uses a <xref:System.Windows.Media.RadialGradientBrush> to paint a rectangle with a radial gradient that transitions from yellow to red to blue to lime green.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/RadialGradientBrushSnippet.cs#simpleradialgradientexamplewholepage)]
 [!code-vb[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/radialgradientbrushsnippet.vb#simpleradialgradientexamplewholepage)]
 [!code-xaml[BrushesIntroduction_snip#SimpleRadialGradientExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/RadialGradientBrushSnippet.xaml#simpleradialgradientexamplewholepage)]  
  
 <span data-ttu-id="9b399-106">На следующем рисунке показан градиент из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="9b399-106">The following illustration shows the gradient from the preceding example.</span></span> <span data-ttu-id="9b399-107">Выделены точки останова градиента.</span><span class="sxs-lookup"><span data-stu-id="9b399-107">The gradient's stops have been highlighted.</span></span>  
  
 <span data-ttu-id="9b399-108">![Остановки градиента в радиальном градиенте](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span><span class="sxs-lookup"><span data-stu-id="9b399-108">![Gradient stops in a radial gradient](./media/wcpsdk-graphicsmm-4gradientstops-rg.png "wcpsdk_graphicsmm_4gradientstops_rg")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b399-109">В примерах этого раздела используется система координат по умолчанию для установки контрольных точек.</span><span class="sxs-lookup"><span data-stu-id="9b399-109">The examples in this topic use the default coordinate system for setting control points.</span></span> <span data-ttu-id="9b399-110">Система координат по умолчанию задается относительно ограничивающего прямоугольника: 0 указывает 0 процентов ограничивающего прямоугольника, а 1 — 100 процентов ограничивающего прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="9b399-110">The default coordinate system is relative to a bounding box: 0 indicates 0 percent of the bounding box, and 1 indicates 100 percent of the bounding box.</span></span> <span data-ttu-id="9b399-111">Вы можете изменить эту систему координат, задав для свойства <xref:System.Windows.Media.GradientBrush.MappingMode%2A> значение <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span><span class="sxs-lookup"><span data-stu-id="9b399-111">You can change this coordinate system by setting the <xref:System.Windows.Media.GradientBrush.MappingMode%2A> property to the value <xref:System.Windows.Media.BrushMappingMode.Absolute>.</span></span> <span data-ttu-id="9b399-112">Абсолютная система координат не привязана к ограничивающему прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="9b399-112">An absolute coordinate system is not relative to a bounding box.</span></span> <span data-ttu-id="9b399-113">Значения интерпретируются непосредственно в локальной области.</span><span class="sxs-lookup"><span data-stu-id="9b399-113">Values are interpreted directly in local space.</span></span>  
  
 <span data-ttu-id="9b399-114">Дополнительные <xref:System.Windows.Media.RadialGradientBrush> примеры см. в разделе [Пример использования кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="9b399-114">For additional <xref:System.Windows.Media.RadialGradientBrush> examples, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="9b399-115">Дополнительные сведения о градиентах и других типах кистей см. [в статье Общие сведения о рисовании с помощью сплошных цветов и градиентов](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9b399-115">For more information about gradients and other types of brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>
