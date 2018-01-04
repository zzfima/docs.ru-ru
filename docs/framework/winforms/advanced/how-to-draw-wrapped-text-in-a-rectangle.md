---
title: "Практическое руководство. Многострочный вывод текста в прямоугольнике"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 82e8c324cac8f9eda8f3052f77230733dd47777d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>Практическое руководство. Многострочный вывод текста в прямоугольнике
Перенос текста в прямоугольнике можно нарисовать с помощью <xref:System.Drawing.Graphics.DrawString%2A> перегруженным методом <xref:System.Drawing.Graphics> класс, который принимает <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF> параметра. Вы также будете использовать <xref:System.Drawing.Brush> и <xref:System.Drawing.Font>.  
  
 Также можно рисовать перенос текста в прямоугольнике, используя <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженным методом <xref:System.Windows.Forms.TextRenderer> , который принимает <xref:System.Drawing.Rectangle> и <xref:System.Windows.Forms.TextFormatFlags> параметр. Вы также будете использовать <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.  
  
 На следующем рисунке показан текст, выведенный в прямоугольнике с помощью <xref:System.Drawing.Graphics.DrawString%2A> метод.  
  
 ![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Чтобы нарисовать вывод текста в прямоугольнике с помощью GDI +  
  
1.  Используйте <xref:System.Drawing.Graphics.DrawString%2A> перегруженный метод, передав текст, который будет <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> и <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Чтобы нарисовать вывод текста в прямоугольнике с помощью GDI  
  
1.  Используйте <xref:System.Windows.Forms.TextFormatFlags> значение перечисления для задания текста, которые должны быть помещены с <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженный метод, передав текст, который будет <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> и <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Предыдущих примеров требуются:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>`e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Работами со шрифтами и текстом](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Практическое руководство. Разработка шрифтов и их семейств](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [Практическое руководство. Рисование текста в указанной позиции](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
