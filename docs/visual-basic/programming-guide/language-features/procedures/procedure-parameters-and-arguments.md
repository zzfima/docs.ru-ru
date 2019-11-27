---
title: Параметры и аргументы процедуры
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: 7dfbbcb39cf7bb05c8a62a7a252e425f287c9a09
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352582"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="094a0-102">Параметры и аргументы процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="094a0-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="094a0-103">В большинстве случаев для процедуры требуются некоторые сведения о обстоятельствах, в которых она была вызвана.</span><span class="sxs-lookup"><span data-stu-id="094a0-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="094a0-104">Процедура, выполняющая повторяющиеся или общие задачи, использует разные сведения для каждого вызова.</span><span class="sxs-lookup"><span data-stu-id="094a0-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="094a0-105">Эти сведения состоят из переменных, констант и выражений, которые передаются в процедуру при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="094a0-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="094a0-106">*Параметр* представляет значение, которое процедура предполагает указать при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="094a0-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="094a0-107">В объявлении процедуры определяются ее параметры.</span><span class="sxs-lookup"><span data-stu-id="094a0-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="094a0-108">Можно определить процедуру без параметров, один параметр или несколько.</span><span class="sxs-lookup"><span data-stu-id="094a0-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="094a0-109">Часть определения процедуры, указывающая параметры, называется *списком параметров*.</span><span class="sxs-lookup"><span data-stu-id="094a0-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="094a0-110">*Аргумент* представляет значение, указываемое в параметре процедуры при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="094a0-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="094a0-111">Вызывающий код предоставляет аргументы при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="094a0-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="094a0-112">Часть вызова процедуры, указывающая аргументы, называется *списком аргументов*.</span><span class="sxs-lookup"><span data-stu-id="094a0-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="094a0-113">На следующем рисунке показан код, вызывающий процедуру, `safeSquareRoot` из двух различных мест.</span><span class="sxs-lookup"><span data-stu-id="094a0-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="094a0-114">Первый вызов передает значение переменной `x` (4,0) в параметр `number`, а возвращаемое значение в `root` (2,0) присваивается переменной `y`.</span><span class="sxs-lookup"><span data-stu-id="094a0-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="094a0-115">Второй вызов передает литеральное значение 9,0 в `number`и присваивает возвращаемое значение (3,0) переменной `z`.</span><span class="sxs-lookup"><span data-stu-id="094a0-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 ![Схема, показывающая передачу аргумента в параметр](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 <span data-ttu-id="094a0-117">Дополнительные сведения см. в разделе [различия между параметрами и аргументами](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="094a0-117">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="094a0-118">Тип данных параметра</span><span class="sxs-lookup"><span data-stu-id="094a0-118">Parameter Data Type</span></span>  
 <span data-ttu-id="094a0-119">Тип данных для параметра определяется с помощью предложения `As` в его объявлении.</span><span class="sxs-lookup"><span data-stu-id="094a0-119">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="094a0-120">Например, следующая функция принимает строку и целое число.</span><span class="sxs-lookup"><span data-stu-id="094a0-120">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 <span data-ttu-id="094a0-121">Если параметр проверки типов ([оператор Option строго](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `Off,` предложение `As` является необязательным, за исключением того, что если какой-либо параметр использует его, все параметры должны использовать его.</span><span class="sxs-lookup"><span data-stu-id="094a0-121">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="094a0-122">Если проверка типа `On`, то для всех параметров процедуры требуется предложение `As`.</span><span class="sxs-lookup"><span data-stu-id="094a0-122">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="094a0-123">Если вызывающий код должен предоставить аргумент с типом данных, отличным от того, который соответствует его параметру, например `Byte` параметру `String`, необходимо выполнить одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="094a0-123">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
- <span data-ttu-id="094a0-124">Указывайте только аргументы с типами данных, которые расширяются до типа данных параметра;</span><span class="sxs-lookup"><span data-stu-id="094a0-124">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
- <span data-ttu-id="094a0-125">Задайте `Option Strict Off`, чтобы разрешить неявные сужающие преобразования; ни</span><span class="sxs-lookup"><span data-stu-id="094a0-125">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
- <span data-ttu-id="094a0-126">Используйте ключевое слово преобразования для явного преобразования типа данных.</span><span class="sxs-lookup"><span data-stu-id="094a0-126">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="094a0-127">Параметры типа</span><span class="sxs-lookup"><span data-stu-id="094a0-127">Type Parameters</span></span>  
 <span data-ttu-id="094a0-128">*Универсальная процедура* также определяет один или несколько *параметров типа* в дополнение к обычным параметрам.</span><span class="sxs-lookup"><span data-stu-id="094a0-128">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="094a0-129">Универсальная процедура позволяет вызывающему коду передавать различные типы данных при каждом вызове процедуры, чтобы можно было адаптировать типы данных к требованиям каждого отдельного вызова.</span><span class="sxs-lookup"><span data-stu-id="094a0-129">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="094a0-130">См. раздел [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="094a0-130">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="094a0-131">См. также</span><span class="sxs-lookup"><span data-stu-id="094a0-131">See also</span></span>

- [<span data-ttu-id="094a0-132">Процедуры</span><span class="sxs-lookup"><span data-stu-id="094a0-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="094a0-133">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="094a0-133">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="094a0-134">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="094a0-134">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="094a0-135">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="094a0-135">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="094a0-136">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="094a0-136">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="094a0-137">Практическое руководство. Определение параметра для процедуры</span><span class="sxs-lookup"><span data-stu-id="094a0-137">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="094a0-138">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="094a0-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="094a0-139">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="094a0-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="094a0-140">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="094a0-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="094a0-141">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="094a0-141">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
