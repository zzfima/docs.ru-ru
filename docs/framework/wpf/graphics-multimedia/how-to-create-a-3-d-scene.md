---
title: 'Как: Создать 3D-сцену'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scenes [WPF], 3D
- 3D scenes
ms.assetid: adb4a598-71a2-4dd5-b677-ea3fc11b78b2
ms.openlocfilehash: 36453894e06e7b59f339c21713449140c17f6851
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112106"
---
# <a name="how-to-create-a-3d-scene"></a><span data-ttu-id="f2478-102">Как: Создать 3D-сцену</span><span class="sxs-lookup"><span data-stu-id="f2478-102">How to: Create a 3D Scene</span></span>
<span data-ttu-id="f2478-103">В этом примере показано, как создать 3D-объект, похожий на плоский лист бумаги, который был повернут.</span><span class="sxs-lookup"><span data-stu-id="f2478-103">This example shows how to create a 3D object that looks like a flat sheet of paper which has been rotated.</span></span> <span data-ttu-id="f2478-104">А <xref:System.Windows.Controls.Viewport3D> вместе со следующими компонентами используются для создания этой простой 3D сцены:</span><span class="sxs-lookup"><span data-stu-id="f2478-104">A <xref:System.Windows.Controls.Viewport3D> along with the following components are used to create this simple 3D scene:</span></span>  
  
- <span data-ttu-id="f2478-105">Камера создается с <xref:System.Windows.Media.Media3D.PerspectiveCamera>помощью .</span><span class="sxs-lookup"><span data-stu-id="f2478-105">A camera is created using a <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="f2478-106">Камера определяет, какая часть 3D-сцены видна для просмотра.</span><span class="sxs-lookup"><span data-stu-id="f2478-106">The camera specifies what part of the 3D scene is viewable.</span></span>  
  
- <span data-ttu-id="f2478-107">Создается сетка для определения формы 3D-объекта (листа <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> бумаги) с использованием свойства <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="f2478-107">A mesh is created to specify the shape of 3D object (sheet of paper) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Geometry%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="f2478-108">Материал указан для отображения на поверхности объекта (линейный градиент в данном образце) с использованием <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> свойства <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span><span class="sxs-lookup"><span data-stu-id="f2478-108">A material is specified to be displayed on the surface of the object (linear gradient in this sample) using the <xref:System.Windows.Media.Media3D.GeometryModel3D.Material%2A> property of <xref:System.Windows.Media.Media3D.GeometryModel3D>.</span></span>  
  
- <span data-ttu-id="f2478-109">Свет создается, чтобы сиять <xref:System.Windows.Media.Media3D.DirectionalLight>на объекте с помощью.</span><span class="sxs-lookup"><span data-stu-id="f2478-109">A light is created to shine on the object using <xref:System.Windows.Media.Media3D.DirectionalLight>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2478-110">Пример</span><span class="sxs-lookup"><span data-stu-id="f2478-110">Example</span></span>  
 <span data-ttu-id="f2478-111">В приведенном ниже коде показано, как создать 3D-сцену в XAML.</span><span class="sxs-lookup"><span data-stu-id="f2478-111">The code below shows how to create a 3D scene in XAML.</span></span>  
  
 [!code-xaml[3DGallery_snip#Basic3DShapeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/Basic3DShapeExample.xaml#basic3dshapeexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="f2478-112">Пример</span><span class="sxs-lookup"><span data-stu-id="f2478-112">Example</span></span>  
 <span data-ttu-id="f2478-113">В приведенном ниже коде показано, как создать ту же 3D-сцену в процедурном коде.</span><span class="sxs-lookup"><span data-stu-id="f2478-113">The code below shows how to create the same 3D scene in procedural code.</span></span>  
  
 [!code-csharp[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/Basic3DShapeExample.cs#basic3dshapecodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#Basic3DShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/basic3dshapeexample.vb#basic3dshapecodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f2478-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f2478-114">See also</span></span>

- [<span data-ttu-id="f2478-115">3D Графика Обзор</span><span class="sxs-lookup"><span data-stu-id="f2478-115">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
