---
title: "Параметры и аргументы процедуры (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 726667950cfb227a0359bd6238c202883561749c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="d2c81-102">Параметры и аргументы процедуры (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d2c81-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="d2c81-103">В большинстве случаев процедуре требуется некоторая информация о ситуациях, в которых она была вызвана.</span><span class="sxs-lookup"><span data-stu-id="d2c81-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="d2c81-104">Процедура, которая выполняет повторяющуюся задачу использует различные сведения для каждого вызова.</span><span class="sxs-lookup"><span data-stu-id="d2c81-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="d2c81-105">Эта информация состоит из переменных, констант и выражений, которые передаются процедуре при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="d2c81-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="d2c81-106">Объект *параметр* представляет значение, которое процедура необходимо указать при ее вызове.</span><span class="sxs-lookup"><span data-stu-id="d2c81-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="d2c81-107">Объявление процедуры определяет его параметры.</span><span class="sxs-lookup"><span data-stu-id="d2c81-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="d2c81-108">Можно определить процедуру без параметров, один параметр или несколько.</span><span class="sxs-lookup"><span data-stu-id="d2c81-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="d2c81-109">Часть определения процедуры, которое указывает параметры, называется *список параметров*.</span><span class="sxs-lookup"><span data-stu-id="d2c81-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="d2c81-110">*Аргумент* представляет значение, указываемое в параметрах процедуры при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="d2c81-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="d2c81-111">Вызывающий код не предоставляет аргументы при вызове процедуры.</span><span class="sxs-lookup"><span data-stu-id="d2c81-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="d2c81-112">Часть вызова процедуры, которая определяет аргументы, называется *список аргументов*.</span><span class="sxs-lookup"><span data-stu-id="d2c81-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="d2c81-113">На следующем рисунке показан код вызова процедуры `safeSquareRoot` из двух различных местах.</span><span class="sxs-lookup"><span data-stu-id="d2c81-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="d2c81-114">Первый вызов передает значение переменной `x` (4.0) в параметр `number`и возвращаемое значение в `root` (2.0) присваивается переменной `y`.</span><span class="sxs-lookup"><span data-stu-id="d2c81-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="d2c81-115">Второй вызов передает значение литерала 9.0 в `number`и присваивает возвращаемое значение (3.0) переменной `z`.</span><span class="sxs-lookup"><span data-stu-id="d2c81-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 <span data-ttu-id="d2c81-116">![Схема графика передачи аргумента в параметр](./media/parametersargue.gif "ParametersArgue")</span><span class="sxs-lookup"><span data-stu-id="d2c81-116">![Graphic diagram of passing argument to parameter](./media/parametersargue.gif "ParametersArgue")</span></span>  
<span data-ttu-id="d2c81-117">Передача аргумента в параметр</span><span class="sxs-lookup"><span data-stu-id="d2c81-117">Passing an argument to a parameter</span></span>  
  
 <span data-ttu-id="d2c81-118">Дополнительные сведения см. в разделе [различия между параметрами и аргументами](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="d2c81-118">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="d2c81-119">Тип данных параметра</span><span class="sxs-lookup"><span data-stu-id="d2c81-119">Parameter Data Type</span></span>  
 <span data-ttu-id="d2c81-120">Определить тип данных для параметра с помощью `As` предложение в его объявлении.</span><span class="sxs-lookup"><span data-stu-id="d2c81-120">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="d2c81-121">Например следующая функция принимает строку и целое число.</span><span class="sxs-lookup"><span data-stu-id="d2c81-121">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](./codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 <span data-ttu-id="d2c81-122">Если переключатель проверки типа ([оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) является `Off,` `As` предложение необязательно, за исключением того, если любой из параметров использует его, его необходимо использовать все параметры.</span><span class="sxs-lookup"><span data-stu-id="d2c81-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="d2c81-123">Если проверка типов не `On`, `As` предложение является обязательным для всех параметров процедуры.</span><span class="sxs-lookup"><span data-stu-id="d2c81-123">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="d2c81-124">Если вызывающий код ожидает указания аргумента с типом данных, отличному от соответствующего параметра, такие как `Byte` для `String` параметра, он должен выполнить одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d2c81-124">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
-   <span data-ttu-id="d2c81-125">Указать только аргументы с типами данных, которые расширяются до типа данных параметра;</span><span class="sxs-lookup"><span data-stu-id="d2c81-125">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
-   <span data-ttu-id="d2c81-126">Задать `Option Strict Off` чтобы разрешить неявные сужающие преобразования; или</span><span class="sxs-lookup"><span data-stu-id="d2c81-126">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
-   <span data-ttu-id="d2c81-127">Используйте ключевое слово преобразования для явного преобразования типа данных.</span><span class="sxs-lookup"><span data-stu-id="d2c81-127">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="d2c81-128">Параметры типа</span><span class="sxs-lookup"><span data-stu-id="d2c81-128">Type Parameters</span></span>  
 <span data-ttu-id="d2c81-129">Объект *универсальной процедуры* также определяет один или несколько *параметры типа* в дополнение к его обычным параметрам.</span><span class="sxs-lookup"><span data-stu-id="d2c81-129">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="d2c81-130">Универсальная процедура позволяет вызывающему коду для передачи различных типов данных при каждом вызове процедуры, поэтому его можно адаптировать типы данных для каждого отдельного вызова требования.</span><span class="sxs-lookup"><span data-stu-id="d2c81-130">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="d2c81-131">См. раздел [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="d2c81-131">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2c81-132">См. также</span><span class="sxs-lookup"><span data-stu-id="d2c81-132">See Also</span></span>  
 [<span data-ttu-id="d2c81-133">Процедуры</span><span class="sxs-lookup"><span data-stu-id="d2c81-133">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="d2c81-134">Подпрограммы</span><span class="sxs-lookup"><span data-stu-id="d2c81-134">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="d2c81-135">Процедуры функций</span><span class="sxs-lookup"><span data-stu-id="d2c81-135">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="d2c81-136">Процедуры свойств</span><span class="sxs-lookup"><span data-stu-id="d2c81-136">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="d2c81-137">Процедуры операторов</span><span class="sxs-lookup"><span data-stu-id="d2c81-137">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="d2c81-138">Практическое руководство. Определение параметра для процедуры</span><span class="sxs-lookup"><span data-stu-id="d2c81-138">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="d2c81-139">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="d2c81-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="d2c81-140">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="d2c81-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="d2c81-141">Перегрузка процедур</span><span class="sxs-lookup"><span data-stu-id="d2c81-141">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="d2c81-142">Преобразования типов в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d2c81-142">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
