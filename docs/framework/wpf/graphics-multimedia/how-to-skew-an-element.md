---
title: Практическое руководство. Отклонение элемента
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 10b00044c1c518641281e2e72cdb5a68474b5170
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112028"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="58a83-102">Практическое руководство. Отклонение элемента</span><span class="sxs-lookup"><span data-stu-id="58a83-102">How to: Skew an Element</span></span>
<span data-ttu-id="58a83-103">В этом примере <xref:System.Windows.Media.SkewTransform> показано, как использовать элемент для искажать элемент.</span><span class="sxs-lookup"><span data-stu-id="58a83-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="58a83-104">Отклонение (или срез) — это преобразование, которое неравномерно растягивает пространство координат.</span><span class="sxs-lookup"><span data-stu-id="58a83-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="58a83-105">Одним из типичных видов использования <xref:System.Windows.Media.SkewTransform> является моделирование 3D глубины в 2D-объектах.</span><span class="sxs-lookup"><span data-stu-id="58a83-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating 3D depth in 2D objects.</span></span>  
  
 <span data-ttu-id="58a83-106">Используйте <xref:System.Windows.Media.SkewTransform.CenterX%2A> <xref:System.Windows.Media.SkewTransform.CenterY%2A> и свойства, чтобы указать центральную точку <xref:System.Windows.Media.SkewTransform>.</span><span class="sxs-lookup"><span data-stu-id="58a83-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="58a83-107">Используйте <xref:System.Windows.Media.SkewTransform.AngleX%2A> <xref:System.Windows.Media.SkewTransform.AngleY%2A> и свойства, чтобы указать угол перекоса x-оси и y-оси, и исказить текущую систему координат вдоль этих осей.</span><span class="sxs-lookup"><span data-stu-id="58a83-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="58a83-108">Чтобы предсказать эффект преобразования перекоса, учтите, что <xref:System.Windows.Media.SkewTransform.AngleX%2A> перекосы значений x-оси относительно исходной системы координат.</span><span class="sxs-lookup"><span data-stu-id="58a83-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="58a83-109">Таким образом, <xref:System.Windows.Media.SkewTransform.AngleX%2A> для 30, y-оси вращается 30 градусов через происхождение и искажает значения в x- на 30 градусов от этого происхождения.</span><span class="sxs-lookup"><span data-stu-id="58a83-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="58a83-110">Аналогичным образом, <xref:System.Windows.Media.SkewTransform.AngleY%2A> из 30 перекосы y- значения формы на 30 градусов от происхождения.</span><span class="sxs-lookup"><span data-stu-id="58a83-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="58a83-111">Обратите внимание, что это не то же самое, что перенос (перемещение) системы координат на 30 градусов по осям X и Y.</span><span class="sxs-lookup"><span data-stu-id="58a83-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="58a83-112">Следующий пример применяется горизонтальный перекос 45 градусов <xref:System.Windows.Shapes.Rectangle> к от центральной точки (0,0).</span><span class="sxs-lookup"><span data-stu-id="58a83-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58a83-113">Пример</span><span class="sxs-lookup"><span data-stu-id="58a83-113">Example</span></span>  
 [!code-xaml[transformsSample#41](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="58a83-114">Следующий пример применяется горизонтальный перекос 45 градусов <xref:System.Windows.Shapes.Rectangle> к от центральной точки (25,25).</span><span class="sxs-lookup"><span data-stu-id="58a83-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="58a83-115">Следующий пример применяется вертикальный перекос 45 градусов <xref:System.Windows.Shapes.Rectangle> к от центральной точки (25,25).</span><span class="sxs-lookup"><span data-stu-id="58a83-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="58a83-116">На следующем рисунке показаны отклонения, использованные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="58a83-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="58a83-117">![Примеры SkewTransform](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="58a83-117">![SkewTransform examples](./media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="58a83-118">Показаны три примера SkewTransform</span><span class="sxs-lookup"><span data-stu-id="58a83-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="58a83-119">Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)</span><span class="sxs-lookup"><span data-stu-id="58a83-119">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58a83-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="58a83-120">See also</span></span>

- <xref:System.Windows.Media.Transform>
- <xref:System.Windows.Media.SkewTransform>
- [<span data-ttu-id="58a83-121">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="58a83-121">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="58a83-122">Как-к темам</span><span class="sxs-lookup"><span data-stu-id="58a83-122">How-to Topics</span></span>](transformations-how-to-topics.md)
