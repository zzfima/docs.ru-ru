---
title: Практическое руководство. Поворот объекта с использованием геометрического пути
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
ms.assetid: cb31ca4d-f05a-4c6b-9a18-4b6faaf38d45
ms.openlocfilehash: a351fdc936f634b7c57ba5a49e51501f7572a3c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186878"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path"></a><span data-ttu-id="455b7-102">Практическое руководство. Поворот объекта с использованием геометрического пути</span><span class="sxs-lookup"><span data-stu-id="455b7-102">How to: Rotate an Object by Using a Geometric Path</span></span>
<span data-ttu-id="455b7-103">Этот пример показывает, как повернуть (поворот) объекта вдоль геометрического <xref:System.Windows.Media.PathGeometry> пути, который определяется объектом.</span><span class="sxs-lookup"><span data-stu-id="455b7-103">This example shows how to rotate (pivot) an object along a geometric path that is defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="455b7-104">Пример</span><span class="sxs-lookup"><span data-stu-id="455b7-104">Example</span></span>  
 <span data-ttu-id="455b7-105">В следующем примере используются три <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> объекта для перемещения прямоугольника по геометрическому пути.</span><span class="sxs-lookup"><span data-stu-id="455b7-105">The following example uses three <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> objects to move a rectangle along a geometric path.</span></span>  
  
- <span data-ttu-id="455b7-106">Первый <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> <xref:System.Windows.Media.RotateTransform> оживляет, который наносится на прямоугольник.</span><span class="sxs-lookup"><span data-stu-id="455b7-106">The first <xref:System.Windows.Media.Animation.DoubleAnimationUsingPath> animates a <xref:System.Windows.Media.RotateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="455b7-107">Анимация формирует значения угла.</span><span class="sxs-lookup"><span data-stu-id="455b7-107">The animation generates angle values.</span></span> <span data-ttu-id="455b7-108">Это заставляет прямоугольник поворачиваться (вращаться) вдоль контуров пути.</span><span class="sxs-lookup"><span data-stu-id="455b7-108">It makes the rectangle rotate (pivot) along the contours of the path.</span></span>  
  
- <span data-ttu-id="455b7-109">Два других объекта <xref:System.Windows.Media.TranslateTransform.X%2A> оживляют <xref:System.Windows.Media.TranslateTransform.Y%2A> и <xref:System.Windows.Media.TranslateTransform> значения, которые применяются к прямоугольнику.</span><span class="sxs-lookup"><span data-stu-id="455b7-109">The other two objects animate the <xref:System.Windows.Media.TranslateTransform.X%2A> and <xref:System.Windows.Media.TranslateTransform.Y%2A> values of a <xref:System.Windows.Media.TranslateTransform> that is applied to the rectangle.</span></span> <span data-ttu-id="455b7-110">Это заставляет прямоугольник двигаться горизонтально и вертикально вдоль пути.</span><span class="sxs-lookup"><span data-stu-id="455b7-110">They make the rectangle move horizontally and vertically along the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/rotateanimationusingpathexample.xaml#rotateanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/RotateAnimationUsingPathExample.cs#rotateanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#RotateAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/RotateAnimationUsingPathExample.vb#rotateanimationusingpathwholepage)]  
  
 <span data-ttu-id="455b7-111">Другой способ повернуть объект с помощью геометрического <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> пути — <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> использовать `true`объект и установить его свойство.</span><span class="sxs-lookup"><span data-stu-id="455b7-111">Another way to rotate an object by using a geometric path is to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object and set its <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property to `true`.</span></span> <span data-ttu-id="455b7-112">Для получения дополнительной информации и примера [см.](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md)</span><span class="sxs-lookup"><span data-stu-id="455b7-112">For more information and an example, see [Rotate an Object by Using a Geometric Path (Matrix Animation)](how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation.md).</span></span>  
  
 <span data-ttu-id="455b7-113">Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)</span><span class="sxs-lookup"><span data-stu-id="455b7-113">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="455b7-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="455b7-114">See also</span></span>

- [<span data-ttu-id="455b7-115">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="455b7-115">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="455b7-116">Пример анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="455b7-116">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="455b7-117">Практические руководства, посвященные анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="455b7-117">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
