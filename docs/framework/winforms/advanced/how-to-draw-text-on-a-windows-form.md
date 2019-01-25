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
# <a name="how-to-draw-text-on-a-windows-form"></a><span data-ttu-id="f9072-102">Как выполнить Рисование текста в форме Windows</span><span class="sxs-lookup"><span data-stu-id="f9072-102">How to: Draw Text on a Windows Form</span></span>
<span data-ttu-id="f9072-103">В следующем примере кода показано, как использовать <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> для рисования текста в форме.</span><span class="sxs-lookup"><span data-stu-id="f9072-103">The following code example shows how to use the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> to draw text on a form.</span></span> <span data-ttu-id="f9072-104">Кроме того, можно использовать <xref:System.Windows.Forms.TextRenderer> для рисования текста в форме.</span><span class="sxs-lookup"><span data-stu-id="f9072-104">Alternatively, you can use <xref:System.Windows.Forms.TextRenderer> for drawing text on a form.</span></span> <span data-ttu-id="f9072-105">Дополнительные сведения см. в разделе [Как Рисование текста с использованием GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).</span><span class="sxs-lookup"><span data-stu-id="f9072-105">For more information, see [How to: Draw Text with GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9072-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f9072-106">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f9072-107">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="f9072-107">Compiling the Code</span></span>  
 <span data-ttu-id="f9072-108">Нельзя вызывать <xref:System.Drawing.Graphics.DrawString%2A> метод в <xref:System.Windows.Forms.Form.Load> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="f9072-108">You cannot call the <xref:System.Drawing.Graphics.DrawString%2A> method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="f9072-109">Если скрыта другой формой или изменении размера формы, рисунок перерисовываться не будет.</span><span class="sxs-lookup"><span data-stu-id="f9072-109">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="f9072-110">Чтобы сделать автоматическую перерисовку, нужно переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="f9072-110">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f9072-111">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="f9072-111">Robust Programming</span></span>  
 <span data-ttu-id="f9072-112">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="f9072-112">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="f9072-113">Шрифт Arial не установлен.</span><span class="sxs-lookup"><span data-stu-id="f9072-113">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9072-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f9072-114">See also</span></span>
- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Windows.Forms.TextRenderer.DrawText%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.TextFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="f9072-115">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="f9072-115">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [<span data-ttu-id="f9072-116">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="f9072-116">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
