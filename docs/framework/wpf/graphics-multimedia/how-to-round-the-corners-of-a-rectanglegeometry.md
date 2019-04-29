---
title: Практическое руководство. Скругление углов объекта RectangleGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: eb2f173bedb903e12b2795264c684524cfa09825
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651407"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="b570f-102">Практическое руководство. Скругление углов объекта RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="b570f-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="b570f-103">Для скругления углов <xref:System.Windows.Media.RectangleGeometry>, задайте его <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> свойства в значение больше нуля.</span><span class="sxs-lookup"><span data-stu-id="b570f-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="b570f-104">Чем больше значения, тем больше радиус скругления углов прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="b570f-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b570f-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b570f-105">Example</span></span>  
 <span data-ttu-id="b570f-106">В следующем примере показано несколько <xref:System.Windows.Media.RectangleGeometry> объектов с разными <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> параметры.</span><span class="sxs-lookup"><span data-stu-id="b570f-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="b570f-107"><xref:System.Windows.Media.RectangleGeometry> Объекты отображаются с помощью <xref:System.Windows.Shapes.Path> элементов.</span><span class="sxs-lookup"><span data-stu-id="b570f-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="b570f-108">![Прямоугольники с разных RadiusX&#47;RadiusY параметры](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="b570f-108">![Rectangles with different RadiusX&#47;RadiusY settings](./media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="b570f-109">Прямоугольники с закругленными углами</span><span class="sxs-lookup"><span data-stu-id="b570f-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b570f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="b570f-110">See also</span></span>

- [<span data-ttu-id="b570f-111">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="b570f-111">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="b570f-112">Создание составной фигуры</span><span class="sxs-lookup"><span data-stu-id="b570f-112">Create a Composite Shape</span></span>](how-to-create-a-composite-shape.md)
- [<span data-ttu-id="b570f-113">Создание фигуры с помощью объекта PathGeometry</span><span class="sxs-lookup"><span data-stu-id="b570f-113">Create a Shape by Using a PathGeometry</span></span>](how-to-create-a-shape-by-using-a-pathgeometry.md)
