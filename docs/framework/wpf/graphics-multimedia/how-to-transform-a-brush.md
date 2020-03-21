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
ms.openlocfilehash: b4484e2fc1ae3e969b02b1d8f3ae4ab2a035558e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187339"
---
# <a name="how-to-transform-a-brush"></a><span data-ttu-id="81bb1-102">Практическое руководство. Преобразование кисти</span><span class="sxs-lookup"><span data-stu-id="81bb1-102">How to: Transform a Brush</span></span>
<span data-ttu-id="81bb1-103">В этом примере <xref:System.Windows.Media.Brush> показано, как преобразовывать объекты, используя два их свойства преобразования: <xref:System.Windows.Media.Brush.RelativeTransform%2A> и <xref:System.Windows.Media.Brush.Transform%2A>.</span><span class="sxs-lookup"><span data-stu-id="81bb1-103">This example shows how to transform <xref:System.Windows.Media.Brush> objects by using their two transformation properties: <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A>.</span></span>  
  
 <span data-ttu-id="81bb1-104">В следующих <xref:System.Windows.Media.RotateTransform> примерах используется для <xref:System.Windows.Media.ImageBrush> вращения содержимого на 45 градусов.</span><span class="sxs-lookup"><span data-stu-id="81bb1-104">The following examples use a <xref:System.Windows.Media.RotateTransform> to rotate the content of an <xref:System.Windows.Media.ImageBrush> by 45 degrees.</span></span>  
  
 <span data-ttu-id="81bb1-105">Следующая иллюстрация <xref:System.Windows.Media.ImageBrush> показывает <xref:System.Windows.Media.RotateTransform>без <xref:System.Windows.Media.RotateTransform> , с <xref:System.Windows.Media.Brush.RelativeTransform%2A> применяется к <xref:System.Windows.Media.RotateTransform> собственности, и с применяется к собственности. <xref:System.Windows.Media.Brush.Transform%2A></span><span class="sxs-lookup"><span data-stu-id="81bb1-105">The following illustration shows the <xref:System.Windows.Media.ImageBrush> without a <xref:System.Windows.Media.RotateTransform>, with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property, and with the <xref:System.Windows.Media.RotateTransform> applied to the <xref:System.Windows.Media.Brush.Transform%2A> property.</span></span>  
  
 <span data-ttu-id="81bb1-106">![Параметры кисти RelativeTransform и Transform](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span><span class="sxs-lookup"><span data-stu-id="81bb1-106">![Brush RelativeTransform and Transform settings](./media/wcpsdk-graphicsmm-transformandrelativetransform.png "wcpsdk_graphicsmm_transformandrelativetransform")</span></span>  
  
## <a name="example"></a><span data-ttu-id="81bb1-107">Пример</span><span class="sxs-lookup"><span data-stu-id="81bb1-107">Example</span></span>  
 <span data-ttu-id="81bb1-108">Первый пример применяется <xref:System.Windows.Media.RotateTransform> <xref:System.Windows.Media.Brush.RelativeTransform%2A> к свойству <xref:System.Windows.Media.ImageBrush>.</span><span class="sxs-lookup"><span data-stu-id="81bb1-108">The first example applies a <xref:System.Windows.Media.RotateTransform> to the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property of an <xref:System.Windows.Media.ImageBrush>.</span></span> <span data-ttu-id="81bb1-109">Свойства <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> объекта <xref:System.Windows.Media.RotateTransform> установлены на 0,5, что является относительной координатой центральной точки этого содержимого.</span><span class="sxs-lookup"><span data-stu-id="81bb1-109">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of a <xref:System.Windows.Media.RotateTransform> object are both set to 0.5, which is the relative coordinate of the center point of this content.</span></span> <span data-ttu-id="81bb1-110">В результате содержимое <xref:System.Windows.Media.ImageBrush> вращается вокруг его центра.</span><span class="sxs-lookup"><span data-stu-id="81bb1-110">As a result, the <xref:System.Windows.Media.ImageBrush> content rotates about its center.</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushrelativetransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushrelativetransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushRelativeTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushrelativetransformexample)]  
  
 <span data-ttu-id="81bb1-111">Второй пример также <xref:System.Windows.Media.RotateTransform> применяется <xref:System.Windows.Media.ImageBrush>к ; однако в этом <xref:System.Windows.Media.Brush.Transform%2A> примере <xref:System.Windows.Media.Brush.RelativeTransform%2A> используется свойство вместо свойства.</span><span class="sxs-lookup"><span data-stu-id="81bb1-111">The second example also applies a <xref:System.Windows.Media.RotateTransform> to an <xref:System.Windows.Media.ImageBrush>; however, this example uses the <xref:System.Windows.Media.Brush.Transform%2A> property instead of the <xref:System.Windows.Media.Brush.RelativeTransform%2A> property.</span></span>  
  
 <span data-ttu-id="81bb1-112">Чтобы повернуть кисть вокруг ее центра, <xref:System.Windows.Media.RotateTransform.CenterY%2A> пример <xref:System.Windows.Media.RotateTransform> устанавливает <xref:System.Windows.Media.RotateTransform.CenterX%2A> и свойства объекта к абсолютным координатам.</span><span class="sxs-lookup"><span data-stu-id="81bb1-112">To rotate the brush about its center, the example sets the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> object to absolute coordinates.</span></span> <span data-ttu-id="81bb1-113">Так как эта кисть рисует прямоугольник размером 175 на 90 пикселей, центральная точка прямоугольника имеет координаты (87,5, 45).</span><span class="sxs-lookup"><span data-stu-id="81bb1-113">Because the brush paints a rectangle that is 175 by 90 pixels, the center point of the rectangle is (87.5, 45).</span></span>  
  
 [!code-csharp[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/BrushTransformExample.cs#imagebrushtransformexample)]
 [!code-vb[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/brushtransformexample.vb#imagebrushtransformexample)]
 [!code-xaml[BrushesIntroduction_snip#ImageBrushTransformExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/BrushTransformExample.xaml#imagebrushtransformexample)]  
  
 <span data-ttu-id="81bb1-114">Описание того, как <xref:System.Windows.Media.Brush.RelativeTransform%2A> <xref:System.Windows.Media.Brush.Transform%2A> работают и как работают свойства, можно ознакомьтесь с [обзором трансформации кисти.](brush-transformation-overview.md)</span><span class="sxs-lookup"><span data-stu-id="81bb1-114">For a description of how the <xref:System.Windows.Media.Brush.RelativeTransform%2A> and <xref:System.Windows.Media.Brush.Transform%2A> properties work, see the [Brush Transformation Overview](brush-transformation-overview.md).</span></span>  
  
 <span data-ttu-id="81bb1-115">Полный пример см. в разделе [Примеры кистей](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="81bb1-115">For the complete sample, see [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span> <span data-ttu-id="81bb1-116">Дополнительные сведения о кистях см. в разделе [Общие сведения о закраске сплошным цветом и градиентом](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="81bb1-116">For more information about brushes, see [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81bb1-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="81bb1-117">See also</span></span>

- [<span data-ttu-id="81bb1-118">Общие сведения о преобразованиях кистей</span><span class="sxs-lookup"><span data-stu-id="81bb1-118">Brush Transformation Overview</span></span>](brush-transformation-overview.md)
- [<span data-ttu-id="81bb1-119">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="81bb1-119">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="81bb1-120">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="81bb1-120">Transforms Overview</span></span>](transforms-overview.md)
