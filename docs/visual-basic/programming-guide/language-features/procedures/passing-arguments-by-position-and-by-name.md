---
title: "Передача аргументов по позиции и по имени (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 164f69fcf23049441a0acbe05058c792d5363a03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="70786-102">Передача аргументов по позиции и по имени (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="70786-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="70786-103">При вызове `Sub` или `Function` процедуры, можно передать аргументы *по позиции* — в том порядке, в котором они отображаются в определении процедуры, или их можно передать *по имени*, без учета.</span><span class="sxs-lookup"><span data-stu-id="70786-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="70786-104">Если аргумент передается по имени, укажите его объявленное имя, за которым следует двоеточие и знак равенства (`:=`), а затем значение аргумента.</span><span class="sxs-lookup"><span data-stu-id="70786-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="70786-105">Можно передать аргументы в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="70786-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="70786-106">Например, следующая `Sub` процедура принимает три аргумента:</span><span class="sxs-lookup"><span data-stu-id="70786-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[VbVbcnProcedures#41](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_1.vb)]  
  
 <span data-ttu-id="70786-107">При вызове этой процедуры можно указать аргументов по позиции, по имени или с помощью их сочетании.</span><span class="sxs-lookup"><span data-stu-id="70786-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="70786-108">Передача аргументов по позиции</span><span class="sxs-lookup"><span data-stu-id="70786-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="70786-109">Можно вызвать процедуру `studentInfo` с передачей аргументов по позиции, разделенными запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="70786-109">You can call the procedure `studentInfo` with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#42](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_2.vb)]  
  
 <span data-ttu-id="70786-110">Если необязательный аргумент в списке позиционный аргумент опущен, необходимо отметить его место запятой.</span><span class="sxs-lookup"><span data-stu-id="70786-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="70786-111">В следующем примере вызывается `studentInfo` без `age` аргумент:</span><span class="sxs-lookup"><span data-stu-id="70786-111">The following example calls `studentInfo` without the `age` argument:</span></span>  
  
 [!code-vb[VbVbcnProcedures#43](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_3.vb)]  
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="70786-112">Передача аргументов по имени</span><span class="sxs-lookup"><span data-stu-id="70786-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="70786-113">Кроме того, можно вызвать метод `studentInfo` с аргументами, передаваемыми по имени и также разделенными запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="70786-113">Alternatively, you can call `studentInfo` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#44](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_4.vb)]  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="70786-114">Смешивание аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="70786-114">Mixing Arguments by Position and by Name</span></span>  
 <span data-ttu-id="70786-115">Аргументов по позиции и по имени в одном вызове процедуры, можно указать, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="70786-115">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
 [!code-vb[VbVbcnProcedures#45](./codesnippet/VisualBasic/passing-arguments-by-position-and-by-name_5.vb)]  
  
 <span data-ttu-id="70786-116">В приведенном выше примере дополнительная запятая, не обязательно отмечающая пропущенный аргумент `age` аргумент, поскольку `birth` передается по имени.</span><span class="sxs-lookup"><span data-stu-id="70786-116">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
 <span data-ttu-id="70786-117">Если аргументы перепутаны позиции и имя, это позиционные аргументы должны быть первой.</span><span class="sxs-lookup"><span data-stu-id="70786-117">When you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="70786-118">После аргумента, передаваемого по имени, все последующие аргументы должны быть по имени.</span><span class="sxs-lookup"><span data-stu-id="70786-118">Once you supply an argument by name, the remaining arguments must all be by name.</span></span>  
  
## <a name="supplying-optional-arguments-by-name"></a><span data-ttu-id="70786-119">Задание необязательных аргументов по имени</span><span class="sxs-lookup"><span data-stu-id="70786-119">Supplying Optional Arguments by Name</span></span>  
 <span data-ttu-id="70786-120">Передача аргументов по имени особенно удобна при вызове процедуры, которая имеет более чем один необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="70786-120">Passing arguments by name is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="70786-121">Если аргументы передаются по имени, не имеют несколько запятых подряд для опускать позиционные аргументы.</span><span class="sxs-lookup"><span data-stu-id="70786-121">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="70786-122">Передача аргументов по имени делает его более удобным для отслеживания какие аргументы заданы, а какие пропущены.</span><span class="sxs-lookup"><span data-stu-id="70786-122">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="70786-123">Ограничения при передаче аргументов по имени</span><span class="sxs-lookup"><span data-stu-id="70786-123">Restrictions on Supplying Arguments by Name</span></span>  
 <span data-ttu-id="70786-124">Аргументы невозможно передать по имени, чтобы избежать ввода обязательных аргументов.</span><span class="sxs-lookup"><span data-stu-id="70786-124">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="70786-125">Можно опустить только необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="70786-125">You can omit only the optional arguments.</span></span>  
  
 <span data-ttu-id="70786-126">Невозможно передать массив параметров по имени.</span><span class="sxs-lookup"><span data-stu-id="70786-126">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="70786-127">Это так, как при вызове процедуры, необходимо указать неопределенное число разделенных запятыми аргументов для массива параметров, и компилятор не может связывать несколько аргументов с одним именем.</span><span class="sxs-lookup"><span data-stu-id="70786-127">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70786-128">См. также</span><span class="sxs-lookup"><span data-stu-id="70786-128">See Also</span></span>  
 [<span data-ttu-id="70786-129">Процедуры</span><span class="sxs-lookup"><span data-stu-id="70786-129">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="70786-130">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="70786-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="70786-131">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="70786-131">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="70786-132">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="70786-132">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="70786-133">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="70786-133">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="70786-134">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="70786-134">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="70786-135">Необязательный</span><span class="sxs-lookup"><span data-stu-id="70786-135">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="70786-136">ParamArray</span><span class="sxs-lookup"><span data-stu-id="70786-136">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
