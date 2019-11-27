---
title: Практическое руководство. Передача аргументов в процедуру
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
ms.openlocfilehash: 0267eed7c145988d61de715fd661bd4906d8d57d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344846"
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a><span data-ttu-id="9c276-102">Практическое руководство. Передача аргументов в процедуру (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c276-102">How to: Pass Arguments to a Procedure (Visual Basic)</span></span>
<span data-ttu-id="9c276-103">При вызове процедуры необходимо следовать имени процедуры со списком аргументов в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="9c276-103">When you call a procedure, you follow the procedure name with an argument list in parentheses.</span></span> <span data-ttu-id="9c276-104">Укажите аргумент, соответствующий каждому обязательному параметру, определяемому процедурой, и при необходимости можно указать аргументы для параметров `Optional`.</span><span class="sxs-lookup"><span data-stu-id="9c276-104">You supply an argument corresponding to every required parameter the procedure defines, and you can optionally supply arguments to the `Optional` parameters.</span></span> <span data-ttu-id="9c276-105">Если в вызове не указан параметр `Optional`, необходимо включить запятую, чтобы пометить ее место в списке аргументов, если вы предоставляете последующие аргументы.</span><span class="sxs-lookup"><span data-stu-id="9c276-105">If you do not supply an `Optional` parameter in the call, you must include a comma to mark its place in the argument list if you are supplying any subsequent arguments.</span></span>  
  
 <span data-ttu-id="9c276-106">Если предполагается передать аргумент типа данных, отличный от того, который соответствует его параметру, например `Byte` для `String`, можно установить для параметра проверки типов ([оператор Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) значение `Off`.</span><span class="sxs-lookup"><span data-stu-id="9c276-106">If you intend to pass an argument of a data type different from that of its corresponding parameter, such as `Byte` to `String`, you can set the type-checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) to `Off`.</span></span> <span data-ttu-id="9c276-107">Если `Option Strict` `On`, необходимо использовать либо расширяющие преобразования, либо ключевые слова явного преобразования.</span><span class="sxs-lookup"><span data-stu-id="9c276-107">If `Option Strict` is `On`, you must use either widening conversions or explicit conversion keywords.</span></span> <span data-ttu-id="9c276-108">Дополнительные сведения см. в разделе [расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и [функции преобразования типов](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="9c276-108">For more information, see [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>  
  
 <span data-ttu-id="9c276-109">Дополнительные сведения см. в разделе [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="9c276-109">For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).</span></span>  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a><span data-ttu-id="9c276-110">Передача одного или нескольких аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="9c276-110">To pass one or more arguments to a procedure</span></span>  
  
1. <span data-ttu-id="9c276-111">В операторе вызова используйте имя процедуры с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="9c276-111">In the calling statement, follow the procedure name with parentheses.</span></span>  
  
2. <span data-ttu-id="9c276-112">Внутри круглых скобок вставьте список аргументов.</span><span class="sxs-lookup"><span data-stu-id="9c276-112">Inside the parentheses, put an argument list.</span></span> <span data-ttu-id="9c276-113">Включите аргумент для каждого обязательного параметра, определяемого процедурой, и разделите аргументы запятыми.</span><span class="sxs-lookup"><span data-stu-id="9c276-113">Include an argument for each required parameter the procedure defines, and separate the arguments with commas.</span></span>  
  
3. <span data-ttu-id="9c276-114">Убедитесь, что каждый аргумент является допустимым выражением, результатом которого является тип данных, преобразуемый в тип, определяемый процедурой для соответствующего параметра.</span><span class="sxs-lookup"><span data-stu-id="9c276-114">Make sure each argument is a valid expression that evaluates to a data type convertible to the type the procedure defines for the corresponding parameter.</span></span>  
  
4. <span data-ttu-id="9c276-115">Если параметр определен как [необязательный](../../../../visual-basic/language-reference/modifiers/optional.md), его можно включить в список аргументов или опустить.</span><span class="sxs-lookup"><span data-stu-id="9c276-115">If a parameter is defined as [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), you can either include it in the argument list or omit it.</span></span> <span data-ttu-id="9c276-116">Если опустить его, процедура использует значение по умолчанию, определенное для этого параметра.</span><span class="sxs-lookup"><span data-stu-id="9c276-116">If you omit it, the procedure uses the default value defined for that parameter.</span></span>  
  
5. <span data-ttu-id="9c276-117">Если опустить аргумент для параметра `Optional` и после него в списке параметров есть другой параметр, можно пометить место пропущенного аргумента на дополнительную запятую в списке аргументов.</span><span class="sxs-lookup"><span data-stu-id="9c276-117">If you omit an argument for an `Optional` parameter and there is another parameter after it in the parameter list, you can mark the place of the omitted argument by an extra comma in the argument list.</span></span>  
  
     <span data-ttu-id="9c276-118">В следующем примере вызывается функция Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c276-118">The following example calls the Visual Basic <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> function.</span></span>  
  
     [!code-vb[VbVbcnProcedures#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#34)]  
  
     <span data-ttu-id="9c276-119">В предыдущем примере предоставляется обязательный первый аргумент, который представляет собой отображаемую строку сообщения.</span><span class="sxs-lookup"><span data-stu-id="9c276-119">The preceding example supplies the required first argument, which is the message string to be displayed.</span></span> <span data-ttu-id="9c276-120">Он опускает аргумент для необязательного второго параметра, который указывает кнопки, отображаемые в окне сообщения.</span><span class="sxs-lookup"><span data-stu-id="9c276-120">It omits an argument for the optional second parameter, which specifies the buttons to be displayed on the message box.</span></span> <span data-ttu-id="9c276-121">Поскольку вызов не предоставляет значение, `MsgBox` использует значение по умолчанию `MsgBoxStyle.OKOnly`, которое отображает только кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="9c276-121">Because the call does not supply a value, `MsgBox` uses the default value, `MsgBoxStyle.OKOnly`, which displays only an **OK** button.</span></span>  
  
     <span data-ttu-id="9c276-122">Вторая запятая в списке аргументов отмечает место пропущенного второго аргумента, а последняя строка передается необязательному третьему параметру `MsgBox`, который является текстом, отображаемым в заголовке окна.</span><span class="sxs-lookup"><span data-stu-id="9c276-122">The second comma in the argument list marks the place of the omitted second argument, and the last string is passed to the optional third parameter of `MsgBox`, which is the text to be displayed in the title bar.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c276-123">См. также</span><span class="sxs-lookup"><span data-stu-id="9c276-123">See also</span></span>

- [<span data-ttu-id="9c276-124">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="9c276-124">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="9c276-125">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="9c276-125">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="9c276-126">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="9c276-126">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="9c276-127">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="9c276-127">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="9c276-128">Практическое руководство. Определение параметра для процедуры</span><span class="sxs-lookup"><span data-stu-id="9c276-128">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="9c276-129">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="9c276-129">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="9c276-130">Рекурсивные процедуры</span><span class="sxs-lookup"><span data-stu-id="9c276-130">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="9c276-131">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="9c276-131">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="9c276-132">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="9c276-132">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- <span data-ttu-id="9c276-133">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md) (Объектно-ориентированное программирование на языке Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9c276-133">[Object-Oriented Programming (Visual Basic)](../../concepts/object-oriented-programming.md)</span></span>
