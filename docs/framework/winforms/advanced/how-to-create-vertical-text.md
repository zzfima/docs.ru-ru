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
ms.openlocfilehash: 8398b3f18b764743bac19022b69e7f6fac0f7d57
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626000"
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="4c8cd-102">Практическое руководство. Вывод текста по вертикали</span><span class="sxs-lookup"><span data-stu-id="4c8cd-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="4c8cd-103">Можно использовать <xref:System.Drawing.StringFormat> для указания, что текст должен выводиться по вертикали, а не по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4c8cd-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4c8cd-104">Example</span></span>  
 <span data-ttu-id="4c8cd-105">В следующем примере присваивается значение <xref:System.Drawing.StringFormatFlags.DirectionVertical> для <xref:System.Drawing.StringFormat.FormatFlags%2A> свойство <xref:System.Drawing.StringFormat> объекта.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="4c8cd-106">Что <xref:System.Drawing.StringFormat> объект передается <xref:System.Drawing.Graphics.DrawString%2A> метод <xref:System.Drawing.Graphics> класса.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="4c8cd-107">Значение <xref:System.Drawing.StringFormatFlags.DirectionVertical> является членом <xref:System.Drawing.StringFormatFlags> перечисления.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="4c8cd-108">На следующем рисунке показано текста по вертикали:</span><span class="sxs-lookup"><span data-stu-id="4c8cd-108">The following illustration shows the vertical text:</span></span> 
  
 ![Рисунок, показывающий вертикального шрифта текста.](./media/how-to-create-vertical-text/vertical-font-text-graphic.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4c8cd-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4c8cd-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="4c8cd-111">Предыдущий пример предназначен для работы с Windows Forms и требует <xref:System.Windows.Forms.PaintEventArgs> `e` , который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="4c8cd-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c8cd-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4c8cd-112">See also</span></span>

- [<span data-ttu-id="4c8cd-113">Практическое руководство. Рисование текста с использованием GDI</span><span class="sxs-lookup"><span data-stu-id="4c8cd-113">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)
