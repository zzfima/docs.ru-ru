---
title: "Практическое руководство. Проверка нажатия с использованием геометрического объекта в качестве параметра"
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
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b5c5bb47e3f435419bcf3c472f052260adec7c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="0abcf-102">Практическое руководство. Проверка нажатия с использованием геометрического объекта в качестве параметра</span><span class="sxs-lookup"><span data-stu-id="0abcf-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="0abcf-103">В этом примере показано, как выполнять проверки нажатия визуального объекта при помощи <xref:System.Windows.Media.Geometry> параметра проверки нажатия.</span><span class="sxs-lookup"><span data-stu-id="0abcf-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0abcf-104">Пример</span><span class="sxs-lookup"><span data-stu-id="0abcf-104">Example</span></span>  
 <span data-ttu-id="0abcf-105">Приведенный ниже показано, как настроить нажатия, используя <xref:System.Windows.Media.GeometryHitTestParameters> для <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="0abcf-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="0abcf-106"><xref:System.Windows.Point> Значение, передаваемое `OnMouseDown` метод используется для создания <xref:System.Windows.Media.Geometry> объекта, чтобы расширить диапазон проверки нажатия.</span><span class="sxs-lookup"><span data-stu-id="0abcf-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="0abcf-107"><xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> Свойство <xref:System.Windows.Media.GeometryHitTestResult> предоставляет сведения о результатах проверки нажатия, который использует <xref:System.Windows.Media.Geometry> параметра проверки нажатия.</span><span class="sxs-lookup"><span data-stu-id="0abcf-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="0abcf-108">На следующем рисунке показана связь между геометрическим объектом проверки нажатия (синий круг) и отображенным содержимым целевого визуального объекта (красный квадрат).</span><span class="sxs-lookup"><span data-stu-id="0abcf-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 <span data-ttu-id="0abcf-109">![Схема IntersectionDetail, используемая в проверке нажатия](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")</span><span class="sxs-lookup"><span data-stu-id="0abcf-109">![Diagram of IntersectionDetail used in hit testing](../../../../docs/framework/wpf/graphics-multimedia/media/intersectiondetail01.png "IntersectionDetail01")</span></span>  
<span data-ttu-id="0abcf-110">Пересечение между геометрическим объектом проверки попадания и целевым визуальным объектом</span><span class="sxs-lookup"><span data-stu-id="0abcf-110">Intersection between hit test geometry and target visual object</span></span>  
  
 <span data-ttu-id="0abcf-111">В следующем примере показано, как для реализации обратного вызова проверки нажатия при <xref:System.Windows.Media.Geometry> используется в качестве параметра проверки нажатия.</span><span class="sxs-lookup"><span data-stu-id="0abcf-111">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="0abcf-112">`result` Параметр приведен к <xref:System.Windows.Media.GeometryHitTestResult> для извлечения значения <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0abcf-112">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="0abcf-113">Значение свойства позволяет определить, если <xref:System.Windows.Media.Geometry> параметра проверки нажатия полностью или частично находится в пределах отображаемого содержимого целевой объект проверки нажатия.</span><span class="sxs-lookup"><span data-stu-id="0abcf-113">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="0abcf-114">В этом случае пример кода только добавляет результаты проверки попадания в список визуальных объектов, которые полностью содержатся в пределах границ целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="0abcf-114">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
>  <span data-ttu-id="0abcf-115"><xref:System.Windows.Media.HitTestResult> Обратного вызова не должен вызываться, если пересечение подробные <xref:System.Windows.Media.IntersectionDetail.Empty>.</span><span class="sxs-lookup"><span data-stu-id="0abcf-115">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0abcf-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0abcf-116">See Also</span></span>  
 [<span data-ttu-id="0abcf-117">Проверка нажатия на визуальном уровне</span><span class="sxs-lookup"><span data-stu-id="0abcf-117">Hit Testing in the Visual Layer</span></span>](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [<span data-ttu-id="0abcf-118">Проверка попадания геометрического объекта в визуальный объект</span><span class="sxs-lookup"><span data-stu-id="0abcf-118">Hit Test Geometry in a Visual</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-geometry-in-a-visual.md)
