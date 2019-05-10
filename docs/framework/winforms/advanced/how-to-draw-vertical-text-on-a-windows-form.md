---
title: Практическое руководство. Рисование текста по вертикали в Windows Forms
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
ms.openlocfilehash: 660d7abae5463c976e60b7d9caeae8a798d122ca
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626176"
---
# <a name="how-to-draw-vertical-text-on-a-windows-form"></a><span data-ttu-id="3203f-102">Практическое руководство. Рисование текста по вертикали в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3203f-102">How to: Draw Vertical Text on a Windows Form</span></span>
<span data-ttu-id="3203f-103">В следующем примере кода показано, как нарисовать вертикальный текст в форме с помощью <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics>.</span><span class="sxs-lookup"><span data-stu-id="3203f-103">The following code example shows how to draw vertical text on a form by using the <xref:System.Drawing.Graphics.DrawString%2A> method of <xref:System.Drawing.Graphics>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3203f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3203f-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3203f-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3203f-105">Compiling the Code</span></span>  
 <span data-ttu-id="3203f-106">Этот метод нельзя вызывать <xref:System.Windows.Forms.Form.Load> обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="3203f-106">You cannot call this method in the <xref:System.Windows.Forms.Form.Load> event handler.</span></span> <span data-ttu-id="3203f-107">Если скрыта другой формой или изменении размера формы, рисунок перерисовываться не будет.</span><span class="sxs-lookup"><span data-stu-id="3203f-107">The drawn content will not be redrawn if the form is resized or obscured by another form.</span></span> <span data-ttu-id="3203f-108">Чтобы сделать автоматическую перерисовку, нужно переопределить <xref:System.Windows.Forms.Control.OnPaint%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="3203f-108">To make your content automatically repaint, you should override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3203f-109">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="3203f-109">Robust Programming</span></span>  
 <span data-ttu-id="3203f-110">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="3203f-110">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="3203f-111">Шрифт Arial не установлен.</span><span class="sxs-lookup"><span data-stu-id="3203f-111">The Arial font is not installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3203f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3203f-112">See also</span></span>

- <xref:System.Drawing.Graphics.DrawString%2A>
- <xref:System.Drawing.StringFormat.FormatFlags%2A>
- <xref:System.Drawing.StringFormatFlags>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [<span data-ttu-id="3203f-113">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="3203f-113">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="3203f-114">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="3203f-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
