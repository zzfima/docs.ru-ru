---
title: Практическое руководство. Создание GeometryDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- shapes [WPF], renderable
- renderable shapes [WPF]
- graphics [WPF], GeometryDrawing class
- classes [WPF], GeometryDrawing
ms.assetid: 11d3c096-91ba-4d41-9bba-aeac0db70f97
ms.openlocfilehash: 6eb604a8446000ef308c2b5a99480fb6a476c949
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373820"
---
# <a name="how-to-create-a-geometrydrawing"></a>Практическое руководство. Создание GeometryDrawing
В этом примере показано, как создать и отобразить <xref:System.Windows.Media.GeometryDrawing>. Объект <xref:System.Windows.Media.GeometryDrawing> позволяет создавать фигура с заливкой и структуры, связав <xref:System.Windows.Media.Pen> и <xref:System.Windows.Media.Brush> с <xref:System.Windows.Media.Geometry>. <xref:System.Windows.Media.GeometryDrawing.Geometry%2A> Описывает структуру фигуры <xref:System.Windows.Media.GeometryDrawing.Brush%2A> описывает заливку фигуры и <xref:System.Windows.Media.GeometryDrawing.Pen%2A> описывает контура фигуры.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.GeometryDrawing> для отображения фигуры. Фигура описывается <xref:System.Windows.Media.GeometryGroup> и два <xref:System.Windows.Media.EllipseGeometry> объектов. Фигуры закрашивается кистью <xref:System.Windows.Media.LinearGradientBrush> и ее контур рисуется пером <xref:System.Windows.Media.Brushes.Black%2A> <xref:System.Windows.Media.Pen>. <xref:System.Windows.Media.GeometryDrawing> Отображается с использованием <xref:System.Windows.Media.ImageDrawing> и <xref:System.Windows.Controls.Image> элемент.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/GeometryDrawingExample.cs#geometrydrawingexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#GeometryDrawingExampleWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/GeometryDrawingExample.xaml#geometrydrawingexamplewholepage)]  
  
 На следующем рисунке показан итоговый <xref:System.Windows.Media.GeometryDrawing>.  
  
 ![GeometryDrawing двух эллипсов](./media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
  
 Для создания более сложных рисунков, можно объединить несколько графических объектов в один составной рисунок с помощью <xref:System.Windows.Media.DrawingGroup>.  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.DrawingGroup>
- [Обзор объектов Drawing](drawing-objects-overview.md)
- [Общие сведения о классе Geometry](geometry-overview.md)
- [Создание составного рисунка](how-to-create-a-composite-drawing.md)
