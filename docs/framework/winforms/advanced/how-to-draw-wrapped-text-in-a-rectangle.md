---
title: Как выполнить Многострочный вывод текста в прямоугольнике
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 4afe3eb7c3525dac856751331117e0980063faad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602953"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>Как выполнить Многострочный вывод текста в прямоугольнике
Можно рисовать перенос текста в прямоугольнике, используя <xref:System.Drawing.Graphics.DrawString%2A> перегруженным методом <xref:System.Drawing.Graphics> класс, принимающий <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF> параметра. Вы также будете использовать <xref:System.Drawing.Brush> и <xref:System.Drawing.Font>.  
  
 Также можно рисовать перенос текста в прямоугольнике, используя <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженным методом <xref:System.Windows.Forms.TextRenderer> , принимающий <xref:System.Drawing.Rectangle> и <xref:System.Windows.Forms.TextFormatFlags> параметр. Вы также будете использовать <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.  
  
 На следующем рисунке показан вывод текста, рисуемого в прямоугольнике, при использовании <xref:System.Drawing.Graphics.DrawString%2A> метод.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Для рисования вывод текста в прямоугольнике с помощью GDI +  
  
1.  Используйте <xref:System.Drawing.Graphics.DrawString%2A> перегруженный метод, передав текст, <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> и <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Для рисования вывод текста в прямоугольнике с использованием GDI  
  
1.  Используйте <xref:System.Windows.Forms.TextFormatFlags> значение перечисления, чтобы указать текст должен быть заключен в <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженный метод, передав текст, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> и <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для работы предыдущих примеров:  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
- [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [Практическое руководство. Шрифты и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
- [Практическое руководство. Рисование текста в указанном расположении](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
