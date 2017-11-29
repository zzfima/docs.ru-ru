---
title: "Практическое руководство. Рисование изображения с помощью ImageDrawing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drawing [WPF], images
- graphics [WPF], drawing images
- images [WPF], drawing
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d975d33bb3c102e5294d78dc76d8136ab521953
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-an-image-using-imagedrawing"></a>Практическое руководство. Рисование изображения с помощью ImageDrawing
В этом примере показано, как использовать <xref:System.Windows.Media.ImageDrawing> для рисования изображения. <xref:System.Windows.Media.ImageDrawing> Позволяет отображать <xref:System.Windows.Media.ImageSource> с <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage>, или <xref:System.Windows.Media.Visual>. Чтобы нарисовать изображение, создайте <xref:System.Windows.Media.ImageDrawing> и задайте его <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> и <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> свойства. <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=nameWithType> Свойство задает изображение для рисования и <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=nameWithType> свойство указывает положение и размер каждого изображения.  
  
## <a name="example"></a>Пример  
 В следующем примере создается составной рисунок с помощью четырех <xref:System.Windows.Media.ImageDrawing> объектов. В этом примере получается следующее изображение:  
  
 ![Несколько объектов DrawingImage](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.jpg "graphicsmm_ImageDrawingExample")  
Четыре объекта ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xaml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 Пример простой способ отображения изображения без использования <xref:System.Windows.Media.ImageDrawing>, в разделе [использование элемента изображения](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Freezable.Freeze%2A>  
 <xref:System.Windows.Controls.Image>  
 [Обзор объектов Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [Общие сведения об объектах класса Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [Атрибут PresentationOptions: Freeze](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)
