---
title: Практическое руководство. Применение рисования к трехмерной модели
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 26a84d963cac3b5c23617bfaa23279021e29c07a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="bdf10-102">Практическое руководство. Применение рисования к трехмерной модели</span><span class="sxs-lookup"><span data-stu-id="bdf10-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="bdf10-103">В этом примере показано, как использовать <xref:System.Windows.Media.DrawingBrush> как <xref:System.Windows.Media.Media3D.Material> применены к [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] модели.</span><span class="sxs-lookup"><span data-stu-id="bdf10-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="bdf10-104">В следующем коде определяется <xref:System.Windows.Media.DrawingGroup> как содержимое <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="bdf10-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="bdf10-105"><xref:System.Windows.Media.DrawingBrush> Задается как <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> свойство <xref:System.Windows.Media.Media3D.DiffuseMaterial> применены к [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] плоскость.</span><span class="sxs-lookup"><span data-stu-id="bdf10-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] plane.</span></span>  
  
 <span data-ttu-id="bdf10-106">**Примечание:** часто желательно определить сложные объекты и значения, как на рисунке ниже как ресурсы, которые можно использовать повторно и упростить код.</span><span class="sxs-lookup"><span data-stu-id="bdf10-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="bdf10-107">В разделе [ресурсов XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md) для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="bdf10-107">See [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="bdf10-108">Пример</span><span class="sxs-lookup"><span data-stu-id="bdf10-108">Example</span></span>  
 <span data-ttu-id="bdf10-109">Ниже приведен пример целиком.</span><span class="sxs-lookup"><span data-stu-id="bdf10-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="bdf10-110">См. также</span><span class="sxs-lookup"><span data-stu-id="bdf10-110">See Also</span></span>  
 [<span data-ttu-id="bdf10-111">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="bdf10-111">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="bdf10-112">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="bdf10-112">Create a 3-D Scene</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-3-d-scene.md)  
 [<span data-ttu-id="bdf10-113">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="bdf10-113">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="bdf10-114">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="bdf10-114">3-D Graphics Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/3-d-graphics-overview.md)
