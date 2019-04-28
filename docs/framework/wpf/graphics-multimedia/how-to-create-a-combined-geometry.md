---
title: Практическое руководство. Создание объединенных геометрических объектов
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: c5ebe87abd4c2cf70f8fa17f1fcc773293f3ad27
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910109"
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="f9a83-102">Практическое руководство. Создание объединенных геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="f9a83-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="f9a83-103">В этом примере показано, как для объединения геометрических объектов.</span><span class="sxs-lookup"><span data-stu-id="f9a83-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="f9a83-104">Чтобы объединить два геометрических объекта, используйте <xref:System.Windows.Media.CombinedGeometry> объекта.</span><span class="sxs-lookup"><span data-stu-id="f9a83-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="f9a83-105">Задать его <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> свойства два геометрических объекта для объединения и установить <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> свойство, которое определяет, каким образом геометрические объекты будут объединяться, чтобы `Union`, `Intersect`, `Exclude`, или `Xor`.</span><span class="sxs-lookup"><span data-stu-id="f9a83-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="f9a83-106">Чтобы создать составной геометрический объект из двух или более геометрических объектов, используйте <xref:System.Windows.Media.GeometryGroup>.</span><span class="sxs-lookup"><span data-stu-id="f9a83-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9a83-107">Пример</span><span class="sxs-lookup"><span data-stu-id="f9a83-107">Example</span></span>  
 <span data-ttu-id="f9a83-108">В следующем примере <xref:System.Windows.Media.CombinedGeometry> определяется с режимом объединения геометрических `Exclude`.</span><span class="sxs-lookup"><span data-stu-id="f9a83-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="f9a83-109">Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги одного радиуса, но со смещением центров на 50.</span><span class="sxs-lookup"><span data-stu-id="f9a83-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="f9a83-110">![Исключить результаты объединенного режима](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="f9a83-110">![Results of the Exclude combine mode](./media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="f9a83-111">Исключить объединенных геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="f9a83-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="f9a83-112">В следующей разметке <xref:System.Windows.Media.CombinedGeometry> определяется с режимом объединения `Intersect`.</span><span class="sxs-lookup"><span data-stu-id="f9a83-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="f9a83-113">Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги одного радиуса, но со смещением центров на 50.</span><span class="sxs-lookup"><span data-stu-id="f9a83-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="f9a83-114">![Intersect результаты объединенного режима](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="f9a83-114">![Results of the Intersect combine mode](./media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="f9a83-115">Intersect объединенных геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="f9a83-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="f9a83-116">В следующей разметке <xref:System.Windows.Media.CombinedGeometry> определяется с режимом объединения `Union`.</span><span class="sxs-lookup"><span data-stu-id="f9a83-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="f9a83-117">Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги одного радиуса, но со смещением центров на 50.</span><span class="sxs-lookup"><span data-stu-id="f9a83-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="f9a83-118">![Результаты объединения в режиме Union ](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="f9a83-118">![Results of the Union combine mode](./media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="f9a83-119">Объединение объединенных геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="f9a83-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="f9a83-120">В следующей разметке <xref:System.Windows.Media.CombinedGeometry> определяется с режимом объединения `Xor`.</span><span class="sxs-lookup"><span data-stu-id="f9a83-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="f9a83-121">Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги одного радиуса, но со смещением центров на 50.</span><span class="sxs-lookup"><span data-stu-id="f9a83-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="f9a83-122">![Результаты объединения в режиме Xor ](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="f9a83-122">![Results of the Xor combine mode](./media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="f9a83-123">Xor объединенных геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="f9a83-123">Combined Geometry Xor</span></span>
