---
title: Практическое руководство. Скругление углов объекта RectangleGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: e4f1d37e2c0f26967affff14ed6475fc8c0cb28c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561645"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a><span data-ttu-id="cc634-102">Практическое руководство. Скругление углов объекта RectangleGeometry</span><span class="sxs-lookup"><span data-stu-id="cc634-102">How to: Round the Corners of a RectangleGeometry</span></span>
<span data-ttu-id="cc634-103">Для скругления углов <xref:System.Windows.Media.RectangleGeometry>, задайте его <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> свойства в значение больше нуля.</span><span class="sxs-lookup"><span data-stu-id="cc634-103">To round the corners of a <xref:System.Windows.Media.RectangleGeometry>, set its <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> properties to a value greater than zero.</span></span> <span data-ttu-id="cc634-104">Чем больше значения, тем больше радиус скругления углов прямоугольника.</span><span class="sxs-lookup"><span data-stu-id="cc634-104">The larger the values, the rounder the rectangle's corners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc634-105">Пример</span><span class="sxs-lookup"><span data-stu-id="cc634-105">Example</span></span>  
 <span data-ttu-id="cc634-106">В следующем примере показано несколько <xref:System.Windows.Media.RectangleGeometry> объектов с различными <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> параметры.</span><span class="sxs-lookup"><span data-stu-id="cc634-106">The following example shows several <xref:System.Windows.Media.RectangleGeometry> objects with different <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> and <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> settings.</span></span> <span data-ttu-id="cc634-107"><xref:System.Windows.Media.RectangleGeometry> Объекты отображаются с помощью <xref:System.Windows.Shapes.Path> элементов.</span><span class="sxs-lookup"><span data-stu-id="cc634-107">The <xref:System.Windows.Media.RectangleGeometry> objects are displayed using <xref:System.Windows.Shapes.Path> elements.</span></span>  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 <span data-ttu-id="cc634-108">![Прямоугольники с параметрами разных RadiusX&#47;RadiusY параметры](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span><span class="sxs-lookup"><span data-stu-id="cc634-108">![Rectangles with different RadiusX&#47;RadiusY settings](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")</span></span>  
<span data-ttu-id="cc634-109">Прямоугольников со скругленными углами</span><span class="sxs-lookup"><span data-stu-id="cc634-109">Rectangles with Rounded Corners</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc634-110">См. также</span><span class="sxs-lookup"><span data-stu-id="cc634-110">See Also</span></span>  
 [<span data-ttu-id="cc634-111">Общие сведения о классе Geometry</span><span class="sxs-lookup"><span data-stu-id="cc634-111">Geometry Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [<span data-ttu-id="cc634-112">Создание составной фигуры</span><span class="sxs-lookup"><span data-stu-id="cc634-112">Create a Composite Shape</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)  
 [<span data-ttu-id="cc634-113">Создание фигуры с помощью объекта PathGeometry</span><span class="sxs-lookup"><span data-stu-id="cc634-113">Create a Shape by Using a PathGeometry</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
