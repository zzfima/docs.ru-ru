---
title: Практическое руководство. Применение эмиссионного материала к трехмерному объекту
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3-D objects
- 3-D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: b898148fa07950e3ad1eddcaf9206f7d6a837241
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163128"
---
# <a name="how-to-apply-emissive-material-to-a-3-d-object"></a><span data-ttu-id="7ed34-102">Практическое руководство. Применение эмиссионного материала к трехмерному объекту</span><span class="sxs-lookup"><span data-stu-id="7ed34-102">How to: Apply Emissive Material to a 3-D Object</span></span>
<span data-ttu-id="7ed34-103">В следующем примере показано, как использовать <xref:System.Windows.Media.Media3D.EmissiveMaterial> добавить цвет в существующий материал, равный цвету кисти EmissiveMaterial.</span><span class="sxs-lookup"><span data-stu-id="7ed34-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="7ed34-104">В коде ниже показан <xref:System.Windows.Media.Media3D.DiffuseMaterial> и <xref:System.Windows.Media.Media3D.EmissiveMaterial> примененные вместе для добавления синего цвета во внешний вид DiffuseMaterial.</span><span class="sxs-lookup"><span data-stu-id="7ed34-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="7ed34-105">В процедурном коде:</span><span class="sxs-lookup"><span data-stu-id="7ed34-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="7ed34-106">Пример</span><span class="sxs-lookup"><span data-stu-id="7ed34-106">Example</span></span>  
 <span data-ttu-id="7ed34-107">В следующем коде показано весь пример в XAML.</span><span class="sxs-lookup"><span data-stu-id="7ed34-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="7ed34-108">Пример</span><span class="sxs-lookup"><span data-stu-id="7ed34-108">Example</span></span>  
 <span data-ttu-id="7ed34-109">Ниже приведен пример целиком в процедурном коде.</span><span class="sxs-lookup"><span data-stu-id="7ed34-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="7ed34-110">См. также</span><span class="sxs-lookup"><span data-stu-id="7ed34-110">See also</span></span>

- [<span data-ttu-id="7ed34-111">Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="7ed34-111">Create a 3-D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="7ed34-112">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="7ed34-112">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="7ed34-113">Анимация свойств материалов в трехмерной сцене</span><span class="sxs-lookup"><span data-stu-id="7ed34-113">Animate Material Properties in a 3-D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="7ed34-114">Применение материала к лицевой и обратной стороне трехмерного объекта</span><span class="sxs-lookup"><span data-stu-id="7ed34-114">Apply Material to the Front and Back of a 3-D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
