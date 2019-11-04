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
ms.openlocfilehash: 14300f763b67c6ac67ee408de2009c328d499c13
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424371"
---
# <a name="how-to-draw-text-to-a-controls-background"></a>Практическое руководство. Рисование текста на фоне элемента управления
Можно нарисовать текст непосредственно на фоне элемента управления, преобразовав текстовую строку в <xref:System.Windows.Media.FormattedText> объект, а затем вырисуя объект в <xref:System.Windows.Media.DrawingContext>элемента управления. Эту методику также можно использовать для рисования в фоновом режиме объектов, производных от <xref:System.Windows.Controls.Panel>, таких как <xref:System.Windows.Controls.Canvas> и <xref:System.Windows.Controls.StackPanel>.  
  
 ![Снимок экрана элементов управления, отображающих текст как фон.](./media/how-to-draw-text-to-a-control-background/draw-text-background.png "DrawText2Background01")  
Пример элементов управления с фоном из пользовательского текста  
  
## <a name="example"></a>Пример  
 Чтобы нарисовать фон элемента управления, создайте новый объект <xref:System.Windows.Media.DrawingBrush> и нарисуйте преобразованный текст в <xref:System.Windows.Media.DrawingContext>объекта. Затем назначьте новый <xref:System.Windows.Media.DrawingBrush> свойству Background элемента управления.  
  
 В следующем примере кода показано, как создать объект <xref:System.Windows.Media.FormattedText> и нарисовать фон <xref:System.Windows.Controls.Label> и <xref:System.Windows.Controls.Button> объекта.  
  
 [!code-csharp[DrawTextToControlBackground#DrawTextToControlBackground1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawTextToControlBackground/CSHARP/Window1.xaml.cs#drawtexttocontrolbackground1)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.FormattedText>
- [Рисование форматированного текста](drawing-formatted-text.md)
