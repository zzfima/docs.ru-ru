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
ms.openlocfilehash: 2adb33e3d05e38ee71be8a12cdc2e20dc8c55c72
ms.sourcegitcommit: ceca5a1c027627abcca2767567703c3879f33325
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2018
ms.locfileid: "36338134"
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="3e5be-102">Практическое руководство. Сглаживание текста</span><span class="sxs-lookup"><span data-stu-id="3e5be-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="3e5be-103">*Сглаживание* ссылается на сглаживания неровными краями графических элементов и текста для улучшения их внешнего вида и удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="3e5be-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="3e5be-104">Управляемые [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] классов, можно вывести высококачественный сглаженный текст, а также текст низкого качества.</span><span class="sxs-lookup"><span data-stu-id="3e5be-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="3e5be-105">Как правило более качественная визуализация занимает больше времени обработки, чем менее качественная.</span><span class="sxs-lookup"><span data-stu-id="3e5be-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="3e5be-106">Чтобы установить уровень качества текста, задайте <xref:System.Drawing.Graphics.TextRenderingHint%2A> свойство <xref:System.Drawing.Graphics> к одному из элементов <xref:System.Drawing.Text.TextRenderingHint> перечисления</span><span class="sxs-lookup"><span data-stu-id="3e5be-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e5be-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3e5be-107">Example</span></span>  
 <span data-ttu-id="3e5be-108">В следующем примере кода выводит текст с двумя различными уровнями качества.</span><span class="sxs-lookup"><span data-stu-id="3e5be-108">The following code example draws text with two different quality settings.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
 
 <span data-ttu-id="3e5be-109">Ниже показан результат выполнения примера кода:</span><span class="sxs-lookup"><span data-stu-id="3e5be-109">The following illustration shows the output of the example code:</span></span>  
  
 <span data-ttu-id="3e5be-110">![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="3e5be-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3e5be-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3e5be-111">Compiling the Code</span></span>  
 <span data-ttu-id="3e5be-112">Предыдущий пример кода предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="3e5be-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e5be-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3e5be-113">See Also</span></span>  
 [<span data-ttu-id="3e5be-114">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="3e5be-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
