---
title: 'Как: Применить рисунок к 3D-модели'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3D models
- 3D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 5b10630ab674fa9489cdf7ad53516a680f19da08
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112184"
---
# <a name="how-to-apply-a-drawing-to-a-3d-model"></a><span data-ttu-id="303a8-102">Как: Применить рисунок к 3D-модели</span><span class="sxs-lookup"><span data-stu-id="303a8-102">How to: Apply a Drawing to a 3D Model</span></span>

<span data-ttu-id="303a8-103">В этом примере <xref:System.Windows.Media.DrawingBrush> показано, <xref:System.Windows.Media.Media3D.Material> как использовать применяемый к 3D-модели.</span><span class="sxs-lookup"><span data-stu-id="303a8-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3D model.</span></span>

<span data-ttu-id="303a8-104">Следующий код определяет <xref:System.Windows.Media.DrawingGroup> как содержимое <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="303a8-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="303a8-105">Устанавливается <xref:System.Windows.Media.DrawingBrush> как <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> свойство <xref:System.Windows.Media.Media3D.DiffuseMaterial> прикладного к 3D плоскости.</span><span class="sxs-lookup"><span data-stu-id="303a8-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3D plane.</span></span>

> [!NOTE]
> <span data-ttu-id="303a8-106">Часто желательно определить сложные объекты и значения, такие как приведенный ниже рисунок, как ресурсы, которые могут быть повторно использованы и упростить код.</span><span class="sxs-lookup"><span data-stu-id="303a8-106">It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="303a8-107">Дополнительную информацию можно узнать на [примере XAML Resources.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)</span><span class="sxs-lookup"><span data-stu-id="303a8-107">See [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md) for more information.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]

## <a name="example"></a><span data-ttu-id="303a8-108">Пример</span><span class="sxs-lookup"><span data-stu-id="303a8-108">Example</span></span>

<span data-ttu-id="303a8-109">Следующий код показывает весь образец.</span><span class="sxs-lookup"><span data-stu-id="303a8-109">The following code shows the entire sample.</span></span>

[!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]

## <a name="see-also"></a><span data-ttu-id="303a8-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="303a8-110">See also</span></span>

- [<span data-ttu-id="303a8-111">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="303a8-111">XAML Resources</span></span>](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="303a8-112">Создание 3D-сцены</span><span class="sxs-lookup"><span data-stu-id="303a8-112">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="303a8-113">Общие сведения об объектах Drawing</span><span class="sxs-lookup"><span data-stu-id="303a8-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="303a8-114">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="303a8-114">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
