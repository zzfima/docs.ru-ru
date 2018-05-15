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
ms.openlocfilehash: e18ff96ea97eb636de8ab73aaa094c07b10fd456
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-draw-text-with-gdi"></a><span data-ttu-id="9744e-102">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="9744e-102">How to: Draw Text with GDI</span></span>
<span data-ttu-id="9744e-103">С <xref:System.Windows.Forms.TextRenderer.DrawText%2A> метод в <xref:System.Windows.Forms.TextRenderer> класс, доступны [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] функциональные возможности для рисования текста в форме или элементе управления.</span><span class="sxs-lookup"><span data-stu-id="9744e-103">With the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method in the <xref:System.Windows.Forms.TextRenderer> class, you can access [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] functionality for drawing text on a form or control.</span></span> [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]<span data-ttu-id="9744e-104"> визуализация текста обычно обладают большей производительностью и более точно управляют параметрами чем текста [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9744e-104"> text rendering typically offers better performance and more accurate text measuring than [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9744e-105"><xref:System.Windows.Forms.TextRenderer.DrawText%2A> Методы <xref:System.Windows.Forms.TextRenderer> класса не поддерживаются для печати.</span><span class="sxs-lookup"><span data-stu-id="9744e-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of the <xref:System.Windows.Forms.TextRenderer> class are not supported for printing.</span></span> <span data-ttu-id="9744e-106">При печати, всегда используйте <xref:System.Drawing.Graphics.DrawString%2A> методы <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="9744e-106">When printing, always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of the <xref:System.Drawing.Graphics> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9744e-107">Пример</span><span class="sxs-lookup"><span data-stu-id="9744e-107">Example</span></span>  
 <span data-ttu-id="9744e-108">В следующем примере кода показано, как отображается текст на нескольких строках внутри прямоугольника с помощью <xref:System.Windows.Forms.TextRenderer.DrawText%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="9744e-108">The following code example demonstrates how to draw text on multiple lines within a rectangle using the <xref:System.Windows.Forms.TextRenderer.DrawText%2A> method.</span></span>  
  
 [!code-csharp[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/CS/Form1.cs#7)]
 [!code-vb[System.Windows.Forms.TextRendererExamples#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TextRendererExamples/VB/Form1.vb#7)]  
  
 <span data-ttu-id="9744e-109">Чтобы отобразить с <xref:System.Windows.Forms.TextRenderer> класса, необходимо <xref:System.Drawing.IDeviceContext>, такие как <xref:System.Drawing.Graphics> и <xref:System.Drawing.Font>, расположение для рисования текста и цвет, в котором оно должно отображаться.</span><span class="sxs-lookup"><span data-stu-id="9744e-109">To render text with the <xref:System.Windows.Forms.TextRenderer> class, you need an <xref:System.Drawing.IDeviceContext>, such as a <xref:System.Drawing.Graphics> and a <xref:System.Drawing.Font>, a location to draw the text, and the color in which it should be drawn.</span></span> <span data-ttu-id="9744e-110">При необходимости можно указать текст, форматирование с использованием <xref:System.Windows.Forms.TextFormatFlags> перечисления.</span><span class="sxs-lookup"><span data-stu-id="9744e-110">Optionally, you can specify the text formatting by using the <xref:System.Windows.Forms.TextFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="9744e-111">Дополнительные сведения о получении <xref:System.Drawing.Graphics>, в разделе [как: Создание графических объектов для рисования](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span><span class="sxs-lookup"><span data-stu-id="9744e-111">For more information about obtaining a <xref:System.Drawing.Graphics>, see [How to: Create Graphics Objects for Drawing](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md).</span></span> <span data-ttu-id="9744e-112">Дополнительные сведения о построении <xref:System.Drawing.Font>, в разделе [как: шрифтов и их семейств создания](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).</span><span class="sxs-lookup"><span data-stu-id="9744e-112">For more information about constructing a <xref:System.Drawing.Font>, see [How to: Construct Font Families and Fonts](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9744e-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="9744e-113">Compiling the Code</span></span>  
 <span data-ttu-id="9744e-114">Предыдущий пример кода предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="9744e-114">The preceding code example is designed for use with Windows Forms, and it requires the <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9744e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="9744e-115">See Also</span></span>  
 <xref:System.Windows.Forms.TextRenderer>  
 <xref:System.Drawing.Font>  
 <xref:System.Drawing.Color>  
 <xref:System.Drawing.Color>  
 [<span data-ttu-id="9744e-116">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="9744e-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
