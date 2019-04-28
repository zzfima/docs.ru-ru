---
title: Практическое руководство. Передача аргументов в процедуру (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 012ad8e6229958575030ee820a3b0b79cc50facc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863445"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="0cdda-102">Практическое руководство. Передача аргументов в процедуру (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cdda-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="0cdda-103">При вызове процедуры, необходимо выполнить имя процедуры со списком аргументов в скобках.</span><span class="sxs-lookup"><span data-stu-id="0cdda-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="0cdda-104">Необходимо указать аргумент, соответствующий каждому обязательному параметру в процедуре можно определить, и при необходимости можно указать аргументы для `Optional` параметров.</span><span class="sxs-lookup"><span data-stu-id="0cdda-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="0cdda-105">Если вы не предоставляете `Optional` параметра в вызове, необходимо включить запятую, чтобы отметить его место в списке аргументов, если указываются все последующие аргументы.</span><span class="sxs-lookup"><span data-stu-id="0cdda-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="0cdda-106">Если требуется передать аргумент типа данных отличается от соответствующего параметра, такие как `Byte` для `String`, можно задать для ключа проверки типов ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) для `Off`.</span><span class="sxs-lookup"><span data-stu-id="0cdda-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="0cdda-107">Если `Option Strict` является `On`, необходимо использовать либо расширяющих преобразований, либо ключевые слова явное преобразование.</span><span class="sxs-lookup"><span data-stu-id="0cdda-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="0cdda-108">Дополнительные сведения см. в разделе [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="0cdda-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="0cdda-109">Дополнительные сведения см. в разделе [параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="0cdda-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="0cdda-110">Чтобы передать один или несколько аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="0cdda-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="0cdda-111">В операторе вызова после имени процедуры со скобками.</span><span class="sxs-lookup"><span data-stu-id="0cdda-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="0cdda-112">В скобках, поместите список аргументов.</span><span class="sxs-lookup"><span data-stu-id="0cdda-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="0cdda-113">Включить аргумент для каждого обязательного параметра, определяемого этой процедурой, а аргументы необходимо разделять запятыми.</span><span class="sxs-lookup"><span data-stu-id="0cdda-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="0cdda-114">Убедитесь, что каждый аргумент является допустимое выражение, результатом вычисления которого преобразуется в тип процедуры определяются для соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="0cdda-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="0cdda-115">Если параметр определен как [необязательно](../../../../visual-basic/language-reference/modifiers/optional.md), можно включить его в списке аргументов или пропустите его.</span><span class="sxs-lookup"><span data-stu-id="0cdda-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="0cdda-116">Если он пропущен, процедура будет использовать значение по умолчанию, определенное для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="0cdda-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="0cdda-117">Если опустить аргумент для `Optional` параметр и в списке параметров после него имеется еще один параметр, можно пометить вместо пропущенный аргумент с лишнюю запятую в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="0cdda-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="0cdda-118">В следующем примере вызывается Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> функции.</span><span class="sxs-lookup"><span data-stu-id="0cdda-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="0cdda-119">В предыдущем примере передается обязательный первый аргумент, являющийся строку сообщения для отображения.</span><span class="sxs-lookup"><span data-stu-id="0cdda-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="0cdda-120">Он указывается аргумент для необязательный второй параметр, указывающий кнопки, отображаемые в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="0cdda-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="0cdda-121">Поскольку вызов не передается значение, `MsgBox` используется значение по умолчанию, `MsgBoxStyle.OKOnly`, отображающий только **ОК** кнопку.</span><span class="sxs-lookup"><span data-stu-id="0cdda-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="0cdda-122">Вторая запятая в списке аргументов отмечает место пропущенного второго параметра, а последняя строка передается третий необязательный параметр `MsgBox`, который является текст, отображаемый в заголовке окна.</span><span class="sxs-lookup"><span data-stu-id="0cdda-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cdda-123">См. также</span><span class="sxs-lookup"><span data-stu-id="0cdda-123">See also</span></span>

- [<span data-ttu-id="0cdda-124">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="0cdda-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="0cdda-125">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="0cdda-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="0cdda-126">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="0cdda-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="0cdda-127">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="0cdda-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="0cdda-128">Практическое руководство. Определение параметра для процедуры</span><span class="sxs-lookup"><span data-stu-id="0cdda-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="0cdda-129">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="0cdda-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="0cdda-130">Рекурсивные процедуры</span><span class="sxs-lookup"><span data-stu-id="0cdda-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="0cdda-131">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="0cdda-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="0cdda-132">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="0cdda-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- <span data-ttu-id="0cdda-133">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0cdda-133">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md)</span></span>
