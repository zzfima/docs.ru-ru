---
title: "Передача аргументов по позиции и по имени (Visual Basic)"
ms.custom: 
ms.date: 02/01/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13f5e5a8da6a899d4920a25b250ca88b2a21f559
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2018
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="a9ffd-102">Передача аргументов по позиции и по имени (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9ffd-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="a9ffd-103">При вызове `Sub` или `Function` процедуры, можно передать аргументы *по позиции* — в том порядке, в котором они отображаются в определении процедуры, или их можно передать *по имени*, без учета.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="a9ffd-104">Если аргумент передается по имени, укажите его объявленное имя, за которым следует двоеточие и знак равенства (`:=`), а затем значение аргумента.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="a9ffd-105">Можно передать аргументы в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="a9ffd-106">Например, следующая `Sub` процедура принимает три аргумента:</span><span class="sxs-lookup"><span data-stu-id="a9ffd-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="a9ffd-107">При вызове этой процедуры можно указать аргументов по позиции, по имени или с помощью их сочетании.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="a9ffd-108">Передача аргументов по позиции</span><span class="sxs-lookup"><span data-stu-id="a9ffd-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="a9ffd-109">Можно вызвать `Display` метод с ее аргументы, передаваемые по позиции и разделенными запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a9ffd-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="a9ffd-110">Если необязательный аргумент в списке позиционный аргумент опущен, необходимо отметить его место запятой.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="a9ffd-111">В следующем примере вызывается `Display` метод без `age` аргумент:</span><span class="sxs-lookup"><span data-stu-id="a9ffd-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="a9ffd-112">Передача аргументов по имени</span><span class="sxs-lookup"><span data-stu-id="a9ffd-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="a9ffd-113">Кроме того, можно вызвать метод `Display` с аргументами, передаваемыми по имени и также разделенными запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a9ffd-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="a9ffd-114">Передача аргументов по имени таким образом особенно полезна при вызове процедуры, которая имеет более чем один необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="a9ffd-115">Если аргументы передаются по имени, не имеют несколько запятых подряд для опускать позиционные аргументы.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="a9ffd-116">Передача аргументов по имени делает его более удобным для отслеживания какие аргументы заданы, а какие пропущены.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="a9ffd-117">Смешивание аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="a9ffd-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="a9ffd-118">Аргументов по позиции и по имени в одном вызове процедуры, можно указать, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="a9ffd-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="a9ffd-119">В приведенном выше примере дополнительная запятая, не обязательно отмечающая пропущенный аргумент `age` аргумент, поскольку `birth` передается по имени.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="a9ffd-120">В версиях Visual Basic до 15,5 Если аргументы перепутаны позиции и имя, это позиционные аргументы должны быть первой.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="a9ffd-121">После аргумента, передаваемого по имени, все остальные аргументы все передается по имени.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="a9ffd-122">Например, в следующем вызове `Display` метод отображает ошибку компилятора [BC30241: ожидается аргумент с именем](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="a9ffd-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="a9ffd-123">Начиная с Visual Basic 15,5 позиционные аргументы для выполнения именованные аргументы окончания позиционные аргументы находятся в правильном положении.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="a9ffd-124">При компиляции в Visual Basic 15,5, предыдущего вызова `Display` метод успешно компилируется и больше не создает ошибку компилятора [BC30241](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="a9ffd-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="a9ffd-125">Эта возможность комбинировать и сопоставлять именованных и позиционных аргументов в любом порядке особенно полезен, если вы хотите использовать именованный аргумент, чтобы сделать код более удобочитаемым.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="a9ffd-126">Например, следующая `Person` конструктору класса требуется два аргумента типа `Person`, которые могут быть `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="a9ffd-127">С помощью смешанного именованных и позиционных аргументов, снимите помогает сделать назначение кода, когда значение `father` и `mother` аргументов является `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="a9ffd-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="a9ffd-128">Чтобы выполнить позиционные аргументы с именованными аргументами, необходимо добавить следующий элемент в проект Visual Basic (\*.vbproj) файла:</span><span class="sxs-lookup"><span data-stu-id="a9ffd-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="a9ffd-129">Ограничения при передаче аргументов по имени</span><span class="sxs-lookup"><span data-stu-id="a9ffd-129">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="a9ffd-130">Аргументы невозможно передать по имени, чтобы избежать ввода обязательных аргументов.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-130">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="a9ffd-131">Можно опустить только необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-131">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="a9ffd-132">Невозможно передать массив параметров по имени.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-132">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="a9ffd-133">Это так, как при вызове процедуры, необходимо указать неопределенное число разделенных запятыми аргументов для массива параметров, и компилятор не может связывать несколько аргументов с одним именем.</span><span class="sxs-lookup"><span data-stu-id="a9ffd-133">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9ffd-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a9ffd-134">See Also</span></span>  
 [<span data-ttu-id="a9ffd-135">Процедуры</span><span class="sxs-lookup"><span data-stu-id="a9ffd-135">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="a9ffd-136">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="a9ffd-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="a9ffd-137">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="a9ffd-137">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="a9ffd-138">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="a9ffd-138">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="a9ffd-139">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="a9ffd-139">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="a9ffd-140">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="a9ffd-140">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="a9ffd-141">Необязательный</span><span class="sxs-lookup"><span data-stu-id="a9ffd-141">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="a9ffd-142">ParamArray</span><span class="sxs-lookup"><span data-stu-id="a9ffd-142">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
