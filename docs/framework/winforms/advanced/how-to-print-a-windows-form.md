---
title: Практическое руководство. Печать формы Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 42940654a0754ac3616ca7983af07d20607f480f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="a5fa4-102">Практическое руководство. Печать формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5fa4-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="a5fa4-103">В рамках процесса разработки обычно требуется распечатать копию формы Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a5fa4-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="a5fa4-104">В следующем примере кода показано, как напечатать копию текущей формы с помощью <xref:System.Drawing.Graphics.CopyFromScreen%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="a5fa4-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5fa4-105">Пример</span><span class="sxs-lookup"><span data-stu-id="a5fa4-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a5fa4-106">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a5fa4-106">Compiling the Code</span></span>  
 <span data-ttu-id="a5fa4-107">Это полный пример кода, содержащий `Main` метод.</span><span class="sxs-lookup"><span data-stu-id="a5fa4-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a5fa4-108">Отказоустойчивость</span><span class="sxs-lookup"><span data-stu-id="a5fa4-108">Robust Programming</span></span>  
 <span data-ttu-id="a5fa4-109">При следующих условиях возможно возникновение исключения:</span><span class="sxs-lookup"><span data-stu-id="a5fa4-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="a5fa4-110">У вас разрешения на доступ к принтеру.</span><span class="sxs-lookup"><span data-stu-id="a5fa4-110">You do not have permission to access the printer.</span></span>  
  
-   <span data-ttu-id="a5fa4-111">Нет не установлен принтер.</span><span class="sxs-lookup"><span data-stu-id="a5fa4-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="a5fa4-112">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a5fa4-112">.NET Framework Security</span></span>  
 <span data-ttu-id="a5fa4-113">Чтобы запустить этот пример кода, необходимо иметь разрешение на доступ к принтеру, используемому на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a5fa4-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5fa4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="a5fa4-114">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="a5fa4-115">Практическое руководство. Прорисовка изображений с использованием GDI+</span><span class="sxs-lookup"><span data-stu-id="a5fa4-115">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [<span data-ttu-id="a5fa4-116">Практическое руководство. Печать графических изображений в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5fa4-116">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
