---
title: Практическое руководство. Применение рисования к трехмерной модели
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], applying to 3-D models
- 3-D models [WPF], applying drawings to
ms.assetid: 68357577-b7fc-446e-8be9-a8cc7df3a350
ms.openlocfilehash: 8ac24fdf8d7e407e10764c17fcc12121aa5f51d7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662816"
---
# <a name="how-to-apply-a-drawing-to-a-3-d-model"></a><span data-ttu-id="0082d-102">Практическое руководство. Применение рисования к трехмерной модели</span><span class="sxs-lookup"><span data-stu-id="0082d-102">How to: Apply a Drawing to a 3-D Model</span></span>
<span data-ttu-id="0082d-103">В этом примере показано, как использовать <xref:System.Windows.Media.DrawingBrush> как <xref:System.Windows.Media.Media3D.Material> применяется к трехмерной модели.</span><span class="sxs-lookup"><span data-stu-id="0082d-103">This example shows how to use a <xref:System.Windows.Media.DrawingBrush> as the <xref:System.Windows.Media.Media3D.Material> applied to a 3-D model.</span></span>  
  
 <span data-ttu-id="0082d-104">В следующем коде определяется <xref:System.Windows.Media.DrawingGroup> как содержимое <xref:System.Windows.Media.DrawingBrush>.</span><span class="sxs-lookup"><span data-stu-id="0082d-104">The following code defines a <xref:System.Windows.Media.DrawingGroup> as the content of a <xref:System.Windows.Media.DrawingBrush>.</span></span>  <span data-ttu-id="0082d-105"><xref:System.Windows.Media.DrawingBrush> Задается как <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> свойство <xref:System.Windows.Media.Media3D.DiffuseMaterial> применяется к трехмерной плоскости.</span><span class="sxs-lookup"><span data-stu-id="0082d-105">The <xref:System.Windows.Media.DrawingBrush> is set as the <xref:System.Windows.Media.Media3D.DiffuseMaterial.Brush%2A> property of the <xref:System.Windows.Media.Media3D.DiffuseMaterial> applied to a 3-D plane.</span></span>  
  
 <span data-ttu-id="0082d-106">**Примечание.** Часто желательно, чтобы определить сложные объекты и значения, как на рисунке ниже как ресурсы, которые можно использовать повторно и упростить код.</span><span class="sxs-lookup"><span data-stu-id="0082d-106">**Note:** It is often desirable to define complex objects and values like the drawing below as resources which can be reused and simplify your code.</span></span> <span data-ttu-id="0082d-107">См. в разделе [ресурсы XAML](../advanced/xaml-resources.md) Дополнительные сведения.</span><span class="sxs-lookup"><span data-stu-id="0082d-107">See [XAML Resources](../advanced/xaml-resources.md) for more information.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialinline1)]  
  
## <a name="example"></a><span data-ttu-id="0082d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="0082d-108">Example</span></span>  
 <span data-ttu-id="0082d-109">В следующем коде показано весь пример.</span><span class="sxs-lookup"><span data-stu-id="0082d-109">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[3DGallery_snip#ApplyDrawingToMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/ApplyDrawingToMaterialExample.xaml#applydrawingtomaterialexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0082d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="0082d-110">See also</span></span>

- [<span data-ttu-id="0082d-111">Ресурсы XAML</span><span class="sxs-lookup"><span data-stu-id="0082d-111">XAML Resources</span></span>](../advanced/xaml-resources.md)
- [<span data-ttu-id="0082d-112">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="0082d-112">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="0082d-113">Обзор объектов Drawing</span><span class="sxs-lookup"><span data-stu-id="0082d-113">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="0082d-114">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="0082d-114">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
