---
title: Практическое руководство. Сглаживание текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182476"
---
# <a name="how-to-use-antialiasing-with-text"></a>Практическое руководство. Сглаживание текста
*Антиалиазирование* относится к сглаживанию зубчатых краев нарисованной графики и текста, чтобы улучшить их внешний вид или читаемость. С помощью управляемых классов GDI можно визуализировать высококачественный антиалиазный текст, а также текст более низкого качества. Как правило, более высокое качество визуализации занимает больше времени обработки, чем более низкое качество визуализации. Чтобы установить уровень качества <xref:System.Drawing.Graphics.TextRenderingHint%2A> текста, <xref:System.Drawing.Graphics> установите свойство <xref:System.Drawing.Text.TextRenderingHint> одного из элементов перечисления  
  
## <a name="example"></a>Пример  
 Следующий пример кода рисует текст с двумя различными настройками качества.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 На следующей иллюстрации показан выход кода примера:  
  
 ![Скриншот, который показывает текст с двумя различными настройками качества.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для использования с <xref:System.Windows.Forms.PaintEventArgs> `e`Windows Forms, и <xref:System.Windows.Forms.PaintEventHandler>он требует, который является параметром .  
  
## <a name="see-also"></a>См. также раздел

- [Шрифты и текст](using-fonts-and-text.md)
