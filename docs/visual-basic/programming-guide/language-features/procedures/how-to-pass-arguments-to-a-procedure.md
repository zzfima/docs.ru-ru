---
title: "Практическое руководство: передача аргументов в процедуру (Visual Basic) | Документы Microsoft"
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
- arguments [Visual Basic], passing to procedures
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures, calling
- argument passing, procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
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
ms.openlocfilehash: 1e0a8d5e798f25f22f53f56a7c01bd69e3e14463
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="44020-102">Практическое руководство. Передача аргументов в процедуру (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44020-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="44020-103">При вызове процедуры, то после имени процедуры со списком аргументов в скобках.</span><span class="sxs-lookup"><span data-stu-id="44020-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="44020-104">Указать аргумент, соответствующий каждому обязательному параметру процедура определяет, и можно также указать дополнительные аргументы для `Optional` параметров.</span><span class="sxs-lookup"><span data-stu-id="44020-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="44020-105">Если не указать `Optional` параметр в вызове, необходимо включить запятую, чтобы отметить его место в списке аргументов, если указываются все последующие аргументы.</span><span class="sxs-lookup"><span data-stu-id="44020-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="44020-106">Если требуется передать аргумент типа данных отличается от соответствующего параметра, такие как `Byte` для `String`, можно задать для ключа проверки типов ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) для `Off`.</span><span class="sxs-lookup"><span data-stu-id="44020-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="44020-107">Если `Option Strict` — `On`, необходимо использовать либо расширяющих преобразований, либо явное преобразование ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="44020-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="44020-108">Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="44020-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="44020-109">Дополнительные сведения см. в разделе [параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="44020-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="44020-110">Для передачи одного или нескольких аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="44020-110">To pass one or more arguments to a procedure</span></span>  
  
1.  <span data-ttu-id="44020-111">В операторе вызова после имени процедуры со скобками.</span><span class="sxs-lookup"><span data-stu-id="44020-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2.  <span data-ttu-id="44020-112">Внутри скобок поместите список аргументов.</span><span class="sxs-lookup"><span data-stu-id="44020-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="44020-113">Включать аргумент для каждого обязательного параметра, определяемого процедурой и аргументов необходимо разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="44020-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3.  <span data-ttu-id="44020-114">Убедитесь, что каждый аргумент имеет допустимое выражение, результатом вычисления которого преобразуется в тип процедуры определяет для соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="44020-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4.  <span data-ttu-id="44020-115">Если параметр определен как [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md), можно либо включить его в список аргументов или пропустить.</span><span class="sxs-lookup"><span data-stu-id="44020-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="44020-116">Если он опущен, процедура использует значение по умолчанию, определенное для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="44020-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5.  <span data-ttu-id="44020-117">Если не указан аргумент для `Optional` параметр и в списке параметров после него имеется еще один параметр, можно отметить место пропущенного аргумента по лишнюю запятую в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="44020-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="44020-118">В следующем примере вызывается [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>функция.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="44020-118">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     <span data-ttu-id="44020-119">[!code-vb[VbVbcnProcedures&#34;](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="44020-119">[!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="44020-120">В предыдущем примере передается обязательный первый аргумент, который является строкой сообщения для отображения.</span><span class="sxs-lookup"><span data-stu-id="44020-120">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="44020-121">Он пропускается необязательный второй параметр, который указывает кнопки, отображаемые в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="44020-121">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="44020-122">Поскольку в вызове не передается значение, `MsgBox` использует значение по умолчанию `MsgBoxStyle.OKOnly`, которая отображает только **ОК** кнопки.</span><span class="sxs-lookup"><span data-stu-id="44020-122">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="44020-123">Вторая запятая в списке аргументов отмечает место пропущенного второго параметра, а последняя строка передается в третий необязательный параметр `MsgBox`, который является текст, отображаемый в строке заголовка.</span><span class="sxs-lookup"><span data-stu-id="44020-123">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44020-124">См. также</span><span class="sxs-lookup"><span data-stu-id="44020-124">See Also</span></span>  
 <span data-ttu-id="44020-125">[Sub-процедуры](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="44020-125">[Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="44020-126"> [Процедуры функций](./function-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="44020-126"> [Function Procedures](./function-procedures.md) </span></span>  
<span data-ttu-id="44020-127"> [Процедуры свойств](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="44020-127"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="44020-128"> [Процедуры операторов](./operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="44020-128"> [Operator Procedures](./operator-procedures.md) </span></span>  
<span data-ttu-id="44020-129"> [Практическое руководство: определение параметра для процедуры](./how-to-define-a-parameter-for-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="44020-129"> [How to: Define a Parameter for a Procedure](./how-to-define-a-parameter-for-a-procedure.md) </span></span>  
<span data-ttu-id="44020-130"> [Передача аргументов по значению и по ссылке](./passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="44020-130"> [Passing Arguments by Value and by Reference](./passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="44020-131"> [Рекурсивные процедуры](./recursive-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="44020-131"> [Recursive Procedures](./recursive-procedures.md) </span></span>  
<span data-ttu-id="44020-132"> [Перегрузка процедур](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="44020-132"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="44020-133"> [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="44020-133"> [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="44020-134"> [Объектно-ориентированное программирование](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span><span class="sxs-lookup"><span data-stu-id="44020-134"> [Object-Oriented Programming](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)</span></span>
