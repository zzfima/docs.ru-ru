---
title: Как выполнить Создание отражения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating reflections [WPF]
- brushes [WPF], creating reflections
- reflections [WPF], creating
ms.assetid: 4f017e16-ab80-43c7-98df-03b6bddbb203
ms.openlocfilehash: 0fae98966481003c7906f5cbb34afaea666d583d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559038"
---
# <a name="how-to-create-a-reflection"></a>Как выполнить Создание отражения
В этом примере показано, как использовать <xref:System.Windows.Media.VisualBrush> для создания отражения. Так как <xref:System.Windows.Media.VisualBrush> можно отображать существующие визуальные, эту возможность можно использовать для создания интересных визуальных эффектов, например отражения и увеличения.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.VisualBrush> для создания отражения <xref:System.Windows.Controls.Border> , содержащего несколько элементов. На следующей иллюстрации показан результат выполнения этого примера.  
  
 ![Объект отражены визуальный объект](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-visualbrush-reflection-small.jpg "graphicsmm_visualbrush_reflection_small")  
Отраженный объект Visual  
  
 [!code-csharp[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/ReflectionExample.cs#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-vb[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/reflectionexample.vb#graphicsmmvisualbrushreflectionexamplewholepage)]
 [!code-xaml[visualbrush_markup_snip#GraphicsMMVisualBrushReflectionExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/ReflectionExample.xaml#graphicsmmvisualbrushreflectionexamplewholepage)]  
  
 Полный образец, который включает примеры, демонстрирующие увеличение частей экрана и создание отражений, см. в разделе [пример VisualBrush](https://go.microsoft.com/fwlink/?LinkID=160049).  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Media.VisualBrush>
- [Заполнение с использованием изображений, рисунков и визуальных элементов](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
