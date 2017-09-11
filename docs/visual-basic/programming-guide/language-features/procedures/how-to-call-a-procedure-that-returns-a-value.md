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
- procedures, returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
caps.latest.revision: 15
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
ms.openlocfilehash: cc1e274a705618213c830d7cf4f61a5e64afd980
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a><span data-ttu-id="e69ac-102">Практическое руководство. Вызов процедуры, возвращающей значение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e69ac-102">How to: Call a Procedure That Returns a Value (Visual Basic)</span></span>
<span data-ttu-id="e69ac-103">A `Function` процедура возвращает значение в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="e69ac-103">A `Function` procedure returns a value to the calling code.</span></span> <span data-ttu-id="e69ac-104">Можно вызвать его, включая ее имя и аргументы справа от оператора присваивания или в составе выражения.</span><span class="sxs-lookup"><span data-stu-id="e69ac-104">You call it by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span>  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a><span data-ttu-id="e69ac-105">Чтобы вызвать процедуру Function в выражении</span><span class="sxs-lookup"><span data-stu-id="e69ac-105">To call a Function procedure within an expression</span></span>  
  
1.  <span data-ttu-id="e69ac-106">Использовать `Function` так же, как бы переменной имя процедуры.</span><span class="sxs-lookup"><span data-stu-id="e69ac-106">Use the `Function` procedure name the same way you would use a variable.</span></span> <span data-ttu-id="e69ac-107">Можно использовать `Function` вызов процедуры везде, где можно использовать переменную или константу в выражении.</span><span class="sxs-lookup"><span data-stu-id="e69ac-107">You can use a `Function` procedure call anywhere you can use a variable or constant in an expression.</span></span>  
  
2.  <span data-ttu-id="e69ac-108">После имени процедуры с заключенным в списке аргументов скобки.</span><span class="sxs-lookup"><span data-stu-id="e69ac-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e69ac-109">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="e69ac-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="e69ac-110">Однако с помощью скобок делает код более удобными для чтения.</span><span class="sxs-lookup"><span data-stu-id="e69ac-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="e69ac-111">Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="e69ac-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e69ac-112">Убедитесь, что аргументы указаны в том же порядке, `Function` процедуры определены соответствующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e69ac-112">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="e69ac-113">Кроме того можно передать один или несколько аргументов по имени.</span><span class="sxs-lookup"><span data-stu-id="e69ac-113">Alternatively, you can pass one or more arguments by name.</span></span> <span data-ttu-id="e69ac-114">Дополнительные сведения см. в разделе [передача аргументов по позиции и по имени](./passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="e69ac-114">For more information, see [Passing Arguments by Position and by Name](./passing-arguments-by-position-and-by-name.md).</span></span>  
  
4.  <span data-ttu-id="e69ac-115">Значение, возвращаемое процедурой участвует в выражении, как и значение переменной или константа.</span><span class="sxs-lookup"><span data-stu-id="e69ac-115">The value returned from the procedure participates in the expression just as the value of a variable or constant would.</span></span>  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a><span data-ttu-id="e69ac-116">Чтобы вызвать процедуру Function в операторе присваивания</span><span class="sxs-lookup"><span data-stu-id="e69ac-116">To call a Function procedure in an assignment statement</span></span>  
  
1.  <span data-ttu-id="e69ac-117">Используйте `Function` имя процедуры после равенства (`=`) входа в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="e69ac-117">Use the `Function` procedure name following the equal (`=`) sign in the assignment statement.</span></span>  
  
2.  <span data-ttu-id="e69ac-118">После имени процедуры с заключенным в списке аргументов скобки.</span><span class="sxs-lookup"><span data-stu-id="e69ac-118">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e69ac-119">Если не указано никаких аргументов, скобки можно опустить.</span><span class="sxs-lookup"><span data-stu-id="e69ac-119">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="e69ac-120">Однако с помощью скобок делает код более удобными для чтения.</span><span class="sxs-lookup"><span data-stu-id="e69ac-120">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="e69ac-121">Поместите аргументы в списке аргументов в круглых скобках, разделенные запятыми.</span><span class="sxs-lookup"><span data-stu-id="e69ac-121">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e69ac-122">Убедитесь, что аргументы указаны в том же порядке, `Function` процедура определяет соответствующие им параметры, если только не используется их передача по имени.</span><span class="sxs-lookup"><span data-stu-id="e69ac-122">Be sure you supply the arguments in the same order that the `Function` procedure defines the corresponding parameters, unless you are passing them by name.</span></span>  
  
4.  <span data-ttu-id="e69ac-123">Значение, возвращаемое процедурой, хранится в переменной или свойстве в левой части оператора присваивания.</span><span class="sxs-lookup"><span data-stu-id="e69ac-123">The value returned from the procedure is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e69ac-124">Пример</span><span class="sxs-lookup"><span data-stu-id="e69ac-124">Example</span></span>  
 <span data-ttu-id="e69ac-125">В следующем примере вызывается [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A>для получения значения переменной среды операционной системы.</xref:Microsoft.VisualBasic.Interaction.Environ%2A></span><span class="sxs-lookup"><span data-stu-id="e69ac-125">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.Environ%2A> to retrieve the value of an operating system environment variable.</span></span> <span data-ttu-id="e69ac-126">Первая строка вызывает `Environ` в выражении, а вторая строка вызывает его в операторе присваивания.</span><span class="sxs-lookup"><span data-stu-id="e69ac-126">The first line calls `Environ` within an expression, and the second line calls it in an assignment statement.</span></span> <span data-ttu-id="e69ac-127">`Environ`принимает имя переменной в качестве единственного аргумента.</span><span class="sxs-lookup"><span data-stu-id="e69ac-127">`Environ` takes the variable name as its sole argument.</span></span> <span data-ttu-id="e69ac-128">Значение переменной возвращается в вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="e69ac-128">It returns the variable's value to the calling code.</span></span>  
  
 <span data-ttu-id="e69ac-129">[!code-vb[VbVbcnProcedures&#7;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e69ac-129">[!code-vb[VbVbcnProcedures#7](./codesnippet/VisualBasic/how-to-call-a-procedure-that-returns-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e69ac-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e69ac-130">See Also</span></span>  
 <span data-ttu-id="e69ac-131">[Процедуры функций](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="e69ac-131">[Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="e69ac-132"> [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="e69ac-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="e69ac-133"> [Оператор Function](../../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e69ac-133"> [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="e69ac-134"> [Практическое руководство: создание процедуры, возвращающей значение](./how-to-create-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="e69ac-134"> [How to: Create a Procedure that Returns a Value](./how-to-create-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="e69ac-135"> [Практическое руководство: возвращаемое значение из процедуры](./how-to-return-a-value-from-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="e69ac-135"> [How to: Return a Value from a Procedure](./how-to-return-a-value-from-a-procedure.md) </span></span>  
<span data-ttu-id="e69ac-136"> [Практическое руководство. Вызов процедуры, которая не возвращает значение](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span><span class="sxs-lookup"><span data-stu-id="e69ac-136"> [How to: Call a Procedure that Does Not Return a Value](./how-to-call-a-procedure-that-does-not-return-a-value.md)</span></span>
