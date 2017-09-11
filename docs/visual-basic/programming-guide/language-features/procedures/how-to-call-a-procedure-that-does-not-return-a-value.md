---
title: "Практическое руководство: вызов процедуры, возвращающей значение (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 26120b763d2ecedb3aa43adb08e4c87c2b1e0be1
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="99f8e-102">Практическое руководство. Вызов процедуры, которая не возвращает значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99f8e-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="99f8e-103">A `Sub` процедура не возвращает значения в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="99f8e-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="99f8e-104">Можно вызвать явным образом с помощью отдельного вызывающего оператора.</span><span class="sxs-lookup"><span data-stu-id="99f8e-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="99f8e-105">Нельзя вызвать, просто указав ее имя в выражении.</span><span class="sxs-lookup"><span data-stu-id="99f8e-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="99f8e-106">Для вызова процедуры Sub</span><span class="sxs-lookup"><span data-stu-id="99f8e-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="99f8e-107">Укажите имя `Sub` процедуры.</span><span class="sxs-lookup"><span data-stu-id="99f8e-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="99f8e-108">После имени процедуры с заключенным в списке аргументов скобки.</span><span class="sxs-lookup"><span data-stu-id="99f8e-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="99f8e-109">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="99f8e-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="99f8e-110">Однако с помощью скобок делает код более удобными для чтения.</span><span class="sxs-lookup"><span data-stu-id="99f8e-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="99f8e-111">Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="99f8e-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="99f8e-112">Убедитесь, что аргументы указаны в том же порядке, `Sub` процедуры определены соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="99f8e-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="99f8e-113">В следующем примере вызывается [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>функцию для активации окна приложения.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="99f8e-113">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="99f8e-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>принимает в качестве единственного аргумента заголовок окна.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="99f8e-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="99f8e-115">Возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="99f8e-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="99f8e-116">Если Блокнот не запущена, в примере возникает исключение <xref:System.ArgumentException>.</xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="99f8e-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="99f8e-117">`Shell` Процедура предполагает приложения, в указанных путей.</span><span class="sxs-lookup"><span data-stu-id="99f8e-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     <span data-ttu-id="99f8e-118">[!code-vb[VbVbalrCatRef&11;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="99f8e-118">[!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99f8e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="99f8e-119">See Also</span></span>  
 <span data-ttu-id="99f8e-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></xref:Microsoft.VisualBasic.Interaction.Shell%2A></span><span class="sxs-lookup"><span data-stu-id="99f8e-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></span></span>   
 <span data-ttu-id="99f8e-121"><xref:System.ArgumentException></xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="99f8e-121"><xref:System.ArgumentException></span></span>   
<span data-ttu-id="99f8e-122"> [Процедуры](./index.md) </span><span class="sxs-lookup"><span data-stu-id="99f8e-122"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="99f8e-123"> [Sub-процедуры](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="99f8e-123"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="99f8e-124"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="99f8e-124"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="99f8e-125"> [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="99f8e-125"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="99f8e-126"> [Практическое руководство: создание процедуры](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="99f8e-126"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="99f8e-127"> [Практическое руководство: вызов процедуры, возвращающей значение](./how-to-call-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="99f8e-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="99f8e-128"> [Практическое руководство: вызов обработчика событий в Visual Basic](./how-to-call-an-event-handler.md)</span><span class="sxs-lookup"><span data-stu-id="99f8e-128"> [How to: Call an Event Handler in Visual Basic](./how-to-call-an-event-handler.md)</span></span>
