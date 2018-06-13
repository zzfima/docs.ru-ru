---
title: Практическое руководство. Отклонение элемента
ms.date: 03/30/2017
helpviewer_keywords:
- skewing elements [WPF]
- graphics [WPF], skewing elements
- classes [WPF], SkewTransform
ms.assetid: 56b65f2f-dc6e-4238-923f-ca44ec53c52f
ms.openlocfilehash: 8bd860a71253a55cb3148426dbb61cbd3477e95e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561567"
---
# <a name="how-to-skew-an-element"></a><span data-ttu-id="0c6bd-102">Практическое руководство. Отклонение элемента</span><span class="sxs-lookup"><span data-stu-id="0c6bd-102">How to: Skew an Element</span></span>
<span data-ttu-id="0c6bd-103">В этом примере показано, как использовать <xref:System.Windows.Media.SkewTransform> для наклона элемента.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-103">This example shows how to use a <xref:System.Windows.Media.SkewTransform> to skew an element.</span></span> <span data-ttu-id="0c6bd-104">Отклонение (или срез) — это преобразование, которое неравномерно растягивает пространство координат.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-104">A skew, which is also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="0c6bd-105">Одним из примеров использования <xref:System.Windows.Media.SkewTransform> является имитация [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] глубина в [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] объектов.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-105">One typical use of a <xref:System.Windows.Media.SkewTransform> is for simulating [!INCLUDE[TLA#tla_3d](../../../../includes/tlasharptla-3d-md.md)] depth in [!INCLUDE[TLA#tla_2d](../../../../includes/tlasharptla-2d-md.md)] objects.</span></span>  
  
 <span data-ttu-id="0c6bd-106">Используйте <xref:System.Windows.Media.SkewTransform.CenterX%2A> и <xref:System.Windows.Media.SkewTransform.CenterY%2A> точка свойства для указания центра <xref:System.Windows.Media.SkewTransform>.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-106">Use the <xref:System.Windows.Media.SkewTransform.CenterX%2A> and <xref:System.Windows.Media.SkewTransform.CenterY%2A> properties to specify the center point of the <xref:System.Windows.Media.SkewTransform>.</span></span>  
  
 <span data-ttu-id="0c6bd-107">Используйте <xref:System.Windows.Media.SkewTransform.AngleX%2A> и <xref:System.Windows.Media.SkewTransform.AngleY%2A> свойства для указания угол отклонения оси x и оси y и наклонять текущей системы координат по осям эти.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-107">Use the <xref:System.Windows.Media.SkewTransform.AngleX%2A> and <xref:System.Windows.Media.SkewTransform.AngleY%2A> properties to specify the skew angle of the x-axis and y-axis, and to skew the current coordinate system along these axes.</span></span>  
  
 <span data-ttu-id="0c6bd-108">Чтобы спрогнозировать результат наклона, примите во внимание <xref:System.Windows.Media.SkewTransform.AngleX%2A> наклон значений по оси x относительно исходной системы координат.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-108">To predict the effect of a skew transformation, consider that <xref:System.Windows.Media.SkewTransform.AngleX%2A> skews x-axis values relative to the original coordinate system.</span></span> <span data-ttu-id="0c6bd-109">Таким образом, для <xref:System.Windows.Media.SkewTransform.AngleX%2A> равно 30, ось y поворачивается на 30 градусов через начало координат и наклон значений в x-30 градусов от этого начала координат.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-109">Therefore, for an <xref:System.Windows.Media.SkewTransform.AngleX%2A> of 30, the y-axis rotates 30 degrees through the origin and skews the values in x- by 30 degrees from that origin.</span></span> <span data-ttu-id="0c6bd-110">Аналогичным образом <xref:System.Windows.Media.SkewTransform.AngleY%2A> 30 наклон значений y фигуры на 30 градусов от начала координат.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-110">Likewise, an <xref:System.Windows.Media.SkewTransform.AngleY%2A> of 30 skews the y- values of the shape by 30 degrees from the origin.</span></span> <span data-ttu-id="0c6bd-111">Обратите внимание, что это не то же самое, что перенос (перемещение) системы координат на 30 градусов по осям X и Y.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-111">Note that this is not the same effect as translating (moving) the coordinate system by 30 degrees in x- or y-.</span></span>  
  
 <span data-ttu-id="0c6bd-112">В следующем примере применяется горизонтальный наклон в 45 градусов <xref:System.Windows.Shapes.Rectangle> относительно центральной точки (0,0).</span><span class="sxs-lookup"><span data-stu-id="0c6bd-112">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (0,0).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c6bd-113">Пример</span><span class="sxs-lookup"><span data-stu-id="0c6bd-113">Example</span></span>  
 [!code-xaml[transformsSample#41](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#41)]  
  
 <span data-ttu-id="0c6bd-114">В следующем примере применяется горизонтальный наклон в 45 градусов <xref:System.Windows.Shapes.Rectangle> относительно центральной точки (25,25).</span><span class="sxs-lookup"><span data-stu-id="0c6bd-114">The following example applies a horizontal skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#42](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#42)]  
  
 <span data-ttu-id="0c6bd-115">В следующем примере применяется вертикальной искажение 45 градусов <xref:System.Windows.Shapes.Rectangle> относительно центральной точки (25,25).</span><span class="sxs-lookup"><span data-stu-id="0c6bd-115">The following example applies a vertical skew of 45 degrees to a <xref:System.Windows.Shapes.Rectangle> from a center point of (25,25).</span></span>  
  
 [!code-xaml[transformsSample#43](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/SkewTransformExample.xaml#43)]  
  
 <span data-ttu-id="0c6bd-116">На следующем рисунке показаны отклонения, использованные в этом примере.</span><span class="sxs-lookup"><span data-stu-id="0c6bd-116">The following illustration shows the different skews that are used in this example.</span></span>  
  
 <span data-ttu-id="0c6bd-117">![Примеры SkewTransform](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span><span class="sxs-lookup"><span data-stu-id="0c6bd-117">![SkewTransform examples](../../../../docs/framework/wpf/graphics-multimedia/media/img-wcpsdk-graphicsmm-skewtransformexample.gif "img_wcpsdk_graphicsmm_skewtransformexample")</span></span>  
<span data-ttu-id="0c6bd-118">Показаны три примера SkewTransform</span><span class="sxs-lookup"><span data-stu-id="0c6bd-118">The three SkewTransform examples illustrated</span></span>  
  
 <span data-ttu-id="0c6bd-119">Полный пример см. в разделе [Примеры двумерных преобразований](http://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="0c6bd-119">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c6bd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="0c6bd-120">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 <xref:System.Windows.Media.SkewTransform>  
 [<span data-ttu-id="0c6bd-121">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="0c6bd-121">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="0c6bd-122">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="0c6bd-122">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
