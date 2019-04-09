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
ms.openlocfilehash: 5214ef2c69349514f05ba68cc023a7622e119e3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210455"
---
# <a name="how-to-align-drawn-text"></a><span data-ttu-id="95191-102">Практическое руководство. Выравнивание рисуемого текста</span><span class="sxs-lookup"><span data-stu-id="95191-102">How to: Align Drawn Text</span></span>
<span data-ttu-id="95191-103">При выполнении пользовательского рисования, часто можно формируемого выравнивание текста по центру формы или элемента управления.</span><span class="sxs-lookup"><span data-stu-id="95191-103">When you perform custom drawing, you may often want to center drawn text on a form or control.</span></span> <span data-ttu-id="95191-104">Выровнять текст, отображаемый с <xref:System.Drawing.Graphics.DrawString%2A> или <xref:System.Windows.Forms.TextRenderer.DrawText%2A> методы создания нужный объект форматирования и установив соответствующие параметры форматирования.</span><span class="sxs-lookup"><span data-stu-id="95191-104">You can easily align text drawn with the <xref:System.Drawing.Graphics.DrawString%2A> or <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods by creating the correct formatting object and setting the appropriate format flags.</span></span>  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a><span data-ttu-id="95191-105">Для рисования по центру текста с помощью GDI + (DrawString)</span><span class="sxs-lookup"><span data-stu-id="95191-105">To draw centered text with GDI+ (DrawString)</span></span>  
  
1.  <span data-ttu-id="95191-106">Используйте <xref:System.Drawing.StringFormat> с соответствующим <xref:System.Drawing.Graphics.DrawString%2A> метод, чтобы задать текст, выровненный по центру.</span><span class="sxs-lookup"><span data-stu-id="95191-106">Use a <xref:System.Drawing.StringFormat> with the appropriate <xref:System.Drawing.Graphics.DrawString%2A> method to specify centered text.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a><span data-ttu-id="95191-107">Для рисования по центру текста с использованием GDI (DrawText)</span><span class="sxs-lookup"><span data-stu-id="95191-107">To draw centered text with GDI (DrawText)</span></span>  
  
1.  <span data-ttu-id="95191-108">Используйте <xref:System.Windows.Forms.TextFormatFlags> перечисления для упаковки, а также по вертикали и горизонтали Центрирование текста с соответствующим <xref:System.Windows.Forms.TextRenderer.DrawText%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="95191-108">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration for wrapping as well as vertically and horizontally centering text with the appropriate <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="95191-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="95191-109">Compiling the Code</span></span>  
 <span data-ttu-id="95191-110">Предыдущий пример кода предназначен для работы с Windows Forms, и они требуют <xref:System.Windows.Forms.PaintEventArgs>`e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="95191-110">The preceding code examples are designed for use with Windows Forms, and they require <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95191-111">См. также</span><span class="sxs-lookup"><span data-stu-id="95191-111">See also</span></span>

- [<span data-ttu-id="95191-112">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="95191-112">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="95191-113">Шрифты и текст</span><span class="sxs-lookup"><span data-stu-id="95191-113">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="95191-114">Практическое руководство. Разработка шрифтов и их семейств</span><span class="sxs-lookup"><span data-stu-id="95191-114">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
