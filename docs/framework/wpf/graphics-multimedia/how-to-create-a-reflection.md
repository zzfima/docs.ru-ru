---
title: Практическое руководство. Создание отражения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: c791dbbe02faaba790c650d482db092702730fa6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-reflection"></a>Практическое руководство. Создание отражения
В этом примере показано, как использовать <xref:System.Windows.Media.VisualBrush> будет создано отражение. Поскольку <xref:System.Windows.Media.VisualBrush> может отображать существующие визуальные, эту возможность можно использовать для создания интересных визуальных эффектов, например отражения и увеличения.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.VisualBrush> создание отражения <xref:System.Windows.Controls.Border> , содержащего несколько элементов. На следующей иллюстрации показан результат выполнения этого примера.  
  
 ![Объект отражены визуального объекта](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Отраженный объект Visual  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Полный пример включает примеры, демонстрирующие создание отражения и увеличения части экрана, в разделе [VisualBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160049).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.VisualBrush>  
 [Заливка с помощью объектов Image, Drawing и Visual](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
