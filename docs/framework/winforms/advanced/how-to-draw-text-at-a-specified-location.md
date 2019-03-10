---
title: Практическое руководство. Рисование текста в указанном расположении
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
ms.openlocfilehash: 3bca6cd364ed4e0d0179c13fb378449b7cf05739
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705354"
---
# <a name="how-to-draw-text-at-a-specified-location"></a><span data-ttu-id="f21eb-102">Практическое руководство. Рисование текста в указанном расположении</span><span class="sxs-lookup"><span data-stu-id="f21eb-102">How to: Draw Text at a Specified Location</span></span>
<span data-ttu-id="f21eb-103">При выполнении пользовательского рисования можно рисовать текст в одной строке по горизонтали, начиная с указанной точки.</span><span class="sxs-lookup"><span data-stu-id="f21eb-103">When you perform custom drawing, you can draw text in a single horizontal line starting at a specified point.</span></span> <span data-ttu-id="f21eb-104">Таким образом можно рисовать текст с помощью <xref:System.Drawing.Graphics.DrawString%2A> перегруженным методом <xref:System.Drawing.Graphics> класс, принимающий <xref:System.Drawing.Point> или <xref:System.Drawing.PointF> параметра.</span><span class="sxs-lookup"><span data-stu-id="f21eb-104">You can draw text in this manner by using the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method of the <xref:System.Drawing.Graphics> class that takes a <xref:System.Drawing.Point> or <xref:System.Drawing.PointF> parameter.</span></span> <span data-ttu-id="f21eb-105"><xref:System.Drawing.Graphics.DrawString%2A> Также требует <xref:System.Drawing.Brush> и <xref:System.Drawing.Font></span><span class="sxs-lookup"><span data-stu-id="f21eb-105">The <xref:System.Drawing.Graphics.DrawString%2A> method also requires a <xref:System.Drawing.Brush> and <xref:System.Drawing.Font></span></span>  
  
 <span data-ttu-id="f21eb-106">Можно также использовать <xref:System.Windows.Forms.TextRenderer.DrawText%2A> перегруженным методом <xref:System.Windows.Forms.TextRenderer> , принимающий <xref:System.Drawing.Point>.</span><span class="sxs-lookup"><span data-stu-id="f21eb-106">You can also use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> overloaded method of the <xref:System.Windows.Forms.TextRenderer> that takes a <xref:System.Drawing.Point>.</span></span> <span data-ttu-id="f21eb-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> также требуется <xref:System.Drawing.Color> и <xref:System.Drawing.Font>.</span><span class="sxs-lookup"><span data-stu-id="f21eb-107"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> also requires a <xref:System.Drawing.Color> and a <xref:System.Drawing.Font>.</span></span>  
  
 <span data-ttu-id="f21eb-108">На следующем рисунке показан вывод текста, рисуемого в заданной точке при использовании <xref:System.Drawing.Graphics.DrawString%2A> перегруженный метод.</span><span class="sxs-lookup"><span data-stu-id="f21eb-108">The following illustration shows the output of text drawn at a specified point when you use the <xref:System.Drawing.Graphics.DrawString%2A> overloaded method.</span></span>  
  
 <span data-ttu-id="f21eb-109">![Текст шрифтов](./media/csfontstext1.png "csfontstext1")</span><span class="sxs-lookup"><span data-stu-id="f21eb-109">![Fonts Text](./media/csfontstext1.png "csfontstext1")</span></span>  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="f21eb-110">Рисование линии текста с помощью GDI +</span><span class="sxs-lookup"><span data-stu-id="f21eb-110">To draw a line of text with GDI+</span></span>  
  
1.  <span data-ttu-id="f21eb-111">Используйте <xref:System.Drawing.Graphics.DrawString%2A> , передавая текст, <xref:System.Drawing.Point> или <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, и <xref:System.Drawing.Brush>.</span><span class="sxs-lookup"><span data-stu-id="f21eb-111">Use the <xref:System.Drawing.Graphics.DrawString%2A> method, passing the text you want, <xref:System.Drawing.Point> or <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Brush>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a><span data-ttu-id="f21eb-112">Рисование линии текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="f21eb-112">To draw a line of text with GDI</span></span>  
  
1.  <span data-ttu-id="f21eb-113">Используйте <xref:System.Windows.Forms.TextRenderer.DrawText%2A> , передавая текст, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, и <xref:System.Drawing.Color>.</span><span class="sxs-lookup"><span data-stu-id="f21eb-113">Use the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method, passing the text you want, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, and <xref:System.Drawing.Color>.</span></span>  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f21eb-114">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f21eb-114">Compiling the Code</span></span>  
 <span data-ttu-id="f21eb-115">Для работы предыдущих примеров:</span><span class="sxs-lookup"><span data-stu-id="f21eb-115">The previous examples require:</span></span>  
  
-   <span data-ttu-id="f21eb-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="f21eb-116"><xref:System.Windows.Forms.PaintEventArgs>  `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f21eb-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f21eb-117">See also</span></span>
- [<span data-ttu-id="f21eb-118">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="f21eb-118">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
- [<span data-ttu-id="f21eb-119">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="f21eb-119">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="f21eb-120">Практическое руководство. Шрифты и их семейств</span><span class="sxs-lookup"><span data-stu-id="f21eb-120">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)
- [<span data-ttu-id="f21eb-121">Практическое руководство. Многострочный вывод текста в прямоугольнике</span><span class="sxs-lookup"><span data-stu-id="f21eb-121">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)
