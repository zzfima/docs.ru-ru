---
title: Практическое руководство. Рисование текста в указанной позиции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: e55afd0629c1b9e6d30c8b31116ec28a718fcb4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="8548f-102">Практическое руководство. Рисование текста в указанной позиции</span><span class="sxs-lookup"><span data-stu-id="8548f-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="8548f-103">При выполнении пользовательской отрисовки, можно нарисовать текст в одной горизонтальной строки, начиная с заданной точки.</span><span class="sxs-lookup"><span data-stu-id="8548f-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="8548f-104">Можно рисовать текст таким образом, используя <xref:System.Drawing.Graphics.DrawString%2A> перегруженным методом <xref:System.Drawing.Graphics> класс, который принимает <xref:System.Drawing.Point> или <xref:System.Drawing.PointF> параметра.</span><span class="sxs-lookup"><span data-stu-id="8548f-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="8548f-105"><xref:System.Drawing.Graphics.DrawString%2A> Также требует <xref:System.Drawing.Brush> и <xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="8548f-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="8548f-106">Можно также использовать <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженным методом <xref:System.Windows.Forms.TextRenderer> , который принимает <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="8548f-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="8548f-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> также требуется <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="8548f-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="8548f-108">На следующем рисунке показан текст, выведенный в заданной точке с помощью <xref:System.Drawing.Graphics.DrawString%2A> перегруженный метод.</span><span class="sxs-lookup"><span data-stu-id="8548f-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 <span data-ttu-id="8548f-109">![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span><span class="sxs-lookup"><span data-stu-id="8548f-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")</span></span>  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="8548f-110">Чтобы нарисовать линию текста с использованием GDI +</span><span class="sxs-lookup"><span data-stu-id="8548f-110">To draw a line of text with GDI+</span></span>  
  
1.  <span data-ttu-id="8548f-111">Используйте <xref:System.Drawing.Graphics.DrawString%2A> метод, передав текст, который будет <xref:System.Drawing.Point> или <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, и <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="8548f-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="8548f-112">Чтобы нарисовать линию текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="8548f-112">To draw a line of text with GDI</span></span>  
  
1.  <span data-ttu-id="8548f-113">Используйте <xref:System.Windows.Forms.TextRenderer.DrawText%2A> метод, передав текст, который будет <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, и <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="8548f-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8548f-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="8548f-114">Compiling the Code</span></span>  
 <span data-ttu-id="8548f-115">Предыдущих примеров требуются:</span><span class="sxs-lookup"><span data-stu-id="8548f-115">The previous examples require:</span></span>  
  
-   <span data-ttu-id="8548f-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="8548f-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8548f-117">См. также</span><span class="sxs-lookup"><span data-stu-id="8548f-117">See Also</span></span>  
 [<span data-ttu-id="8548f-118">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="8548f-118">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [<span data-ttu-id="8548f-119">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="8548f-119">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="8548f-120">Практическое руководство. Разработка шрифтов и их семейств</span><span class="sxs-lookup"><span data-stu-id="8548f-120">How to: Construct Font Families and Fonts</span></span>](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [<span data-ttu-id="8548f-121">Практическое руководство. Многострочный вывод текста в прямоугольнике</span><span class="sxs-lookup"><span data-stu-id="8548f-121">How to: Draw Wrapped Text in a Rectangle</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
