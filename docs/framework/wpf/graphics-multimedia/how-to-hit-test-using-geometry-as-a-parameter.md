---
title: Практическое руководство. Проверка нажатия с использованием геометрии в качестве параметра
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects using Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], hit tests on visual objects [WPF]
ms.assetid: 6c8bdbf2-19e0-4fbb-bf89-c1252b2ebc61
ms.openlocfilehash: 8bed7784b00f49178c9a87def74b62f7ce620ec7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923406"
---
# <a name="how-to-hit-test-using-geometry-as-a-parameter"></a><span data-ttu-id="26651-102">Практическое руководство. Проверка нажатия с использованием геометрии в качестве параметра</span><span class="sxs-lookup"><span data-stu-id="26651-102">How to: Hit Test Using Geometry as a Parameter</span></span>
<span data-ttu-id="26651-103">В этом примере показано, как выполнить проверку нажатия для визуального объекта, <xref:System.Windows.Media.Geometry> используя в качестве параметра проверки нажатия.</span><span class="sxs-lookup"><span data-stu-id="26651-103">This example shows how to perform a hit test on a visual object using a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26651-104">Пример</span><span class="sxs-lookup"><span data-stu-id="26651-104">Example</span></span>  
 <span data-ttu-id="26651-105">В следующем примере показано, как настроить проверку нажатия с помощью <xref:System.Windows.Media.GeometryHitTestParameters> <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="26651-105">The following example shows how to set up a hit test using <xref:System.Windows.Media.GeometryHitTestParameters> for the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method.</span></span> <span data-ttu-id="26651-106">Значение, передаваемое `OnMouseDown` в метод <xref:System.Windows.Media.Geometry> , используется для создания объекта, чтобы расширить диапазон проверки нажатия. <xref:System.Windows.Point></span><span class="sxs-lookup"><span data-stu-id="26651-106">The <xref:System.Windows.Point> value that is passed to the `OnMouseDown` method is used to create a <xref:System.Windows.Media.Geometry> object in order to expand the range of the hit test.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet10)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet10)]  
  
 <span data-ttu-id="26651-107">Свойство объекта <xref:System.Windows.Media.GeometryHitTestResult> предоставляет сведения о результатах проверки попадания, которая использует в <xref:System.Windows.Media.Geometry> качестве параметра проверки нажатия. <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A></span><span class="sxs-lookup"><span data-stu-id="26651-107">The <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property of <xref:System.Windows.Media.GeometryHitTestResult> provides information about the results of a hit test that uses a <xref:System.Windows.Media.Geometry> as a hit test parameter.</span></span> <span data-ttu-id="26651-108">На следующем рисунке показана связь между геометрическим объектом проверки нажатия (синий круг) и отображенным содержимым целевого визуального объекта (красный квадрат).</span><span class="sxs-lookup"><span data-stu-id="26651-108">The following illustration shows the relationship between the hit test geometry (the blue circle) and the rendered content of the target visual object (the red square).</span></span>  
  
 ![Схема, на которой показаны IntersectionDetail, используемые при проверке попадания.](./media/how-to-hit-test-using-geometry-as-a-parameter/intersectiondetail-hit-test.png)  
  
 <span data-ttu-id="26651-110">В следующем примере показано, как реализовать обратный вызов проверки попадания при <xref:System.Windows.Media.Geometry> использовании в качестве параметра проверки нажатия.</span><span class="sxs-lookup"><span data-stu-id="26651-110">The following example shows how to implement a hit test callback when a <xref:System.Windows.Media.Geometry> is used as a hit test parameter.</span></span> <span data-ttu-id="26651-111">Параметр приводится к типу, <xref:System.Windows.Media.GeometryHitTestResult> чтобы <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> получить значение свойства. `result`</span><span class="sxs-lookup"><span data-stu-id="26651-111">The `result` parameter is cast to a <xref:System.Windows.Media.GeometryHitTestResult> in order to retrieve the value of the <xref:System.Windows.Media.GeometryHitTestResult.IntersectionDetail%2A> property.</span></span> <span data-ttu-id="26651-112">Значение свойства позволяет определить, является ли <xref:System.Windows.Media.Geometry> параметр проверки нажатия полностью или частично включен в отображаемое содержимое целевого объекта проверки попадания.</span><span class="sxs-lookup"><span data-stu-id="26651-112">The property value allows you to determine if the <xref:System.Windows.Media.Geometry> hit test parameter is fully or partially contained within the rendered content of the hit test target.</span></span> <span data-ttu-id="26651-113">В этом случае пример кода только добавляет результаты проверки попадания в список визуальных объектов, которые полностью содержатся в пределах границ целевого объекта.</span><span class="sxs-lookup"><span data-stu-id="26651-113">In this case, the sample code is only adding hit test results to the list for visuals that are fully contained within the target boundary.</span></span>  
  
 [!code-csharp[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTestingOverview/CSharp/GeometryHitTest.cs#hittestingoverviewsnippet11)]
 [!code-vb[HitTestingOverview#HitTestingOverviewSnippet11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTestingOverview/visualbasic/geometryhittest.vb#hittestingoverviewsnippet11)]  
  
> [!NOTE]
> <span data-ttu-id="26651-114">Обратный вызов не должен вызываться, если сведения о пересечении имеют <xref:System.Windows.Media.IntersectionDetail.Empty>значение. <xref:System.Windows.Media.HitTestResult></span><span class="sxs-lookup"><span data-stu-id="26651-114">The <xref:System.Windows.Media.HitTestResult> callback should not be called when the intersection detail is <xref:System.Windows.Media.IntersectionDetail.Empty>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26651-115">См. также</span><span class="sxs-lookup"><span data-stu-id="26651-115">See also</span></span>

- [<span data-ttu-id="26651-116">Проверка нажатия на визуальном уровне</span><span class="sxs-lookup"><span data-stu-id="26651-116">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="26651-117">Проверка попадания геометрического объекта в визуальный объект</span><span class="sxs-lookup"><span data-stu-id="26651-117">Hit Test Geometry in a Visual</span></span>](how-to-hit-test-geometry-in-a-visual.md)
