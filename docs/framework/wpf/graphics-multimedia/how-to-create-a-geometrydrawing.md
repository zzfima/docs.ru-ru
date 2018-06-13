---
title: Практическое руководство. Создание GeometryDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: 713cecd10bfa62494c50c96cb8cbece69f7e5660
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560664"
---
# <a name="how-to-create-a-geometrydrawing"></a>Практическое руководство. Создание GeometryDrawing
В этом примере показано, как создать и отобразить <xref:System.Windows.Media.GeometryDrawing>. Объект <xref:System.Windows.Media.GeometryDrawing> позволяет создавать фигура с заливкой и контуром, связав <xref:System.Windows.Media.Pen> и <xref:System.Windows.Media.Brush> с <xref:System.Windows.Media.Geometry>. <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> Описывает структуру фигуры <xref:System.Windows.Media.GeometryDrawing.Brush%2A> описывает заливку фигуры и <xref:System.Windows.Media.GeometryDrawing.Pen%2A> описывает контура фигуры.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.GeometryDrawing> для отображения фигуры. Описывается фигуры <xref:System.Windows.Media.GeometryGroup> и два <xref:System.Windows.Media.EllipseGeometry> объектов. Рисования внутренней области фигуры с <xref:System.Windows.Media.LinearGradientBrush> и его контур рисуется с <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. <xref:System.Windows.Media.GeometryDrawing> Отображается с использованием <xref:System.Windows.Media.ImageDrawing> и <xref:System.Windows.Controls.Image> элемента.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 На следующем рисунке показан итоговый <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 Для создания более сложных рисунков можно объединить несколько графических объектов в один составной рисунок с помощью <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.DrawingGroup>  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)  
 [Создание составного рисунка](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-composite-drawing.md)
