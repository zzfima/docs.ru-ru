---
title: Практическое руководство. Проверка попадания геометрического объекта в визуальный объект
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 52b9b99b0af38d797e4a3c98dc0979211c930c1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923383"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="9ed56-102">Практическое руководство. Проверка попадания геометрического объекта в визуальный объект</span><span class="sxs-lookup"><span data-stu-id="9ed56-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="9ed56-103">В этом примере показано, как выполнить проверку нажатия для визуального объекта, состоящего из одного или <xref:System.Windows.Media.Geometry> нескольких объектов.</span><span class="sxs-lookup"><span data-stu-id="9ed56-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ed56-104">Пример</span><span class="sxs-lookup"><span data-stu-id="9ed56-104">Example</span></span>  
 <span data-ttu-id="9ed56-105">В следующем примере показано, <xref:System.Windows.Media.DrawingGroup> как получить из визуального объекта, <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> использующего метод.</span><span class="sxs-lookup"><span data-stu-id="9ed56-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="9ed56-106">Затем выполняется проверка нажатия для отображаемого содержимого каждого рисунка в, <xref:System.Windows.Media.DrawingGroup> чтобы определить, какая геометрия была достигнута.</span><span class="sxs-lookup"><span data-stu-id="9ed56-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ed56-107">В большинстве случаев для определения того, пересекается ли точка с отображаемым содержимым визуального элемента, используется <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="9ed56-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="9ed56-108">Метод является перегруженным методом, который позволяет выполнять проверку попадания с помощью указанного <xref:System.Windows.Point> или <xref:System.Windows.Media.Geometry>. <xref:System.Windows.Media.Geometry.FillContains%2A></span><span class="sxs-lookup"><span data-stu-id="9ed56-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="9ed56-109">Если линия геометрического объекта штрихованная, штрих может выходить за границы заполнения.</span><span class="sxs-lookup"><span data-stu-id="9ed56-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="9ed56-110">В этом случае может потребоваться вызов <xref:System.Windows.Media.Geometry.StrokeContains%2A> в дополнение к. <xref:System.Windows.Media.Geometry.FillContains%2A></span><span class="sxs-lookup"><span data-stu-id="9ed56-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="9ed56-111">Можно также предоставить <xref:System.Windows.Media.ToleranceType> , который используется в целях спрямления Безье.</span><span class="sxs-lookup"><span data-stu-id="9ed56-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ed56-112">В этом примере не учитываются преобразования или обрезка, которые могут быть применены к геометрическому объекту.</span><span class="sxs-lookup"><span data-stu-id="9ed56-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="9ed56-113">Кроме того этот пример не будет работать с элементом управления со стилями, поскольку он не имеет никаких рисунков, непосредственно связанных с ним.</span><span class="sxs-lookup"><span data-stu-id="9ed56-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ed56-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9ed56-114">See also</span></span>

- [<span data-ttu-id="9ed56-115">Проверка нажатия на визуальном уровне</span><span class="sxs-lookup"><span data-stu-id="9ed56-115">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="9ed56-116">Проверка нажатия с использованием геометрии в качестве параметра</span><span class="sxs-lookup"><span data-stu-id="9ed56-116">Hit Test Using Geometry as a Parameter</span></span>](how-to-hit-test-using-geometry-as-a-parameter.md)
