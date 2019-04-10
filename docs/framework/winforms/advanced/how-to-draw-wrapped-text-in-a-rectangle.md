---
title: Практическое руководство. Многострочный вывод текста в прямоугольнике
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 8e5c7cab1f977bef0570b2e540d7bf3a630aceb0
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301932"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="9c317-102">Практическое руководство. Многострочный вывод текста в прямоугольнике</span><span class="sxs-lookup"><span data-stu-id="9c317-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="9c317-103">Можно рисовать перенос текста в прямоугольнике, используя <xref:System.Drawing.Graphics.DrawString%2A> перегруженным методом <xref:System.Drawing.Graphics> класс, принимающий <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF> параметра.</span><span class="sxs-lookup"><span data-stu-id="9c317-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="9c317-104">Вы также будете использовать <xref:System.Drawing.Brush> и <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="9c317-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="9c317-105">Также можно рисовать перенос текста в прямоугольнике, используя <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженным методом <xref:System.Windows.Forms.TextRenderer> , принимающий <xref:System.Drawing.Rectangle> и <xref:System.Windows.Forms.TextFormatFlags> параметр.</span><span class="sxs-lookup"><span data-stu-id="9c317-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="9c317-106">Вы также будете использовать <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="9c317-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="9c317-107">На следующем рисунке показан вывод текста, рисуемого в прямоугольнике, при использовании <xref:System.Drawing.Graphics.DrawString%2A> метод:</span><span class="sxs-lookup"><span data-stu-id="9c317-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method:</span></span>
  
 ![Снимок экрана, показывающий выходные данные при использовании метода DrawString.](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="9c317-109">Для рисования вывод текста в прямоугольнике с помощью GDI +</span><span class="sxs-lookup"><span data-stu-id="9c317-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1. <span data-ttu-id="9c317-110">Используйте <xref:System.Drawing.Graphics.DrawString%2A> перегруженный метод, передав текст, <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> и <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="9c317-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="9c317-111">Для рисования вывод текста в прямоугольнике с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="9c317-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1. <span data-ttu-id="9c317-112">Используйте <xref:System.Windows.Forms.TextFormatFlags> значение перечисления, чтобы указать текст должен быть заключен в <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженный метод, передав текст, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> и <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="9c317-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9c317-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9c317-113">Compiling the Code</span></span>  
 <span data-ttu-id="9c317-114">Для работы предыдущих примеров:</span><span class="sxs-lookup"><span data-stu-id="9c317-114">The previous examples require:</span></span>  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`<span data-ttu-id="9c317-115">, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="9c317-115">, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c317-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9c317-116">See also</span></span>

- [<span data-ttu-id="9c317-117">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="9c317-117">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="9c317-118">Шрифты и текст</span><span class="sxs-lookup"><span data-stu-id="9c317-118">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="9c317-119">Практическое руководство. Разработка шрифтов и их семейств</span><span class="sxs-lookup"><span data-stu-id="9c317-119">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="9c317-120">Практическое руководство. Рисование текста в указанной позиции</span><span class="sxs-lookup"><span data-stu-id="9c317-120">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)
