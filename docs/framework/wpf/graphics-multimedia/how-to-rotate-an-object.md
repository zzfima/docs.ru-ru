---
title: Практическое руководство. Вращение объекта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: 7eb562d81bdd8c9187672b31ed08ed6ac27da41c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="3ce97-102">Практическое руководство. Вращение объекта</span><span class="sxs-lookup"><span data-stu-id="3ce97-102">How to: Rotate an Object</span></span>
<span data-ttu-id="3ce97-103">В данном примере показано, как можно вращать объект.</span><span class="sxs-lookup"><span data-stu-id="3ce97-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="3ce97-104">В примере сначала создается <xref:System.Windows.Media.RotateTransform> и затем указывает его <xref:System.Windows.Media.RotateTransform.Angle%2A> в градусах.</span><span class="sxs-lookup"><span data-stu-id="3ce97-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="3ce97-105">Следующий пример изменяет <xref:System.Windows.Shapes.Polyline> объекта 45 градусов относительно его верхнего левого угла.</span><span class="sxs-lookup"><span data-stu-id="3ce97-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ce97-106">Пример</span><span class="sxs-lookup"><span data-stu-id="3ce97-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="3ce97-107"><xref:System.Windows.Media.RotateTransform.CenterX%2A> И <xref:System.Windows.Media.RotateTransform.CenterY%2A> свойства <xref:System.Windows.Media.RotateTransform> укажите точку, о котором поворота объекта.</span><span class="sxs-lookup"><span data-stu-id="3ce97-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="3ce97-108">Это центральная точка выражается в пространстве координат преобразуемого элемента.</span><span class="sxs-lookup"><span data-stu-id="3ce97-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="3ce97-109">По умолчанию поворот выполняется относительно точки (0,0), которая является верхним левым углом объекта для преобразования.</span><span class="sxs-lookup"><span data-stu-id="3ce97-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="3ce97-110">Следующий пример изменяет <xref:System.Windows.Shapes.Polyline> объекта по часовой стрелке на 45 градусов относительно точки (25,50).</span><span class="sxs-lookup"><span data-stu-id="3ce97-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="3ce97-111">На следующем рисунке показан результат применения <xref:System.Windows.Media.Transform> к двум объектам.</span><span class="sxs-lookup"><span data-stu-id="3ce97-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="3ce97-112">![Поворот на 45 градусов вокруг различных точек](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="3ce97-112">![45 degree rotations with different center points](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="3ce97-113">Два объекта, повернутые на 45 градусов, с разными центрами вращения</span><span class="sxs-lookup"><span data-stu-id="3ce97-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="3ce97-114"><xref:System.Windows.Shapes.Polyline> В предыдущих примерах <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="3ce97-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="3ce97-115">При применении <xref:System.Windows.Media.Transform> для <xref:System.Windows.UIElement.RenderTransform%2A> свойство <xref:System.Windows.UIElement>, можно использовать <xref:System.Windows.UIElement.RenderTransformOrigin%2A> свойство, чтобы указать источник для каждого <xref:System.Windows.Media.Transform> , относящиеся к элементу.</span><span class="sxs-lookup"><span data-stu-id="3ce97-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="3ce97-116">Поскольку <xref:System.Windows.UIElement.RenderTransformOrigin%2A> свойство использует относительные координаты, можно применить преобразования к центру элемента, даже если вы не знаете его размер.</span><span class="sxs-lookup"><span data-stu-id="3ce97-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="3ce97-117">Дополнительные сведения и пример см. в разделе [укажите источника преобразования с помощью относительных значений](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span><span class="sxs-lookup"><span data-stu-id="3ce97-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](../../../../docs/framework/wpf/graphics-multimedia/how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="3ce97-118">Полный пример см. в разделе [Примеры двумерных преобразований](http://go.microsoft.com/fwlink/?LinkID=158252).</span><span class="sxs-lookup"><span data-stu-id="3ce97-118">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ce97-119">См. также</span><span class="sxs-lookup"><span data-stu-id="3ce97-119">See Also</span></span>  
 <xref:System.Windows.Media.Transform>  
 [<span data-ttu-id="3ce97-120">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="3ce97-120">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)  
 [<span data-ttu-id="3ce97-121">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="3ce97-121">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transformations-how-to-topics.md)
