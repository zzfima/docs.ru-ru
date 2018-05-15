---
title: Практическое руководство. Создание объединенных геометрических объектов
ms.date: 03/30/2017
helpviewer_keywords:
- combining geometries [WPF]
- graphics [WPF], combining geometries
- geometries [WPF], combining
ms.assetid: 54c3277c-6b6e-4b25-91be-fda0bbc706b4
ms.openlocfilehash: 107e0342b822633ccb4f51f256c121cc80c297f4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-combined-geometry"></a><span data-ttu-id="fafd4-102">Практическое руководство. Создание объединенных геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="fafd4-102">How to: Create a Combined Geometry</span></span>
<span data-ttu-id="fafd4-103">В этом примере показано, как объединить геометрических объектов.</span><span class="sxs-lookup"><span data-stu-id="fafd4-103">This example shows how to combine geometries.</span></span> <span data-ttu-id="fafd4-104">Чтобы объединить два геометрических объекта, используйте <xref:System.Windows.Media.CombinedGeometry> объекта.</span><span class="sxs-lookup"><span data-stu-id="fafd4-104">To combine two geometries, use a <xref:System.Windows.Media.CombinedGeometry> object.</span></span> <span data-ttu-id="fafd4-105">Задать его <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> свойства два геометрических объекта для объединения и установить <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> свойство, которое определяет, как геометрические объекты будут объединены вместе, чтобы `Union`, `Intersect`, `Exclude`, или `Xor`.</span><span class="sxs-lookup"><span data-stu-id="fafd4-105">Set its <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> properties  with the two geometries to combine, and set the <xref:System.Windows.Media.CombinedGeometry.GeometryCombineMode%2A> property, which determines how the geometries will be combined together, to `Union`, `Intersect`, `Exclude`, or `Xor`.</span></span>  
  
 <span data-ttu-id="fafd4-106">Чтобы создать составной геометрический объект из двух или более геометрических объектов, используйте <xref:System.Windows.Media.GeometryGroup>.</span><span class="sxs-lookup"><span data-stu-id="fafd4-106">To create a composite geometry from two or more geometries, use a <xref:System.Windows.Media.GeometryGroup>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fafd4-107">Пример</span><span class="sxs-lookup"><span data-stu-id="fafd4-107">Example</span></span>  
 <span data-ttu-id="fafd4-108">В следующем примере <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения geometry из `Exclude`.</span><span class="sxs-lookup"><span data-stu-id="fafd4-108">In the following example, a <xref:System.Windows.Media.CombinedGeometry> is defined with a geometry combine mode of `Exclude`.</span></span>  <span data-ttu-id="fafd4-109">Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги же radius, но со смещением центры 50.</span><span class="sxs-lookup"><span data-stu-id="fafd4-109">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#21)]  
  
 <span data-ttu-id="fafd4-110">![Исключить результаты объединенного режима](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span><span class="sxs-lookup"><span data-stu-id="fafd4-110">![Results of the Exclude combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-exclude.PNG "mil_task_combined_geometry_exclude")</span></span>  
<span data-ttu-id="fafd4-111">Исключить объединенных геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="fafd4-111">Combined Geometry Exclude</span></span>  
  
 <span data-ttu-id="fafd4-112">В следующую разметку <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения из `Intersect`.</span><span class="sxs-lookup"><span data-stu-id="fafd4-112">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Intersect`.</span></span>  <span data-ttu-id="fafd4-113">Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги же radius, но со смещением центры 50.</span><span class="sxs-lookup"><span data-stu-id="fafd4-113">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#22)]  
  
 <span data-ttu-id="fafd4-114">![Функция Intersect результаты объединенного режима](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span><span class="sxs-lookup"><span data-stu-id="fafd4-114">![Results of the Intersect combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-intersect.PNG "mil_task_combined_geometry_intersect")</span></span>  
<span data-ttu-id="fafd4-115">Intersect объединенных геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="fafd4-115">Combined Geometry Intersect</span></span>  
  
 <span data-ttu-id="fafd4-116">В следующую разметку <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения из `Union`.</span><span class="sxs-lookup"><span data-stu-id="fafd4-116">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Union`.</span></span>  <span data-ttu-id="fafd4-117">Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги же radius, но со смещением центры 50.</span><span class="sxs-lookup"><span data-stu-id="fafd4-117">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#23)]  
  
 <span data-ttu-id="fafd4-118">![Результаты объединения в режиме Union ](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span><span class="sxs-lookup"><span data-stu-id="fafd4-118">![Results of the Union combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-union.PNG "mil_task_combined_geometry_union")</span></span>  
<span data-ttu-id="fafd4-119">Объединение комбинированной геометрии</span><span class="sxs-lookup"><span data-stu-id="fafd4-119">Combined Geometry Union</span></span>  
  
 <span data-ttu-id="fafd4-120">В следующую разметку <xref:System.Windows.Media.CombinedGeometry> определяется режимом объединения из `Xor`.</span><span class="sxs-lookup"><span data-stu-id="fafd4-120">In the following markup, a <xref:System.Windows.Media.CombinedGeometry> is defined with a combine mode of `Xor`.</span></span>  <span data-ttu-id="fafd4-121">Оба <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> и <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> определяются как круги же radius, но со смещением центры 50.</span><span class="sxs-lookup"><span data-stu-id="fafd4-121">Both <xref:System.Windows.Media.CombinedGeometry.Geometry1%2A> and the <xref:System.Windows.Media.CombinedGeometry.Geometry2%2A> are defined as circles of the same radius, but with centers offset by 50.</span></span>  
  
 [!code-xaml[GeometrySample#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#24)]  
  
 <span data-ttu-id="fafd4-122">![Результаты объединения в режиме Xor ](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span><span class="sxs-lookup"><span data-stu-id="fafd4-122">![Results of the Xor combine mode](../../../../docs/framework/wpf/graphics-multimedia/media/mil-task-combined-geometry-xor.PNG "mil_task_combined_geometry_xor")</span></span>  
<span data-ttu-id="fafd4-123">Xor объединенных геометрических объектов</span><span class="sxs-lookup"><span data-stu-id="fafd4-123">Combined Geometry Xor</span></span>
