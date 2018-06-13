---
title: Практическое руководство. Выравнивание рисуемого текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 96e14ef510a08ed0c387733e37b6acae6cbd31cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522761"
---
# <a name="how-to-align-drawn-text"></a>Практическое руководство. Выравнивание рисуемого текста
При выполнении пользовательской отрисовки, часто требуется формируемого выравнивание текста по центру формы или элемента управления. Выровнять текст, отображаемый с <xref:System.Drawing.Graphics.DrawString%2A> или <xref:System.Windows.Forms.TextRenderer.DrawText%2A> методы создания нужный объект форматирования и установив соответствующие параметры форматирования.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>Чтобы нарисовать по центру текста с использованием GDI + (DrawString)  
  
1.  Используйте <xref:System.Drawing.StringFormat> с соответствующими <xref:System.Drawing.Graphics.DrawString%2A> метод, чтобы указать текст, выровненный по центру.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>Чтобы нарисовать по центру текста с использованием GDI (DrawText)  
  
1.  Используйте <xref:System.Windows.Forms.TextFormatFlags> перечисления для упаковки, а также по вертикали и горизонтали Центрирование текста с помощью соответствующих <xref:System.Windows.Forms.TextRenderer.DrawText%2A> метод.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms, и требуют <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Практическое руководство. Разработка шрифтов и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
