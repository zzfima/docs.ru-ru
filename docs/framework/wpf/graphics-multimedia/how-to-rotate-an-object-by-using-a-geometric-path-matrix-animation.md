---
title: Практическое руководство. Поворот объекта с использованием геометрического пути (матрица анимации)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- geometric paths [WPF], rotating objects by
- rotating objects by geometric paths [WPF]
- matrix animation [WPF]
ms.assetid: 877dc9aa-6bdc-4beb-8772-3efaec32c0f0
ms.openlocfilehash: 63dc873a2b840ea3f870a8c60c5691ab271c1c9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187414"
---
# <a name="how-to-rotate-an-object-by-using-a-geometric-path-matrix-animation"></a><span data-ttu-id="8c786-102">Практическое руководство. Поворот объекта с использованием геометрического пути (матрица анимации)</span><span class="sxs-lookup"><span data-stu-id="8c786-102">How to: Rotate an Object by Using a Geometric Path (Matrix Animation)</span></span>
<span data-ttu-id="8c786-103">В этом примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> показано, <xref:System.Windows.Media.MatrixTransform> как использовать и использовать (поворот) объекта вдоль <xref:System.Windows.Media.PathGeometry> геометрического пути, определяемого объектом.</span><span class="sxs-lookup"><span data-stu-id="8c786-103">This example shows how to use a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and a <xref:System.Windows.Media.MatrixTransform> to rotate (pivot) an object along a geometric path defined by a <xref:System.Windows.Media.PathGeometry> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c786-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8c786-104">Example</span></span>  
 <span data-ttu-id="8c786-105">В следующем примере <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> используется объект <xref:System.Windows.Media.MatrixTransform.Matrix%2A> для анимировать свойство <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="8c786-105">The following example uses the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> object to animate the <xref:System.Windows.Media.MatrixTransform.Matrix%2A> property of a <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="8c786-106">Применяется <xref:System.Windows.Media.MatrixTransform> к кнопке и заставляет ее двигаться по изогнутому пути.</span><span class="sxs-lookup"><span data-stu-id="8c786-106">The <xref:System.Windows.Media.MatrixTransform> is applied to a button and causes it to move along a curved path.</span></span> <span data-ttu-id="8c786-107">Поскольку <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> свойство `true`настроено на то, что прямоугольник вращается по касательной пути.</span><span class="sxs-lookup"><span data-stu-id="8c786-107">Because the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> property is set to `true`, the rectangle rotates along the tangent of the path.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathdoesrotatewithtangentexample.xaml#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathDoesRotateWithTangentExample.cs#matrixanimationusingpathdoesrotatewithtangentwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathDoesRotateWithTangentWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathDoesRotateWithTangentExample.vb#matrixanimationusingpathdoesrotatewithtangentwholepage)]  
  
 <span data-ttu-id="8c786-108">Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)</span><span class="sxs-lookup"><span data-stu-id="8c786-108">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span>  
  
 <span data-ttu-id="8c786-109">Кодовая версия предыдущего <xref:System.Windows.Media.Animation.Storyboard> образца использовала <xref:System.Windows.Media.EllipseGeometry>a для анимации , хотя была применена только одна анимация.</span><span class="sxs-lookup"><span data-stu-id="8c786-109">The code version of the preceding sample used a <xref:System.Windows.Media.Animation.Storyboard> to animate the <xref:System.Windows.Media.EllipseGeometry>, even though only one animation was applied.</span></span> <span data-ttu-id="8c786-110">Проще всего применить одну анимацию к свойству в <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> коде — использовать метод.</span><span class="sxs-lookup"><span data-stu-id="8c786-110">An easier way to apply a single animation to a property in code is to use the <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> method.</span></span> <span data-ttu-id="8c786-111">Например, [см. Animate a Property без использования раскадровки.](how-to-animate-a-property-without-using-a-storyboard.md)</span><span class="sxs-lookup"><span data-stu-id="8c786-111">For an example, see [Animate a Property Without Using a Storyboard](how-to-animate-a-property-without-using-a-storyboard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c786-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8c786-112">See also</span></span>

- [<span data-ttu-id="8c786-113">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="8c786-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="8c786-114">Практические руководства, посвященные анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="8c786-114">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
- [<span data-ttu-id="8c786-115">Пример анимации по контуру</span><span class="sxs-lookup"><span data-stu-id="8c786-115">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
