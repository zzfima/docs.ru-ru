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
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112067"
---
# <a name="how-to-rotate-an-object"></a><span data-ttu-id="3da56-102">Практическое руководство. Вращение объекта</span><span class="sxs-lookup"><span data-stu-id="3da56-102">How to: Rotate an Object</span></span>
<span data-ttu-id="3da56-103">В данном примере показано, как можно вращать объект.</span><span class="sxs-lookup"><span data-stu-id="3da56-103">This example shows how to rotate an object.</span></span> <span data-ttu-id="3da56-104">Пример сначала создает, <xref:System.Windows.Media.RotateTransform> а затем определяет <xref:System.Windows.Media.RotateTransform.Angle%2A> его в градусах.</span><span class="sxs-lookup"><span data-stu-id="3da56-104">The example first creates a <xref:System.Windows.Media.RotateTransform> and then specifies its <xref:System.Windows.Media.RotateTransform.Angle%2A> in degrees.</span></span>  
  
 <span data-ttu-id="3da56-105">Следующий пример поворачивает <xref:System.Windows.Shapes.Polyline> объект на 45 градусов вокруг его верхнего левого угла.</span><span class="sxs-lookup"><span data-stu-id="3da56-105">The following example rotates a <xref:System.Windows.Shapes.Polyline> object 45 degrees about its upper-left corner.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3da56-106">Пример</span><span class="sxs-lookup"><span data-stu-id="3da56-106">Example</span></span>  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 <span data-ttu-id="3da56-107">И <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> свойства <xref:System.Windows.Media.RotateTransform> указывают точку, о которой вращается объект.</span><span class="sxs-lookup"><span data-stu-id="3da56-107">The <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties of the <xref:System.Windows.Media.RotateTransform> specify the point about which the object is rotated.</span></span> <span data-ttu-id="3da56-108">Это центральная точка выражается в пространстве координат преобразуемого элемента.</span><span class="sxs-lookup"><span data-stu-id="3da56-108">This center point is expressed in the coordinate space of the element that is transformed.</span></span> <span data-ttu-id="3da56-109">По умолчанию поворот выполняется относительно точки (0,0), которая является верхним левым углом объекта для преобразования.</span><span class="sxs-lookup"><span data-stu-id="3da56-109">By default, the rotation is applied to (0,0), which is the upper-left corner of the object to transform.</span></span>  
  
 <span data-ttu-id="3da56-110">Следующий пример поворачивает <xref:System.Windows.Shapes.Polyline> объект по часовой стрелке на 45 градусов вокруг точки (25,50).</span><span class="sxs-lookup"><span data-stu-id="3da56-110">The next example rotates a <xref:System.Windows.Shapes.Polyline> object clockwise 45 degrees about the point (25,50).</span></span>  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 <span data-ttu-id="3da56-111">На следующей иллюстрации показаны <xref:System.Windows.Media.Transform> результаты применения к двум объектам.</span><span class="sxs-lookup"><span data-stu-id="3da56-111">The following illustration shows the results of applying a <xref:System.Windows.Media.Transform> to the two objects.</span></span>  
  
 <span data-ttu-id="3da56-112">![Повороты на 45 градусов с разными центральными точками](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="3da56-112">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
<span data-ttu-id="3da56-113">Два объекта, повернутые на 45 градусов, с разными центрами вращения</span><span class="sxs-lookup"><span data-stu-id="3da56-113">Two objects that rotate 45 degrees from different rotational centers</span></span>  
  
 <span data-ttu-id="3da56-114">В <xref:System.Windows.Shapes.Polyline> предыдущих примерах <xref:System.Windows.UIElement>является .</span><span class="sxs-lookup"><span data-stu-id="3da56-114">The <xref:System.Windows.Shapes.Polyline> in the previous examples is a <xref:System.Windows.UIElement>.</span></span> <span data-ttu-id="3da56-115">При подаче <xref:System.Windows.Media.Transform> заявления <xref:System.Windows.UIElement.RenderTransform%2A> на <xref:System.Windows.UIElement>свойство объекта <xref:System.Windows.UIElement.RenderTransformOrigin%2A> можно использовать свойство <xref:System.Windows.Media.Transform> для указания происхождения для каждого, что вы применяете к элементу.</span><span class="sxs-lookup"><span data-stu-id="3da56-115">When you apply a <xref:System.Windows.Media.Transform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of a <xref:System.Windows.UIElement>, you can use the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to specify an origin for every <xref:System.Windows.Media.Transform> that you apply to the element.</span></span> <span data-ttu-id="3da56-116">Поскольку <xref:System.Windows.UIElement.RenderTransformOrigin%2A> свойство использует относительные координаты, можно применить преобразование к центру элемента, даже если вы не знаете его размер.</span><span class="sxs-lookup"><span data-stu-id="3da56-116">Because the <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property uses relative coordinates, you can apply a transformation to the center of the element even if you do not know its size.</span></span> <span data-ttu-id="3da56-117">Для получения дополнительной информации и, например, [см.](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md)</span><span class="sxs-lookup"><span data-stu-id="3da56-117">For more information and for an example, see [Specify the Origin of a Transform by Using Relative Values](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).</span></span>  
  
 <span data-ttu-id="3da56-118">Для полного образца [см.](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms)</span><span class="sxs-lookup"><span data-stu-id="3da56-118">For the complete sample, see [2D Transforms Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da56-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3da56-119">See also</span></span>

- <xref:System.Windows.Media.Transform>
- [<span data-ttu-id="3da56-120">Общие сведения о классах Transform</span><span class="sxs-lookup"><span data-stu-id="3da56-120">Transforms Overview</span></span>](transforms-overview.md)
- [<span data-ttu-id="3da56-121">Как-к темам</span><span class="sxs-lookup"><span data-stu-id="3da56-121">How-to Topics</span></span>](transformations-how-to-topics.md)
