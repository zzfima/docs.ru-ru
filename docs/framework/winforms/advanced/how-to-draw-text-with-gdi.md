---
title: Практическое руководство. Рисование текста с использованием GDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing with TextRenderer
- drawing [Windows Forms], text
- Windows Forms, drawing text with GDI
ms.assetid: 2a19fe5d-2ace-451c-94db-01cb1118ef7b
ms.openlocfilehash: 3ed2b5c94e4a38a5873a34e61287c4038cab5cbb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956546"
---
# <a name="how-to-draw-text-with-gdi"></a>Практическое руководство. Рисование текста с использованием GDI
С помощью <xref:System.Windows.Forms.TextRenderer> метода в классе можно получить доступ к функциональным возможностям GDI для рисования текста в форме или элементе управления. <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Визуализация текста GDI обычно обеспечивает лучшую производительность и более точное измерение текста, чем GDI+.  
  
> [!NOTE]
> <xref:System.Windows.Forms.TextRenderer.DrawText%2A> Методы<xref:System.Windows.Forms.TextRenderer> класса не поддерживаются для печати. При печати всегда используйте <xref:System.Drawing.Graphics.DrawString%2A> методы <xref:System.Drawing.Graphics> класса.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как нарисовать текст на нескольких строках в прямоугольнике <xref:System.Windows.Forms.TextRenderer.DrawText%2A> с помощью метода.  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 Для отрисовки текста с <xref:System.Windows.Forms.TextRenderer> помощью класса <xref:System.Drawing.IDeviceContext>требуется, <xref:System.Drawing.Font>например <xref:System.Drawing.Graphics> , и, расположение для рисования текста, а также цвет, в котором он должен быть нарисован. При необходимости можно указать форматирование текста с помощью <xref:System.Windows.Forms.TextFormatFlags> перечисления.  
  
 Дополнительные сведения о получении <xref:System.Drawing.Graphics>см. в разделе как [ Создание графических объектов для рисования](how-to-create-graphics-objects-for-drawing.md). Дополнительные сведения о создании <xref:System.Drawing.Font>см. в разделе как [ Создание семейств шрифтов и шрифтов](how-to-construct-font-families-and-fonts.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Приведенный выше пример кода предназначен для использования с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e`, <xref:System.Windows.Forms.PaintEventHandler>который является параметром.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.TextRenderer>
- <xref:System.Drawing.Font>
- <xref:System.Drawing.Color>
- [Работами со шрифтами и текстом](using-fonts-and-text.md)
