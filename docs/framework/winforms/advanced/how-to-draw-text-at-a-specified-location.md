---
title: Как выполнить Рисование текста в указанном расположении
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: e5a1791e21981f60e008b97a51d10f88b827de8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660376"
---
# <a name="how-to-draw-text-at-a-specified-location"></a>Как выполнить Рисование текста в указанном расположении
При выполнении пользовательского рисования можно рисовать текст в одной строке по горизонтали, начиная с указанной точки. Таким образом можно рисовать текст с помощью <xref:System.Drawing.Graphics.DrawString%2A> перегруженным методом <xref:System.Drawing.Graphics> класс, принимающий <xref:System.Drawing.Point> или <xref:System.Drawing.PointF> параметра. <xref:System.Drawing.Graphics.DrawString%2A> Также требует <xref:System.Drawing.Brush> и <xref:System.Drawing.Font>  
  
 Можно также использовать <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженным методом <xref:System.Windows.Forms.TextRenderer> , принимающий <xref:System.Drawing.Point>. <xref:System.Windows.Forms.TextRenderer.DrawText%2A> также требуется <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.  
  
 На следующем рисунке показан вывод текста, рисуемого в заданной точке при использовании <xref:System.Drawing.Graphics.DrawString%2A> перегруженный метод.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Рисование линии текста с помощью GDI +  
  
1.  Используйте <xref:System.Drawing.Graphics.DrawString%2A> , передавая текст, <xref:System.Drawing.Point> или <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, и <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Рисование линии текста с использованием GDI  
  
1.  Используйте <xref:System.Windows.Forms.TextRenderer.DrawText%2A> , передавая текст, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, и <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для работы предыдущих примеров:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
- [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [Практическое руководство. Шрифты и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
- [Практическое руководство. Многострочный вывод текста в прямоугольнике](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
