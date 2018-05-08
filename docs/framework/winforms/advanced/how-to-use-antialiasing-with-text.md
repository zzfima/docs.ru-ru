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
ms.openlocfilehash: 842c1fb0b73533fd2e87474b9e8cfa282eba2a70
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-antialiasing-with-text"></a>Практическое руководство. Сглаживание текста
*Сглаживание* ссылается на сглаживания неровными краями графических элементов и текста для улучшения их внешнего вида и удобства чтения. Управляемые [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] классов, можно вывести высококачественный сглаженный текст, а также текст низкого качества. Как правило более качественная визуализация занимает больше времени обработки, чем менее качественная. Чтобы установить уровень качества текста, задайте <xref:System.Drawing.Graphics.TextRenderingHint%2A> свойство <xref:System.Drawing.Graphics> к одному из элементов <xref:System.Drawing.Text.TextRenderingHint> перечисления  
  
## <a name="example"></a>Пример  
 В следующем примере кода выводит текст с двумя различными уровнями качества.  
  
 Ниже показан результат выполнения этого примера кода.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
