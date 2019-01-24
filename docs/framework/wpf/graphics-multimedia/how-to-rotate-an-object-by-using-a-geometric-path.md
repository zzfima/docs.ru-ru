---
title: Как выполнить Поворот объекта с использованием геометрического пути
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: cd8aaee7563d684e70dc29f1c293b091c1e6cff9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54661494"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="a0f16-102">Как выполнить Поворот объекта с использованием геометрического пути</span><span class="sxs-lookup"><span data-stu-id="a0f16-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="a0f16-103">В этом примере демонстрируется поворот (вращение) объекта вдоль геометрического пути, который определяется <xref:System.Windows.Media.PathGeometry> объекта.</span><span class="sxs-lookup"><span data-stu-id="a0f16-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0f16-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a0f16-104">Example</span></span>  
 <span data-ttu-id="a0f16-105">В следующем примере используется три <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> объекты для перемещения прямоугольника вдоль геометрического пути.</span><span class="sxs-lookup"><span data-stu-id="a0f16-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
-   <span data-ttu-id="a0f16-106">Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> анимирует <xref:System.Windows.Media.RotateTransform> , примененного к прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="a0f16-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="a0f16-107">Анимация формирует значения угла.</span><span class="sxs-lookup"><span data-stu-id="a0f16-107">The animation generates angle values.</span></span> <span data-ttu-id="a0f16-108">Это заставляет прямоугольник поворачиваться (вращаться) вдоль контуров пути.</span><span class="sxs-lookup"><span data-stu-id="a0f16-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
-   <span data-ttu-id="a0f16-109">Другие два объекта анимируют <xref:System.Windows.Media.TranslateTransform.X%2A> и <xref:System.Windows.Media.TranslateTransform.Y%2A> значения <xref:System.Windows.Media.TranslateTransform> , примененного к прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="a0f16-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="a0f16-110">Это заставляет прямоугольник двигаться горизонтально и вертикально вдоль пути.</span><span class="sxs-lookup"><span data-stu-id="a0f16-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="a0f16-111">Поворот объекта с использованием геометрического пути другим способом является использование <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> и задайте его <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="a0f16-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="a0f16-112">Дополнительные сведения и пример см. в разделе [поворот объекта с использованием геометрического пути (матричная анимация)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span><span class="sxs-lookup"><span data-stu-id="a0f16-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](../../../../docs/framework/wpf/graphics-multimedia/how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="a0f16-113">Полный пример см. в разделе [Пример анимации вдоль пути](https://go.microsoft.com/fwlink/?LinkID=160028).</span><span class="sxs-lookup"><span data-stu-id="a0f16-113">For the complete sample, see [Path Animation Sample](https://go.microsoft.com/fwlink/?LinkID=160028).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0f16-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a0f16-114">See also</span></span>
- [<span data-ttu-id="a0f16-115">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="a0f16-115">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
- [<span data-ttu-id="a0f16-116">Пример анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="a0f16-116">Path Animation Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160028)
- [<span data-ttu-id="a0f16-117">Практические руководства, посвященные анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="a0f16-117">Path Animation How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)
