---
title: Как создать фигуру с помощью StreamGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], shapes
- shapes [WPF], creating with StreamGeometry class
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
ms.openlocfilehash: 54819f62b262227017e12b2066a0747107b68900
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560374"
---
# <a name="how-to-create-a-shape-using-a-streamgeometry"></a>Как создать фигуру с помощью StreamGeometry
<xref:System.Windows.Media.StreamGeometry> Упрощенная альтернатива <xref:System.Windows.Media.PathGeometry> для создания геометрических фигур. Используйте <xref:System.Windows.Media.StreamGeometry> для описания сложной геометрии, но не требуется для поддержки привязки данных, анимацию или изменения. Например, из-за его эффективности <xref:System.Windows.Media.StreamGeometry> класса лучше всего подойдет для описания графических элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере используется синтаксис атрибутов для создания треугольного <xref:System.Windows.Media.StreamGeometry> в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xaml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Дополнительные сведения о <xref:System.Windows.Media.StreamGeometry> синтаксиса см. в разделе [синтаксис разметки пути](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md) страницы.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.StreamGeometry> для определения треугольника в коде. Во-первых, в примере создается <xref:System.Windows.Media.StreamGeometry>, затем происходит получение <xref:System.Windows.Media.StreamGeometryContext> и использует его для описания треугольника.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## <a name="example"></a>Пример  
 В следующем примере создается метод, который использует <xref:System.Windows.Media.StreamGeometry> и <xref:System.Windows.Media.StreamGeometryContext> для определения геометрической фигуры на основе указанных параметров.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.PathGeometry>  
 <xref:System.Windows.Media.StreamGeometry>  
 <xref:System.Windows.Media.StreamGeometryContext>  
 [Создание фигуры с помощью объекта PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)  
 [Общие сведения о классе Geometry](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)
