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
ms.openlocfilehash: c753be6a200f166e59e1330c7dbcf1fadc7588a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a><span data-ttu-id="88179-102">Практическое руководство. Многострочный вывод текста в прямоугольнике</span><span class="sxs-lookup"><span data-stu-id="88179-102">How to: Draw Wrapped Text in a Rectangle</span></span>
<span data-ttu-id="88179-103">Перенос текста в прямоугольнике можно нарисовать с помощью <xref:System.Drawing.Graphics.DrawString%2A> перегруженным методом <xref:System.Drawing.Graphics> класс, который принимает <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF> параметра.</span><span class="sxs-lookup"><span data-stu-id="88179-103">You can draw wrapped text in a rectangle by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF> parameter.</span></span> <span data-ttu-id="88179-104">Вы также будете использовать <xref:System.Drawing.Brush> и <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="88179-104">You will also use a <xref:System.Drawing.Brush> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="88179-105">Также можно рисовать перенос текста в прямоугольнике, используя <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженным методом <xref:System.Windows.Forms.TextRenderer> , который принимает <xref:System.Drawing.Rectangle> и <xref:System.Windows.Forms.TextFormatFlags> параметр.</span><span class="sxs-lookup"><span data-stu-id="88179-105">You can also draw wrapped text in a rectangle by using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Rectangle> and a <xref:System.Windows.Forms.TextFormatFlags> parameter.</span></span> <span data-ttu-id="88179-106">Вы также будете использовать <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="88179-106">You will also use a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="88179-107">На следующем рисунке показан текст, выведенный в прямоугольнике с помощью <xref:System.Drawing.Graphics.DrawString%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="88179-107">The following illustration shows the output of text drawn in the rectangle when you use the <xref:System.Drawing.Graphics.DrawString%2A> method.</span></span>  
  
 <span data-ttu-id="88179-108">![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span><span class="sxs-lookup"><span data-stu-id="88179-108">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")</span></span>  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="88179-109">Чтобы нарисовать вывод текста в прямоугольнике с помощью GDI +</span><span class="sxs-lookup"><span data-stu-id="88179-109">To draw wrapped text in a rectangle with GDI+</span></span>  
  
1.  <span data-ttu-id="88179-110">Используйте <xref:System.Drawing.Graphics.DrawString%2A> перегруженный метод, передав текст, который будет <xref:System.Drawing.Rectangle> или <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> и <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="88179-110">Use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle> or <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a><span data-ttu-id="88179-111">Чтобы нарисовать вывод текста в прямоугольнике с помощью GDI</span><span class="sxs-lookup"><span data-stu-id="88179-111">To draw wrapped text in a rectangle with GDI</span></span>  
  
1.  <span data-ttu-id="88179-112">Используйте <xref:System.Windows.Forms.TextFormatFlags> значение перечисления для задания текста, которые должны быть помещены с <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженный метод, передав текст, который будет <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> и <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="88179-112">Use the <xref:System.Windows.Forms.TextFormatFlags> enumeration value to specify the text should be wrapped with the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method, passing the text you want, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="88179-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="88179-113">Compiling the Code</span></span>  
 <span data-ttu-id="88179-114">Предыдущих примеров требуются:</span><span class="sxs-lookup"><span data-stu-id="88179-114">The previous examples require:</span></span>  
  
-   <span data-ttu-id="88179-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="88179-115"><xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88179-116">См. также</span><span class="sxs-lookup"><span data-stu-id="88179-116">See Also</span></span>  
 [<span data-ttu-id="88179-117">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="88179-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="88179-118">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="88179-118">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="88179-119">Практическое руководство. Разработка шрифтов и их семейств</span><span class="sxs-lookup"><span data-stu-id="88179-119">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="88179-120">Практическое руководство. Рисование текста в указанной позиции</span><span class="sxs-lookup"><span data-stu-id="88179-120">How to: Draw Text at a Specified Location</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)
