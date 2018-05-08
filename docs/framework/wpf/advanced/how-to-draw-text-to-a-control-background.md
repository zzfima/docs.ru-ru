---
title: Практическое руководство. Рисование текста на фоне элемента управления
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], drawing text to backgrounds
- text [WPF], drawing to control backgrounds
- drawing [WPF], text to control backgrounds
- backgrounds [WPF], drawing text to
- typography [WPF], drawing text to control backgrounds
ms.assetid: 686d8fba-f61c-4974-a871-c635d67a7f69
ms.openlocfilehash: f79ec4f2c394fdc9462f4fd00942673b4536d713
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-text-to-a-control39s-background"></a>Практическое руководство. Рисование текста на фоне элемента управления
Можно нарисовать текст непосредственно на фоне элемента управления путем преобразования текстовую строку для <xref:System.Windows.Media.FormattedText> объекта, а затем рисование объекта элемента управления <xref:System.Windows.Media.DrawingContext>. Эту технологию можно также использовать для рисования фона для объектов, производных от <xref:System.Windows.Controls.Panel>, такие как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.StackPanel>.  
  
 ![Элементы управления, отображающие текст в качестве фона](../../../../docs/framework/wpf/advanced/media/drawtext2background01.png "DrawText2Background01")  
Пример элементов управления с фоном из пользовательского текста  
  
## <a name="example"></a>Пример  
 Чтобы нарисовать фон элемента управления, создайте новый <xref:System.Windows.Media.DrawingBrush> и рисовать текст, преобразованный в объект <xref:System.Windows.Media.DrawingContext>. После этого назначьте новый <xref:System.Windows.Media.DrawingBrush> свойству фона элемента управления.  
  
 В следующем примере кода показано, как создать <xref:System.Windows.Media.FormattedText> и рисовать фон <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Button> объекта.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.FormattedText>  
 [Рисование форматированного текста](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)
