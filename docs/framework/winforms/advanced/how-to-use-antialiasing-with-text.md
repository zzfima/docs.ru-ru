---
title: Практическое руководство. Сглаживание текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [Windows Forms], smoothing drawn
- antialiasing [Windows Forms], using with text
- text [Windows Forms], smoothing
- text [Windows Forms], antialiasing
- strings [Windows Forms], antialiasing when drawing
ms.assetid: 48fc34f3-f236-4b01-a0cb-f0752e6d22ae
ms.openlocfilehash: 632ed329173d134495a424b34ca7c71e402607bf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182476"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="4cab8-102">Практическое руководство. Сглаживание текста</span><span class="sxs-lookup"><span data-stu-id="4cab8-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="4cab8-103">*Антиалиазирование* относится к сглаживанию зубчатых краев нарисованной графики и текста, чтобы улучшить их внешний вид или читаемость.</span><span class="sxs-lookup"><span data-stu-id="4cab8-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="4cab8-104">С помощью управляемых классов GDI можно визуализировать высококачественный антиалиазный текст, а также текст более низкого качества.</span><span class="sxs-lookup"><span data-stu-id="4cab8-104">With the managed GDI+ classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="4cab8-105">Как правило, более высокое качество визуализации занимает больше времени обработки, чем более низкое качество визуализации.</span><span class="sxs-lookup"><span data-stu-id="4cab8-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="4cab8-106">Чтобы установить уровень качества <xref:System.Drawing.Graphics.TextRenderingHint%2A> текста, <xref:System.Drawing.Graphics> установите свойство <xref:System.Drawing.Text.TextRenderingHint> одного из элементов перечисления</span><span class="sxs-lookup"><span data-stu-id="4cab8-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cab8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="4cab8-107">Example</span></span>  
 <span data-ttu-id="4cab8-108">Следующий пример кода рисует текст с двумя различными настройками качества.</span><span class="sxs-lookup"><span data-stu-id="4cab8-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  

 <span data-ttu-id="4cab8-109">На следующей иллюстрации показан выход кода примера:</span><span class="sxs-lookup"><span data-stu-id="4cab8-109">The following illustration shows the output of the example code:</span></span>  
  
 ![Скриншот, который показывает текст с двумя различными настройками качества.](./media/how-to-use-antialiasing-with-text/antialiasing-text-quality-settings.png)  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4cab8-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="4cab8-111">Compiling the Code</span></span>  
 <span data-ttu-id="4cab8-112">Предыдущий пример кода предназначен для использования с <xref:System.Windows.Forms.PaintEventArgs> `e`Windows Forms, и <xref:System.Windows.Forms.PaintEventHandler>он требует, который является параметром .</span><span class="sxs-lookup"><span data-stu-id="4cab8-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cab8-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4cab8-113">See also</span></span>

- [<span data-ttu-id="4cab8-114">Шрифты и текст</span><span class="sxs-lookup"><span data-stu-id="4cab8-114">Using Fonts and Text</span></span>](using-fonts-and-text.md)
