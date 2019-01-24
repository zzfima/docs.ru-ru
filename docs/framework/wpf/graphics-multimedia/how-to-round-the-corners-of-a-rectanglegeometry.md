---
title: Как выполнить Скругление углов объекта RectangleGeometry
ms.date: 03/30/2017
helpviewer_keywords:
- corners [WPF], rounding
- RectangleGeometry class [WPF], rounding corners
- graphics [WPF], rounding corners of RectangleGeometry objects [WPF]
- rounding corners of RectangleGeometry objects [WPF]
ms.assetid: 926644bc-1357-4c0b-ac81-694bd090ae87
ms.openlocfilehash: 1a3ea08e4f54af117474cee23e6ac1041a1ed72b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648379"
---
# <a name="how-to-round-the-corners-of-a-rectanglegeometry"></a>Как выполнить Скругление углов объекта RectangleGeometry
Для скругления углов <xref:System.Windows.Media.RectangleGeometry>, задайте его <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> свойства в значение больше нуля. Чем больше значения, тем больше радиус скругления углов прямоугольника.  
  
## <a name="example"></a>Пример  
 В следующем примере показано несколько <xref:System.Windows.Media.RectangleGeometry> объектов с разными <xref:System.Windows.Media.RectangleGeometry.RadiusX%2A> и <xref:System.Windows.Media.RectangleGeometry.RadiusY%2A> параметры. <xref:System.Windows.Media.RectangleGeometry> Объекты отображаются с помощью <xref:System.Windows.Shapes.Path> элементов.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMRoundedRectangleGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/RectangleGeometryRoundedCornerExample.xaml#graphicsmmroundedrectanglegeometryexamplewholepage)]  
  
 ![Прямоугольники с разных RadiusX&#47;RadiusY параметры](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-rounded.png "graphicsmm_rounded")  
Прямоугольники с закругленными углами  
  
## <a name="see-also"></a>См. также
- [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
- [Создание составной фигуры](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-shape.md)
- [Создание фигуры с помощью объекта PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)
