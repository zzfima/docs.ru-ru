---
title: Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 899c33e6615e2979ba7abe0f537dbe05fd104beb
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965570"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="b5ae3-102">Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5ae3-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="b5ae3-103">Объект `Sub` процедура не возвращает значение вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="b5ae3-104">Вызвать его напрямую с помощью отдельного вызывающего оператора.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="b5ae3-105">Его нельзя вызвать, просто указав ее имя в выражении.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="b5ae3-106">Для вызова процедуры Sub</span><span class="sxs-lookup"><span data-stu-id="b5ae3-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="b5ae3-107">Укажите имя `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="b5ae3-108">После имени процедуры с помощью скобок, заключите список аргументов.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="b5ae3-109">Если аргументы не используются, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="b5ae3-110">Тем не менее с помощью скобок делает код более удобным для чтения.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="b5ae3-111">Поместите аргументы в списке аргументов в скобки, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="b5ae3-112">Убедитесь, что аргументы указаны в том же порядке, `Sub` процедуры определены соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="b5ae3-113">В следующем примере вызывается Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> функции для активации окна приложения.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-113">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="b5ae3-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> принимает заголовок окна в качестве единственного аргумента.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="b5ae3-115">Он не возвращает значение вызывающему коду.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="b5ae3-116">Если Блокнот не запущена, в примере создается исключение <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="b5ae3-117">`Shell` Предполагается приложения находятся в указанных путей.</span><span class="sxs-lookup"><span data-stu-id="b5ae3-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="b5ae3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="b5ae3-118">See also</span></span>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [<span data-ttu-id="b5ae3-119">Процедуры</span><span class="sxs-lookup"><span data-stu-id="b5ae3-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b5ae3-120">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="b5ae3-120">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="b5ae3-121">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="b5ae3-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b5ae3-122">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="b5ae3-122">Sub Statement</span></span>](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="b5ae3-123">Практическое руководство. Создание процедуры</span><span class="sxs-lookup"><span data-stu-id="b5ae3-123">How to: Create a Procedure</span></span>](./how-to-create-a-procedure.md)
- [<span data-ttu-id="b5ae3-124">Практическое руководство. Вызов процедуры, возвращающей значение</span><span class="sxs-lookup"><span data-stu-id="b5ae3-124">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="b5ae3-125">Практическое руководство. Вызов обработчика событий в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5ae3-125">How to: Call an Event Handler in Visual Basic</span></span>](./how-to-call-an-event-handler.md)
