---
title: Практическое руководство. Использование рисунка в качестве источника изображения
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], drawings [WPF], as image sources
- image sources [WPF], drawings
- drawings [WPF], as image sources
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
ms.openlocfilehash: 7da8a2a594b0562667aaf417d736159d98818a63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-a-drawing-as-an-image-source"></a>Практическое руководство. Использование рисунка в качестве источника изображения
В этом примере показано, как использовать <xref:System.Windows.Media.Drawing> как <xref:System.Windows.Controls.Image.Source%2A> для <xref:System.Windows.Controls.Image> элемента управления. Для отображения <xref:System.Windows.Media.Drawing> с <xref:System.Windows.Controls.Image> управления, используйте <xref:System.Windows.Media.DrawingImage> как <xref:System.Windows.Controls.Image> элемента управления <xref:System.Windows.Controls.Image.Source%2A> и задайте <xref:System.Windows.Media.DrawingImage> объекта <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=nameWithType> свойство в документ, который требуется отобразить.  
  
## <a name="example"></a>Пример  
 В следующем примере используется <xref:System.Windows.Media.DrawingImage> и <xref:System.Windows.Controls.Image> управления для отображения <xref:System.Windows.Media.GeometryDrawing>. В этом примере выводятся следующие данные:  
  
 ![GeometryDrawing двух эллипсов](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.jpg "graphicsmm_geodraw")  
Объект DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xaml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [Рисование изображения с помощью объекта ImageDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Атрибут PresentationOptions: Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
