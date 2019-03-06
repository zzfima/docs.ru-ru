---
title: Практическое руководство. Преобразование кисти
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- brushes [WPF], rotating contents
- brushes [WPF], Transform property
- rotating contents of brushes [WPF]
ms.assetid: ebada2f9-f01f-4863-9ea2-c2e4e51610f1
ms.openlocfilehash: 990c82b4844ce3ca7f5b553b180280b6b37496ca
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373768"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="ce9ef-102">Практическое руководство. Преобразование кисти</span><span class="sxs-lookup"><span data-stu-id="ce9ef-102">How to: Transform a Brush</span></span>
<span data-ttu-id="ce9ef-103">В этом примере показано, как преобразовать <xref:System.Windows.Media.Brush> объектов с помощью двух свойств преобразования: <xref:System.Windows.Media.Brush.RelativeTransform%2A> и <xref:System.Windows.Media.Brush.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="ce9ef-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="ce9ef-104">В следующих примерах используется <xref:System.Windows.Media.RotateTransform> для поворота содержимого объекта <xref:System.Windows.Media.ImageBrush> на 45 градусов.</span><span class="sxs-lookup"><span data-stu-id="ce9ef-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="ce9ef-105">На следующем рисунке показано <xref:System.Windows.Media.ImageBrush> без <xref:System.Windows.Media.RotateTransform>, с помощью <xref:System.Windows.Media.RotateTransform> применяется к <xref:System.Windows.Media.Brush.RelativeTransform%2A> свойство и с <xref:System.Windows.Media.RotateTransform> применяется к <xref:System.Windows.Media.Brush.Transform%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="ce9ef-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="ce9ef-106">![Параметры RelativeTransform и Transform для кисти](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="ce9ef-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce9ef-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ce9ef-107">Example</span></span>  
 <span data-ttu-id="ce9ef-108">В первом примере применяется <xref:System.Windows.Media.RotateTransform> для <xref:System.Windows.Media.Brush.RelativeTransform%2A> свойство <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="ce9ef-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="ce9ef-109"><xref:System.Windows.Media.RotateTransform.CenterX%2A> И <xref:System.Windows.Media.RotateTransform.CenterY%2A> свойства <xref:System.Windows.Media.RotateTransform> объекта устанавливаются равными 0,5. это относительная координата центральной точки этого содержимого.</span><span class="sxs-lookup"><span data-stu-id="ce9ef-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="ce9ef-110">В результате <xref:System.Windows.Media.ImageBrush> содержимое вращается вокруг своего центра.</span><span class="sxs-lookup"><span data-stu-id="ce9ef-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="ce9ef-111">Во втором примере также применяется <xref:System.Windows.Media.RotateTransform> для <xref:System.Windows.Media.ImageBrush>, однако в этом примере используется <xref:System.Windows.Media.Brush.Transform%2A> вместо свойства <xref:System.Windows.Media.Brush.RelativeTransform%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="ce9ef-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="ce9ef-112">Чтобы повернуть кисть относительно ее центра, в этом примере <xref:System.Windows.Media.RotateTransform.CenterX%2A> и <xref:System.Windows.Media.RotateTransform.CenterY%2A> свойства <xref:System.Windows.Media.RotateTransform> абсолютные координаты.</span><span class="sxs-lookup"><span data-stu-id="ce9ef-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="ce9ef-113">Так как эта кисть рисует прямоугольник размером 175 на 90 пикселей, центральная точка прямоугольника имеет координаты (87,5, 45).</span><span class="sxs-lookup"><span data-stu-id="ce9ef-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="ce9ef-114">Описание того, как <xref:System.Windows.Media.Brush.RelativeTransform%2A> и <xref:System.Windows.Media.Brush.Transform%2A> свойства работы, см. в разделе [Общие сведения о преобразованиях кистей](brush-transformation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ce9ef-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="ce9ef-115">Полный пример см. в разделе [Примеры кистей](https://go.microsoft.com/fwlink/?LinkID=159973).</span><span class="sxs-lookup"><span data-stu-id="ce9ef-115">For the complete sample, see [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).</span></span> <span data-ttu-id="ce9ef-116">Дополнительные сведения о кистях см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ce9ef-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce9ef-117">См. также</span><span class="sxs-lookup"><span data-stu-id="ce9ef-117">See also</span></span>
- [<span data-ttu-id="ce9ef-118">Общие сведения о преобразованиях кистей</span><span class="sxs-lookup"><span data-stu-id="ce9ef-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="ce9ef-119">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="ce9ef-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="ce9ef-120">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="ce9ef-120">Transforms Overview</span></span>](transforms-overview.md)
