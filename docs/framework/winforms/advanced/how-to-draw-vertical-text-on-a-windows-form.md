---
title: Практическое руководство. Нарисовать вертикальный текст в форме Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- StringFormat.FormatFlags
- Graphics.DrawString
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- strings [Windows Forms], drawing vertical
- text [Windows Forms], drawing
- text [Windows Forms], vertical text
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
ms.openlocfilehash: c605e7443a9d496901f55171228ad9a485dbff71
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724504"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a>Практическое руководство. Нарисовать вертикальный текст в форме Windows
В следующем примере кода показано, как нарисовать вертикальный текст в форме с помощью <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics>.  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Этот метод нельзя вызывать <xref:System.Windows.Forms.Form.Load> обработчик событий. Если скрыта другой формой или изменении размера формы, рисунок перерисовываться не будет. Чтобы сделать автоматическую перерисовку, нужно переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Шрифт Arial не установлен.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Приступая к программированию графики](getting-started-with-graphics-programming.md)
- [Работами со шрифтами и текстом](using-fonts-and-text.md)
