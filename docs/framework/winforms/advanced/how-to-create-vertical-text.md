---
title: Практическое руководство. Вывод текста по вертикали
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182560"
---
# <a name="how-to-create-vertical-text"></a>Практическое руководство. Вывод текста по вертикали
Объект можно <xref:System.Drawing.StringFormat> использовать для указания текста нарисованным по вертикали, а не по горизонтали.  
  
## <a name="example"></a>Пример  
 Следующий пример присваивает <xref:System.Drawing.StringFormatFlags.DirectionVertical> значение <xref:System.Drawing.StringFormat> свойству <xref:System.Drawing.StringFormat.FormatFlags%2A> объекта. Этот <xref:System.Drawing.StringFormat> объект передается <xref:System.Drawing.Graphics.DrawString%2A> методу <xref:System.Drawing.Graphics> класса. Значение <xref:System.Drawing.StringFormatFlags.DirectionVertical> является участником <xref:System.Drawing.StringFormatFlags> перечисления.  
  
 На следующей иллюстрации показан вертикальный текст:
  
 ![Графика, отображая вертикальный текст шрифта.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
- Предыдущий пример предназначен для использования с Windows <xref:System.Windows.Forms.PaintEventArgs> `e` Forms, и <xref:System.Windows.Forms.PaintEventHandler>он требует, который является параметром .  
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Рисование текста с использованием GDI](how-to-draw-text-with-gdi.md)
