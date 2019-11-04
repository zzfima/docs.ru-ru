---
title: Практическое руководство. Применение рисования к трехмерной модели
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 311a3ac1d9fa219a3a365d506d9d0c3e8b6bc229
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459364"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="d1712-102">Практическое руководство. Применение рисования к трехмерной модели</span><span class="sxs-lookup"><span data-stu-id="d1712-102">How to: Apply a Drawing to a 3-D Model</span></span>

<span data-ttu-id="d1712-103">В этом примере показано, как использовать <xref:System.Windows.Media.DrawingBrush> в качестве <xref:System.Windows.Media.Media3D.Material>, применяемого к трехмерной модели.</span><span class="sxs-lookup"><span data-stu-id="d1712-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>

<span data-ttu-id="d1712-104">Следующий код определяет <xref:System.Windows.Media.DrawingGroup> как содержимое <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="d1712-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="d1712-105"><xref:System.Windows.Media.DrawingBrush> задается как свойство <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> <xref:System.Windows.Media.Media3D.DiffuseMaterial>, применяемое к трехмерной плоскости.</span><span class="sxs-lookup"><span data-stu-id="d1712-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="d1712-106">Часто желательно определить сложные объекты и значения, такие как рисунок ниже, как ресурсы, которые можно использовать повторно и упростить код.</span><span class="sxs-lookup"><span data-stu-id="d1712-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="d1712-107">Дополнительные сведения см. в разделе [ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md) .</span><span class="sxs-lookup"><span data-stu-id="d1712-107">See [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="d1712-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d1712-108">Example</span></span>

<span data-ttu-id="d1712-109">В следующем коде показан весь пример.</span><span class="sxs-lookup"><span data-stu-id="d1712-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="d1712-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d1712-110">See also</span></span>

- [<span data-ttu-id="d1712-111">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="d1712-111">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="d1712-112">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="d1712-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="d1712-113">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="d1712-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="d1712-114">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="d1712-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
