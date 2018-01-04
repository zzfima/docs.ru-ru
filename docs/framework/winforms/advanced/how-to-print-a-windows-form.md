---
title: "Практическое руководство. Печать формы Windows Forms"
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
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c50b1f47d207334160ed12674ee8efb1390fb84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="87196-102">Практическое руководство. Печать формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87196-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="87196-103">В рамках процесса разработки обычно требуется распечатать копию формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="87196-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="87196-104">В следующем примере кода показано, как напечатать копию текущей формы с помощью <xref:System.Drawing.Graphics.CopyFromScreen%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="87196-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87196-105">Пример</span><span class="sxs-lookup"><span data-stu-id="87196-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="87196-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="87196-106">Compiling the Code</span></span>  
 <span data-ttu-id="87196-107">Это полный пример кода, содержащий `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="87196-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="87196-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="87196-108">Robust Programming</span></span>  
 <span data-ttu-id="87196-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="87196-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="87196-110">У вас разрешения на доступ к принтеру.</span><span class="sxs-lookup"><span data-stu-id="87196-110">You do not have permission to access the printer.</span></span>  
  
-   <span data-ttu-id="87196-111">Нет не установлен принтер.</span><span class="sxs-lookup"><span data-stu-id="87196-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="87196-112">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="87196-112">.NET Framework Security</span></span>  
 <span data-ttu-id="87196-113">Чтобы запустить этот пример кода, необходимо иметь разрешение на доступ к принтеру, используемому на компьютере.</span><span class="sxs-lookup"><span data-stu-id="87196-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87196-114">См. также</span><span class="sxs-lookup"><span data-stu-id="87196-114">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="87196-115">Практическое руководство. Прорисовка изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="87196-115">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [<span data-ttu-id="87196-116">Практическое руководство. Печать графических изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="87196-116">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
