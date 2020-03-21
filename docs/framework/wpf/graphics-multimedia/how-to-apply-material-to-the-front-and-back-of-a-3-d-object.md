---
title: Как применить материал к передней и задней части 3D-объекта
ms.date: 03/30/2017
helpviewer_keywords:
- 3D objects [WPF], applying Material class
- Material class [WPF], applying to both sides of 3D object
- classes [WPF], Material
ms.assetid: d93c8ad6-4939-4d29-9544-4d16d98093c1
ms.openlocfilehash: 5c24879d97e7857fb07fcef4a9ba8efa901e4a39
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112145"
---
# <a name="how-to-apply-material-to-the-front-and-back-of-a-3d-object"></a><span data-ttu-id="0bcb2-102">Как применить материал к передней и задней части 3D-объекта</span><span class="sxs-lookup"><span data-stu-id="0bcb2-102">How to: Apply Material to the Front and Back of a 3D Object</span></span>
<span data-ttu-id="0bcb2-103">В следующем примере показано, как применить <xref:System.Windows.Media.Media3D.Material> к передней и задней части 3D-объекта и оживить объект, чтобы показать обе стороны объекта.</span><span class="sxs-lookup"><span data-stu-id="0bcb2-103">The following example shows how to apply a <xref:System.Windows.Media.Media3D.Material> to the front and back of a 3D object and animate the object to show both sides of the object.</span></span> <span data-ttu-id="0bcb2-104">Свойство <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> <xref:System.Windows.Media.Media3D.GeometryModel3D> используется для нанесения <xref:System.Windows.Media.Brush> красного цвета на переднюю <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> сторону <xref:System.Windows.Media.Media3D.GeometryModel3D> объекта, а свойство используемого для нанесения синего <xref:System.Windows.Media.Brush> цвета на заднюю сторону объекта.</span><span class="sxs-lookup"><span data-stu-id="0bcb2-104">The <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of a <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a red <xref:System.Windows.Media.Brush> to the front side of the object and the <xref:System.Windows.Media.Media3D.GeometryModel3D.BackMaterial%2A> property of the <xref:System.Windows.Media.Media3D.GeometryModel3D> is used to apply a blue <xref:System.Windows.Media.Brush> to the back side of the object.</span></span> <span data-ttu-id="0bcb2-105">Приведенный ниже код показывает применение материалов к объекту:</span><span class="sxs-lookup"><span data-stu-id="0bcb2-105">The code below shows the application of the materials to the object:</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexampleinline1)]  
  
## <a name="example"></a><span data-ttu-id="0bcb2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0bcb2-106">Example</span></span>  
 <span data-ttu-id="0bcb2-107">Следующий код показывает весь образец.</span><span class="sxs-lookup"><span data-stu-id="0bcb2-107">The following code shows the entire sample.</span></span>  
  
 [!code-xaml[Animation3DGallery_snip#BackMaterialAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/BackMaterialAnimationExample.xaml#backmaterialanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="0bcb2-108">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0bcb2-108">See also</span></span>

- [<span data-ttu-id="0bcb2-109">Создание 3D-сцены</span><span class="sxs-lookup"><span data-stu-id="0bcb2-109">Create a 3D Scene</span></span>](how-to-create-a-3-d-scene.md)
- [<span data-ttu-id="0bcb2-110">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="0bcb2-110">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
- [<span data-ttu-id="0bcb2-111">Оживите свойства материала в 3D-сцене</span><span class="sxs-lookup"><span data-stu-id="0bcb2-111">Animate Material Properties in a 3D Scene</span></span>](how-to-animate-material-properties-in-a-3-d-scene.md)
- [<span data-ttu-id="0bcb2-112">Применить эмиссионный материал к 3D-объекту</span><span class="sxs-lookup"><span data-stu-id="0bcb2-112">Apply Emissive Material to a 3D Object</span></span>](how-to-apply-emissive-material-to-a-3-d-object.md)
