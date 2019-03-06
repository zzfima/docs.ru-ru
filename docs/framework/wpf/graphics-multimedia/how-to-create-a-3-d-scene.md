---
title: Практическое руководство. Создание трехмерной сцены
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3-D
- 3-D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 8c9aec78bdda4f9f122b6dbefe0956ba649adf22
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370752"
---
# <a name="how-to-create-a-3-d-scene"></a><span data-ttu-id="e0513-102">Практическое руководство. Создание трехмерной сцены</span><span class="sxs-lookup"><span data-stu-id="e0513-102">How to: Create a 3-D Scene</span></span>
<span data-ttu-id="e0513-103">В этом примере демонстрируется создание трехмерного объекта, который выглядит как плоский листа бумаги, вращающийся.</span><span class="sxs-lookup"><span data-stu-id="e0513-103">This example shows how to create a 3-D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="e0513-104">Объект <xref:System.Windows.Controls.Viewport3D> вместе с следующие компоненты, используются для создания этой простой трехмерной сцены:</span><span class="sxs-lookup"><span data-stu-id="e0513-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3-D scene:</span></span>  
  
-   <span data-ttu-id="e0513-105">Камера создается с помощью <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span><span class="sxs-lookup"><span data-stu-id="e0513-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="e0513-106">Камеры указывает, какая часть трехмерной сцены можно просматривать.</span><span class="sxs-lookup"><span data-stu-id="e0513-106">The camera specifies what part of the 3-D scene is viewable.</span></span>  
  
-   <span data-ttu-id="e0513-107">Сетка создается для задания формы трехмерного объекта (лист бумаги) с помощью <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> свойство <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="e0513-107">A mesh is created to specify the shape of 3-D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="e0513-108">Материал указывается отображаемый на поверхности объекта (линейного градиента в этом образце) с помощью <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> свойство <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="e0513-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
-   <span data-ttu-id="e0513-109">Источник света создается для освещения объекта с помощью <xref:System.Windows.Media.Media3D.DirectionalLight>.</span><span class="sxs-lookup"><span data-stu-id="e0513-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0513-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e0513-110">Example</span></span>  
 <span data-ttu-id="e0513-111">В приведенном ниже коде показано, как создание трехмерной сцены в XAML.</span><span class="sxs-lookup"><span data-stu-id="e0513-111">The code below shows how to create a 3-D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="e0513-112">Пример</span><span class="sxs-lookup"><span data-stu-id="e0513-112">Example</span></span>  
 <span data-ttu-id="e0513-113">В приведенном ниже коде показано создание одной и той же трехмерной сцены в процедурном коде.</span><span class="sxs-lookup"><span data-stu-id="e0513-113">The code below shows how to create the same 3-D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e0513-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e0513-114">See also</span></span>
- [<span data-ttu-id="e0513-115">Обзор трехмерной графики</span><span class="sxs-lookup"><span data-stu-id="e0513-115">3-D Graphics Overview</span></span>](3-d-graphics-overview.md)
