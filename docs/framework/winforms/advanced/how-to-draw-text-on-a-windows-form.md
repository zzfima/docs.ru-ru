---
title: Как выполнить Рисование текста в форме Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], drawing text
- text [Windows Forms], drawing
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
ms.openlocfilehash: 07aef6619468b957d6f2aa46482be3de0411cd40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54512398"
---
# <a name="how-to-draw-text-on-a-windows-form"></a>Как выполнить Рисование текста в форме Windows
В следующем примере кода показано, как использовать <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> для рисования текста в форме. Кроме того, можно использовать <xref:System.Windows.Forms.TextRenderer> для рисования текста в форме. Дополнительные сведения см. в разделе [Как Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).  
  
## <a name="example"></a>Пример  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Нельзя вызывать <xref:System.Drawing.Graphics.DrawString%2A> метод в <xref:System.Windows.Forms.Form.Load> обработчик событий. Если скрыта другой формой или изменении размера формы, рисунок перерисовываться не будет. Чтобы сделать автоматическую перерисовку, нужно переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 При следующих условиях возможно возникновение исключения:  
  
-   Шрифт Arial не установлен.  
  
## <a name="see-also"></a>См. также
- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Приступая к программированию графики](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Практическое руководство. Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
