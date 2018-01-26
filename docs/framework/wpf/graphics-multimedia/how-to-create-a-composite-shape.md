---
title: "Практическое руководство. Создание составной фигуры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ecb4ecdc5c83cbb6f2b4faee9cb3654939bd346
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-composite-shape"></a>Практическое руководство. Создание составной фигуры
В этом примере демонстрируется создание составных фигур с помощью <xref:System.Windows.Media.Geometry> объектов и отобразить их с помощью <xref:System.Windows.Shapes.Path> элемента. В следующем примере <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>и <xref:System.Windows.Media.RectangleGeometry> используются с <xref:System.Windows.Media.GeometryGroup> для создания составного фигуры. Затем вычерчиваются с помощью <xref:System.Windows.Shapes.Path> элемента.  
  
## <a name="example"></a>Пример  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 На следующем рисунке показана фигура, созданная в предыдущем примере.  
  
 ![Составной геометрический объект создан с использованием GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Составная геометрическая фигура  
  
 Более сложные фигуры, таких как многоугольники и фигуры с фрагментами кривых, могут быть созданы с помощью <xref:System.Windows.Media.PathGeometry>. Пример, показывающий, как создать форму с помощью <xref:System.Windows.Media.PathGeometry>, в разделе [создать фигуру с помощью объект PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  Несмотря на то, что этот пример отображает фигуру на экран с помощью <xref:System.Windows.Shapes.Path> элемент, <xref:System.Windows.Media.Geometry> объектов может также использоваться для описания содержимого <xref:System.Windows.Media.GeometryDrawing> или <xref:System.Windows.Media.DrawingContext>. Они также могут использоваться для обрезки и проверки нажатия.  
  
 Этот пример является частью большего примера; полный пример см. в разделе [Пример геометрических объектов](http://go.microsoft.com/fwlink/?LinkID=159989).
