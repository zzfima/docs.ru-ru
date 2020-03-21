---
title: Практическое руководство. Вывод текста по вертикали
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
ms.openlocfilehash: 86401342625f593945b801f7619ef9ca9681317c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182560"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="215bd-102">Практическое руководство. Вывод текста по вертикали</span><span class="sxs-lookup"><span data-stu-id="215bd-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="215bd-103">Объект можно <xref:System.Drawing.StringFormat> использовать для указания текста нарисованным по вертикали, а не по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="215bd-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="215bd-104">Пример</span><span class="sxs-lookup"><span data-stu-id="215bd-104">Example</span></span>  
 <span data-ttu-id="215bd-105">Следующий пример присваивает <xref:System.Drawing.StringFormatFlags.DirectionVertical> значение <xref:System.Drawing.StringFormat> свойству <xref:System.Drawing.StringFormat.FormatFlags%2A> объекта.</span><span class="sxs-lookup"><span data-stu-id="215bd-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="215bd-106">Этот <xref:System.Drawing.StringFormat> объект передается <xref:System.Drawing.Graphics.DrawString%2A> методу <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="215bd-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="215bd-107">Значение <xref:System.Drawing.StringFormatFlags.DirectionVertical> является участником <xref:System.Drawing.StringFormatFlags> перечисления.</span><span class="sxs-lookup"><span data-stu-id="215bd-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="215bd-108">На следующей иллюстрации показан вертикальный текст:</span><span class="sxs-lookup"><span data-stu-id="215bd-108">The following illustration shows the vertical text:</span></span>
  
 ![Графика, отображая вертикальный текст шрифта.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="215bd-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="215bd-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="215bd-111">Предыдущий пример предназначен для использования с Windows <xref:System.Windows.Forms.PaintEventArgs> `e` Forms, и <xref:System.Windows.Forms.PaintEventHandler>он требует, который является параметром .</span><span class="sxs-lookup"><span data-stu-id="215bd-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="215bd-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="215bd-112">See also</span></span>

- [<span data-ttu-id="215bd-113">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="215bd-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
