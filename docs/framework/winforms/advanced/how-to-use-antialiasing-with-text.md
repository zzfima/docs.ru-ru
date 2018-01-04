---
title: "Практическое руководство. Сглаживание текста"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: edd31ec5b9d94ac1791fb0f2a73522fdf4178627
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-antialiasing-with-text"></a><span data-ttu-id="fabc7-102">Практическое руководство. Сглаживание текста</span><span class="sxs-lookup"><span data-stu-id="fabc7-102">How to: Use Antialiasing with Text</span></span>
<span data-ttu-id="fabc7-103">*Сглаживание* ссылается на сглаживания неровными краями графических элементов и текста для улучшения их внешнего вида и удобства чтения.</span><span class="sxs-lookup"><span data-stu-id="fabc7-103">*Antialiasing* refers to the smoothing of jagged edges of drawn graphics and text to improve their appearance or readability.</span></span> <span data-ttu-id="fabc7-104">Управляемые [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] классов, можно вывести высококачественный сглаженный текст, а также текст низкого качества.</span><span class="sxs-lookup"><span data-stu-id="fabc7-104">With the managed [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes, you can render high quality antialiased text, as well as lower quality text.</span></span> <span data-ttu-id="fabc7-105">Как правило более качественная визуализация занимает больше времени обработки, чем менее качественная.</span><span class="sxs-lookup"><span data-stu-id="fabc7-105">Typically, higher quality rendering takes more processing time than lower quality rendering.</span></span> <span data-ttu-id="fabc7-106">Чтобы установить уровень качества текста, задайте <xref:System.Drawing.Graphics.TextRenderingHint%2A> свойство <xref:System.Drawing.Graphics> к одному из элементов <xref:System.Drawing.Text.TextRenderingHint> перечисления</span><span class="sxs-lookup"><span data-stu-id="fabc7-106">To set the text quality level, set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property of a <xref:System.Drawing.Graphics> to one of the elements of the <xref:System.Drawing.Text.TextRenderingHint> enumeration</span></span>  
  
## <a name="example"></a><span data-ttu-id="fabc7-107">Пример</span><span class="sxs-lookup"><span data-stu-id="fabc7-107">Example</span></span>  
 <span data-ttu-id="fabc7-108">В следующем примере кода выводит текст с двумя различными уровнями качества.</span><span class="sxs-lookup"><span data-stu-id="fabc7-108">The following code example draws text with two different quality settings.</span></span>  
  
 <span data-ttu-id="fabc7-109">Ниже показан результат выполнения этого примера кода.</span><span class="sxs-lookup"><span data-stu-id="fabc7-109">The following illustration shows the output of the cod example code.</span></span>  
  
 <span data-ttu-id="fabc7-110">![Текст шрифтов](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span><span class="sxs-lookup"><span data-stu-id="fabc7-110">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext10.png "FontsText10")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.FontsAndText#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fabc7-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="fabc7-111">Compiling the Code</span></span>  
 <span data-ttu-id="fabc7-112">Предыдущий пример кода предназначен для работы с Windows Forms, и для него необходим <xref:System.Windows.Forms.PaintEventArgs> `e`, который является параметром <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="fabc7-112">The preceding code example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabc7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="fabc7-113">See Also</span></span>  
 [<span data-ttu-id="fabc7-114">Работами со шрифтами и текстом</span><span class="sxs-lookup"><span data-stu-id="fabc7-114">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
