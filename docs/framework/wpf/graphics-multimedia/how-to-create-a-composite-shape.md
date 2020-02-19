---
title: Практическое руководство. Создание составной фигуры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452101"
---
# <a name="how-to-create-a-composite-shape"></a>Практическое руководство. Создание составной фигуры
В этом примере показано, как создавать составные фигуры с помощью <xref:System.Windows.Media.Geometry>ных объектов и отображать их с помощью элемента <xref:System.Windows.Shapes.Path>. В следующем примере <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>и <xref:System.Windows.Media.RectangleGeometry> используются с <xref:System.Windows.Media.GeometryGroup> для создания составной фигуры. Затем геометрические объекты рисуются с помощью элемента <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Пример  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 На следующем рисунке показана фигура, созданная в предыдущем примере.  
  
 ![Составная геометрия, созданная с помощью GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Составной геометрический объект  
  
 Более сложные фигуры, такие как многоугольники и фигуры с изогнутыми сегментами, могут быть созданы с помощью <xref:System.Windows.Media.PathGeometry>. Пример создания фигуры с помощью <xref:System.Windows.Media.PathGeometry>см. [в разделе Создание фигуры с помощью PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  Хотя в этом примере фигура подготавливается к экрану с помощью элемента <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Media.Geometry> объекты также могут использоваться для описания содержимого <xref:System.Windows.Media.GeometryDrawing> или <xref:System.Windows.Media.DrawingContext>. Они также могут использоваться для обрезки и проверки попадания.  
  
 Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).
