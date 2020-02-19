---
title: Практическое руководство. Анимация объекта вдоль пути (матричная анимация)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- animation [WPF], objects along paths (matrix animation)
- matrix animation [WPF]
ms.assetid: 7000e697-1414-468c-b915-cf66062fc49e
ms.openlocfilehash: 7dfc233fe60e1cea293edc44a2bba79dc6962f7c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452913"
---
# <a name="how-to-animate-an-object-along-a-path-matrix-animation"></a><span data-ttu-id="8e93b-102">Практическое руководство. Анимация объекта вдоль пути (матричная анимация)</span><span class="sxs-lookup"><span data-stu-id="8e93b-102">How to: Animate an Object Along a Path (Matrix Animation)</span></span>
<span data-ttu-id="8e93b-103">В этом примере показано, как использовать класс <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> для анимации объекта вдоль пути, определенного <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="8e93b-103">This example shows how to use the <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> class to animate an object along a path that is defined by a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e93b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8e93b-104">Example</span></span>  
 <span data-ttu-id="8e93b-105">Следующий пример анимирует объект вдоль пути следующим образом:</span><span class="sxs-lookup"><span data-stu-id="8e93b-105">The following example animates an object along a path by doing the following:</span></span>  
  
- <span data-ttu-id="8e93b-106">Применяет <xref:System.Windows.Media.MatrixTransform> к объекту, чтобы переместить его.</span><span class="sxs-lookup"><span data-stu-id="8e93b-106">Applies a <xref:System.Windows.Media.MatrixTransform> to the object in order to move it.</span></span>  
  
- <span data-ttu-id="8e93b-107">Определяет путь с помощью <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="8e93b-107">Defines the path by using a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
- <span data-ttu-id="8e93b-108">Создает <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> и использует его для анимации свойства <xref:System.Windows.Media.Matrix> <xref:System.Windows.Media.MatrixTransform>.</span><span class="sxs-lookup"><span data-stu-id="8e93b-108">Creates a <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> and uses it to animate the <xref:System.Windows.Media.Matrix> property of the <xref:System.Windows.Media.MatrixTransform>.</span></span> <span data-ttu-id="8e93b-109"><xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> принимает <xref:System.Windows.Media.PathGeometry> и использует его для создания значений <xref:System.Windows.Media.Matrix>.</span><span class="sxs-lookup"><span data-stu-id="8e93b-109">The <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> takes the <xref:System.Windows.Media.PathGeometry> and uses it to generate <xref:System.Windows.Media.Matrix> values.</span></span>  
  
 [!code-xaml[PathAnimationGallery_snippet#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexample.xaml#matrixanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExample.cs#matrixanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExample.vb#matrixanimationusingpathwholepage)]  
  
 <span data-ttu-id="8e93b-110">Полный пример см. в разделе [Пример анимации по путям](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span><span class="sxs-lookup"><span data-stu-id="8e93b-110">For the complete sample, see [Path Animation Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations).</span></span> <span data-ttu-id="8e93b-111">Дополнительные сведения о геометрических путях см. в разделе [Общие сведения о геометрии](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8e93b-111">For more information about geometric paths, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e93b-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8e93b-112">See also</span></span>

- [<span data-ttu-id="8e93b-113">Общие сведения об эффектах анимации</span><span class="sxs-lookup"><span data-stu-id="8e93b-113">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="8e93b-114">Пример анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="8e93b-114">Path Animation Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/PathAnimations)
- [<span data-ttu-id="8e93b-115">Практические руководства, посвященные анимации вдоль пути</span><span class="sxs-lookup"><span data-stu-id="8e93b-115">Path Animation How-to Topics</span></span>](path-animation-how-to-topics.md)
