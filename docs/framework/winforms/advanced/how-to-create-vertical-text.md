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
ms.openlocfilehash: 7d66bf147a220bdcdfd32a703d3407817a184a54
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521476"
---
# <a name="how-to-create-vertical-text"></a>Практическое руководство. Вывод текста по вертикали
Можно использовать <xref:System.Drawing.StringFormat> объекта, чтобы указать, что текст должен выводиться по вертикали, а не по горизонтали.  
  
## <a name="example"></a>Пример  
 В следующем примере присваивается значение <xref:System.Drawing.StringFormatFlags.DirectionVertical> для <xref:System.Drawing.StringFormat.FormatFlags%2A> свойство <xref:System.Drawing.StringFormat> объекта. Что <xref:System.Drawing.StringFormat> объект передается <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класса. Значение <xref:System.Drawing.StringFormatFlags.DirectionVertical> является членом <xref:System.Drawing.StringFormatFlags> перечисления.  
  
 На следующем рисунке вертикальный текст.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Предыдущий пример предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e` , который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
