---
title: "Практическое руководство. Передача аргументов в процедуру (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3debb4fa6e7b15f9c321ef207d0cc04181a98da2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="3b226-102">Практическое руководство. Передача аргументов в процедуру (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b226-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="3b226-103">При вызове процедуры следовать имя процедуры со списком аргументов в скобки.</span><span class="sxs-lookup"><span data-stu-id="3b226-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="3b226-104">Необходимо указать аргумент, соответствующий каждому обязательному параметру определяемого этой процедурой, и при необходимости можно указать дополнительные аргументы для `Optional` параметров.</span><span class="sxs-lookup"><span data-stu-id="3b226-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="3b226-105">Если не указать `Optional` параметра в вызове, необходимо включить запятую, чтобы отметить его место в списке аргументов, если указываются все последующие аргументы.</span><span class="sxs-lookup"><span data-stu-id="3b226-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="3b226-106">Если требуется передать аргумент типа данных отличается от соответствующего параметра, такие как `Byte` для `String`, можно задать для ключа проверки типов ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) для `Off`.</span><span class="sxs-lookup"><span data-stu-id="3b226-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="3b226-107">Если `Option Strict` — `On`, необходимо использовать либо расширяющих преобразований, либо ключевые слова явное преобразование.</span><span class="sxs-lookup"><span data-stu-id="3b226-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="3b226-108">Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="3b226-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="3b226-109">Дополнительные сведения см. в разделе [параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="3b226-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="3b226-110">Чтобы передать один или несколько аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="3b226-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="3b226-111">В операторе вызова после имени процедуры со скобками.</span><span class="sxs-lookup"><span data-stu-id="3b226-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="3b226-112">Заключенный в круглые скобки, поместите список аргументов.</span><span class="sxs-lookup"><span data-stu-id="3b226-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="3b226-113">Включить аргумент для каждого обязательного параметра, определяемого этой процедурой, а аргументы должны разделяться запятыми.</span><span class="sxs-lookup"><span data-stu-id="3b226-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="3b226-114">Убедитесь, что каждый аргумент имеет допустимое выражение, результатом вычисления которого преобразуется в тип процедуры определяет для соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="3b226-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="3b226-115">Если параметр определен как [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md), можно включить его в списке аргументов или удалите его.</span><span class="sxs-lookup"><span data-stu-id="3b226-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="3b226-116">Если он опущен, процедура будет использовать значение по умолчанию, определенное для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="3b226-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="3b226-117">Если не указан аргумент для `Optional` параметр и в списке параметров после него имеется еще один параметр, можно отметить место пропущенный аргумент по Лишняя запятая в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="3b226-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="3b226-118">В следующем примере вызывается [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> функции.</span><span class="sxs-lookup"><span data-stu-id="3b226-118">The following example calls the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     <span data-ttu-id="3b226-119">В предыдущем примере передается обязательный первый аргумент, который является строкой сообщения для отображения.</span><span class="sxs-lookup"><span data-stu-id="3b226-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="3b226-120">Он указывается аргумент для необязательный второй параметр, который определяет кнопки, отображаемые в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="3b226-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="3b226-121">Так как вызов не предоставляет значение, `MsgBox` использует значение по умолчанию `MsgBoxStyle.OKOnly`, отображающий только **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="3b226-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="3b226-122">Вторая запятая в списке аргументов отмечает место пропущенного второго параметра, а последняя строка передается необязательный третий параметр `MsgBox`, содержит текст, отображаемый в заголовке окна.</span><span class="sxs-lookup"><span data-stu-id="3b226-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b226-123">См. также</span><span class="sxs-lookup"><span data-stu-id="3b226-123">See Also</span></span>  
 [<span data-ttu-id="3b226-124">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="3b226-124">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="3b226-125">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="3b226-125">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="3b226-126">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="3b226-126">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="3b226-127">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="3b226-127">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="3b226-128">Практическое руководство. Определение параметра для процедуры</span><span class="sxs-lookup"><span data-stu-id="3b226-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="3b226-129">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="3b226-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="3b226-130">Рекурсивные процедуры</span><span class="sxs-lookup"><span data-stu-id="3b226-130">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="3b226-131">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="3b226-131">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="3b226-132">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="3b226-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="3b226-133">Объектно-ориентированное программирование</span><span class="sxs-lookup"><span data-stu-id="3b226-133">Object-Oriented Programming</span></span>](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
