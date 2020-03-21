---
title: Как применить эмиссионный материал к 3D-объекту
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112158"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a><span data-ttu-id="d930d-102">Как применить эмиссионный материал к 3D-объекту</span><span class="sxs-lookup"><span data-stu-id="d930d-102">How to: Apply Emissive Material to a 3D Object</span></span>
<span data-ttu-id="d930d-103">Ниже приводится пример, <xref:System.Windows.Media.Media3D.EmissiveMaterial> как использовать для добавления цвета к существующему материалу, равному цвету кисти EmissiveMaterial.</span><span class="sxs-lookup"><span data-stu-id="d930d-103">The following example shows how to use <xref:System.Windows.Media.Media3D.EmissiveMaterial> to add color to an existing Material equal to the color of the EmissiveMaterial's brush.</span></span> <span data-ttu-id="d930d-104">Приведенный ниже <xref:System.Windows.Media.Media3D.DiffuseMaterial> <xref:System.Windows.Media.Media3D.EmissiveMaterial> код показывает и применяется в комбинации, чтобы добавить синий цвет к внешнему виду DiffuseMaterial.</span><span class="sxs-lookup"><span data-stu-id="d930d-104">The code below shows <xref:System.Windows.Media.Media3D.DiffuseMaterial> and <xref:System.Windows.Media.Media3D.EmissiveMaterial> applied in combination to add blue to the DiffuseMaterial's appearance.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 <span data-ttu-id="d930d-105">В процедурном кодексе:</span><span class="sxs-lookup"><span data-stu-id="d930d-105">In procedural code:</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="d930d-106">Пример</span><span class="sxs-lookup"><span data-stu-id="d930d-106">Example</span></span>  
 <span data-ttu-id="d930d-107">Следующий код показывает весь образец в XAML.</span><span class="sxs-lookup"><span data-stu-id="d930d-107">The following code shows the entire sample in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="d930d-108">Пример</span><span class="sxs-lookup"><span data-stu-id="d930d-108">Example</span></span>  
 <span data-ttu-id="d930d-109">Ниже приведен авоту всего образца в процедурном кодексе.</span><span class="sxs-lookup"><span data-stu-id="d930d-109">Below is the entire sample in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="d930d-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d930d-110">See also</span></span>

- [<span data-ttu-id="d930d-111">Создание 3D-сцены</span><span class="sxs-lookup"><span data-stu-id="d930d-111">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="d930d-112">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="d930d-112">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="d930d-113">Оживите свойства материала в 3D-сцене</span><span class="sxs-lookup"><span data-stu-id="d930d-113">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="d930d-114">Применить материал к передней и задней части 3D-объекта</span><span class="sxs-lookup"><span data-stu-id="d930d-114">Apply Material to the Front and Back of a 3D Object</span></span>](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
