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
ms.openlocfilehash: 2adb33e3d05e38ee71be8a12cdc2e20dc8c55c72
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338134"
---
# <a name="how-to-use-antialiasing-with-text"></a>Практическое руководство. Сглаживание текста
*Сглаживание* ссылается на сглаживания неровными краями графических элементов и текста для улучшения их внешнего вида и удобства чтения. Управляемые [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] классов, можно вывести высококачественный сглаженный текст, а также текст низкого качества. Как правило более качественная визуализация занимает больше времени обработки, чем менее качественная. Чтобы установить уровень качества текста, задайте <xref:System.Drawing.Graphics.TextRenderingHint%2A> свойство <xref:System.Drawing.Graphics> к одному из элементов <xref:System.Drawing.Text.TextRenderingHint> перечисления  
  
## <a name="example"></a>Пример  
 В следующем примере кода выводит текст с двумя различными уровнями качества.  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 Ниже показан результат выполнения примера кода:  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущий пример кода предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
