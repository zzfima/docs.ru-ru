---
title: Практическое руководство. Применение рисования к трехмерной модели
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: a20b89a7359fc85d9790ac02dd2b173452df8c22
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699114"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="a64b9-102">Практическое руководство. Применение рисования к трехмерной модели</span><span class="sxs-lookup"><span data-stu-id="a64b9-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="a64b9-103">В этом примере показано, как использовать <xref:System.Windows.Media.DrawingBrush> как <xref:System.Windows.Media.Media3D.Material> применяется к [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] модели.</span><span class="sxs-lookup"><span data-stu-id="a64b9-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] model.</span></span>  
  
 <span data-ttu-id="a64b9-104">В следующем коде определяется <xref:System.Windows.Media.DrawingGroup> как содержимое <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="a64b9-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="a64b9-105"><xref:System.Windows.Media.DrawingBrush> Задается как <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> свойство <xref:System.Windows.Media.Media3D.DiffuseMaterial> применяется к [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] плоскости.</span><span class="sxs-lookup"><span data-stu-id="a64b9-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a [!INCLUDE[TLA2#tla_3d](../../../../includes/tla2sharptla-3d-md.md)] plane.</span></span>  
  
 <span data-ttu-id="a64b9-106">**Примечание.** Часто желательно, чтобы определить сложные объекты и значения, как на рисунке ниже как ресурсы, которые можно использовать повторно и упростить код.</span><span class="sxs-lookup"><span data-stu-id="a64b9-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="a64b9-107">См. в разделе [ресурсы XAML](../advanced/xaml-resources.md) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="a64b9-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="a64b9-108">Пример</span><span class="sxs-lookup"><span data-stu-id="a64b9-108">Example</span></span>  
 <span data-ttu-id="a64b9-109">В следующем коде показано весь пример.</span><span class="sxs-lookup"><span data-stu-id="a64b9-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a64b9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a64b9-110">See also</span></span>

- [<span data-ttu-id="a64b9-111">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="a64b9-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="a64b9-112">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="a64b9-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="a64b9-113">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="a64b9-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="a64b9-114">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="a64b9-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
