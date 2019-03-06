---
title: Практическое руководство. Геометрия проверки нажатия в визуальном объекте
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: e51dd73a65666ffee5958325079e8f06f13ac61b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363804"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a><span data-ttu-id="229a8-102">Практическое руководство. Геометрия проверки нажатия в визуальном объекте</span><span class="sxs-lookup"><span data-stu-id="229a8-102">How to: Hit Test Geometry in a Visual</span></span>
<span data-ttu-id="229a8-103">В этом примере показано, как выполнить проверку попадания для визуального объекта, который состоит из одного или нескольких <xref:System.Windows.Media.Geometry> объектов.</span><span class="sxs-lookup"><span data-stu-id="229a8-103">This example shows how to perform a hit test on a visual object that is composed of one or more <xref:System.Windows.Media.Geometry> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="229a8-104">Пример</span><span class="sxs-lookup"><span data-stu-id="229a8-104">Example</span></span>  
 <span data-ttu-id="229a8-105">В следующем примере показано, как получить <xref:System.Windows.Media.DrawingGroup> из визуальный объект, который использует <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="229a8-105">The following example shows how to retrieve the <xref:System.Windows.Media.DrawingGroup> from a visual object that uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method.</span></span> <span data-ttu-id="229a8-106">Затем выполняется попадания на отображаемом содержимом каждого рисунка в <xref:System.Windows.Media.DrawingGroup> для определения, какой геометрический объект произошло попадание.</span><span class="sxs-lookup"><span data-stu-id="229a8-106">A hit test is then performed on the rendered content of each drawing in the <xref:System.Windows.Media.DrawingGroup> to determine which geometry was hit.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="229a8-107">В большинстве случаев можно использовать <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> метод для определения попадания курсора на любой из отображаемого содержимого визуального элемента.</span><span class="sxs-lookup"><span data-stu-id="229a8-107">In most cases, you would use the <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> method to determine whether a point intersects any of the rendered content of a visual.</span></span>  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 <span data-ttu-id="229a8-108"><xref:System.Windows.Media.Geometry.FillContains%2A> Это перегруженный метод, позволяющий попадания с использованием указанного <xref:System.Windows.Point> или <xref:System.Windows.Media.Geometry>.</span><span class="sxs-lookup"><span data-stu-id="229a8-108">The <xref:System.Windows.Media.Geometry.FillContains%2A> method is an overloaded method that allows you to hit test by using a specified <xref:System.Windows.Point> or <xref:System.Windows.Media.Geometry>.</span></span> <span data-ttu-id="229a8-109">Если линия геометрического объекта штрихованная, штрих может выходить за границы заполнения.</span><span class="sxs-lookup"><span data-stu-id="229a8-109">If a geometry is stroked, the stroke can extend outside the fill bounds.</span></span> <span data-ttu-id="229a8-110">В этом случае необходимо вызвать <xref:System.Windows.Media.Geometry.StrokeContains%2A> в дополнение к <xref:System.Windows.Media.Geometry.FillContains%2A>.</span><span class="sxs-lookup"><span data-stu-id="229a8-110">In which case, you may want to call <xref:System.Windows.Media.Geometry.StrokeContains%2A> in addition to <xref:System.Windows.Media.Geometry.FillContains%2A>.</span></span>  
  
 <span data-ttu-id="229a8-111">Вы также можете предоставить <xref:System.Windows.Media.ToleranceType> , используемый в целях спрямления кривой Безье.</span><span class="sxs-lookup"><span data-stu-id="229a8-111">You can also provide a <xref:System.Windows.Media.ToleranceType> that is used for the purposes of Bezier flattening.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="229a8-112">В этом примере не учитываются преобразования или обрезка, которые могут быть применены к геометрическому объекту.</span><span class="sxs-lookup"><span data-stu-id="229a8-112">This sample does not take into account any transforms or clipping that may be applied to the geometry.</span></span> <span data-ttu-id="229a8-113">Кроме того этот пример не будет работать с элементом управления со стилями, поскольку он не имеет никаких рисунков, непосредственно связанных с ним.</span><span class="sxs-lookup"><span data-stu-id="229a8-113">In addition, this sample will not work with a styled control, since it does not have any drawings directly associated with it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="229a8-114">См. также</span><span class="sxs-lookup"><span data-stu-id="229a8-114">See also</span></span>
- [<span data-ttu-id="229a8-115">Проверка нажатия на визуальном уровне</span><span class="sxs-lookup"><span data-stu-id="229a8-115">Hit Testing in the Visual Layer</span></span>](hit-testing-in-the-visual-layer.md)
- [<span data-ttu-id="229a8-116">Проверка нажатия с использованием геометрии в качестве параметра</span><span class="sxs-lookup"><span data-stu-id="229a8-116">Hit Test Using Geometry as a Parameter</span></span>](how-to-hit-test-using-geometry-as-a-parameter.md)
