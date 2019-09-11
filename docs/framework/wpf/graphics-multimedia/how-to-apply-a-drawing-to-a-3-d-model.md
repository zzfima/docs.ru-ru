---
title: Практическое руководство. Применение рисования к трехмерной модели
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 14470d0adeb948ea46a0720b5713c20fb7d8e6d8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855883"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="64fa5-102">Практическое руководство. Применение рисования к трехмерной модели</span><span class="sxs-lookup"><span data-stu-id="64fa5-102">How to: Apply a Drawing to a 3-D Model</span></span>

<span data-ttu-id="64fa5-103">В этом примере показано, как использовать <xref:System.Windows.Media.DrawingBrush> объект в <xref:System.Windows.Media.Media3D.Material> качестве примененного к трехмерной модели.</span><span class="sxs-lookup"><span data-stu-id="64fa5-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>

<span data-ttu-id="64fa5-104">Следующий код определяет в <xref:System.Windows.Media.DrawingGroup> качестве содержимого. <xref:System.Windows.Media.DrawingBrush></span><span class="sxs-lookup"><span data-stu-id="64fa5-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="64fa5-105">Задается <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> как свойство объекта, <xref:System.Windows.Media.Media3D.DiffuseMaterial> применяемого к трехмерной плоскости. <xref:System.Windows.Media.DrawingBrush></span><span class="sxs-lookup"><span data-stu-id="64fa5-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="64fa5-106">Часто желательно определить сложные объекты и значения, такие как рисунок ниже, как ресурсы, которые можно использовать повторно и упростить код.</span><span class="sxs-lookup"><span data-stu-id="64fa5-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="64fa5-107">Дополнительные сведения см. в разделе [ресурсы XAML](../advanced/xaml-resources.md) .</span><span class="sxs-lookup"><span data-stu-id="64fa5-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="64fa5-108">Пример</span><span class="sxs-lookup"><span data-stu-id="64fa5-108">Example</span></span>

<span data-ttu-id="64fa5-109">В следующем коде показан весь пример.</span><span class="sxs-lookup"><span data-stu-id="64fa5-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="64fa5-110">См. также</span><span class="sxs-lookup"><span data-stu-id="64fa5-110">See also</span></span>

- [<span data-ttu-id="64fa5-111">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="64fa5-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="64fa5-112">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="64fa5-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="64fa5-113">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="64fa5-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="64fa5-114">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="64fa5-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
