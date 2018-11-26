---
title: Передача аргументов по позиции и по имени (Visual Basic)
ms.date: 02/01/2018
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
ms.openlocfilehash: bdaa0351e288b85a3e35818c0f53ef4d772932e5
ms.sourcegitcommit: 35316b768394e56087483cde93f854ba607b63bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2018
ms.locfileid: "52296455"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="8cc79-102">Передача аргументов по позиции и по имени (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8cc79-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>
<span data-ttu-id="8cc79-103">При вызове `Sub` или `Function` процедуру, вы можете передавать аргументы *по позиции* — в порядке, в котором они появляются в определении процедуры, или их можно передать *по имени*, без учета.</span><span class="sxs-lookup"><span data-stu-id="8cc79-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>  
  
 <span data-ttu-id="8cc79-104">Когда аргумент передается по имени, укажите его объявленное имя, за которым следует двоеточие и знак равенства (`:=`), а затем, если значение аргумента.</span><span class="sxs-lookup"><span data-stu-id="8cc79-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="8cc79-105">Вы можете указать аргументы в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="8cc79-105">You can supply named arguments in any order.</span></span>  
  
 <span data-ttu-id="8cc79-106">Например, следующая `Sub` процедура принимает три аргумента:</span><span class="sxs-lookup"><span data-stu-id="8cc79-106">For example, the following `Sub` procedure takes three arguments:</span></span>  
  
 [!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]  
  
 <span data-ttu-id="8cc79-107">При вызове этой процедуры можно указать аргументов по позиции, по имени или с помощью их комбинацией.</span><span class="sxs-lookup"><span data-stu-id="8cc79-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>  
  
## <a name="passing-arguments-by-position"></a><span data-ttu-id="8cc79-108">Передача аргументов по позиции</span><span class="sxs-lookup"><span data-stu-id="8cc79-108">Passing Arguments by Position</span></span>  
 <span data-ttu-id="8cc79-109">Вы можете вызвать `Display` метод с аргументов по позиции и разделенными запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8cc79-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)] 
  
 <span data-ttu-id="8cc79-110">Если опустить необязательный аргумент в список позиционных аргументов, должен выполнять вместо него запятую.</span><span class="sxs-lookup"><span data-stu-id="8cc79-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="8cc79-111">В следующем примере вызывается `Display` метод без `age` аргумент:</span><span class="sxs-lookup"><span data-stu-id="8cc79-111">The following example calls the `Display` method without the `age` argument:</span></span>  
  
[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)] 
  
## <a name="passing-arguments-by-name"></a><span data-ttu-id="8cc79-112">Передача аргументов по имени</span><span class="sxs-lookup"><span data-stu-id="8cc79-112">Passing Arguments by Name</span></span>  
 <span data-ttu-id="8cc79-113">Кроме того, можно вызвать `Display` с аргументами, передаваемыми по имени, также разделенными запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8cc79-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>  
  
[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)] 

 <span data-ttu-id="8cc79-114">Передача аргументов по имени, таким образом особенно полезна при вызове процедуры, которая имеет более чем один необязательный аргумент.</span><span class="sxs-lookup"><span data-stu-id="8cc79-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="8cc79-115">Если аргументы по имени, вам не нужно использовать идущие подряд запятые позволяет опускать позиционные аргументы.</span><span class="sxs-lookup"><span data-stu-id="8cc79-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="8cc79-116">Передача аргументов по имени также упрощает для отслеживания какие аргументы, передаваемые и пропуск каких из них.</span><span class="sxs-lookup"><span data-stu-id="8cc79-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>  
  
## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="8cc79-117">Сочетание аргументов по позиции и по имени</span><span class="sxs-lookup"><span data-stu-id="8cc79-117">Mixing Arguments by Position and by Name</span></span>  

<span data-ttu-id="8cc79-118">Аргументов по позиции и по имени в одном вызове процедуры, можно указать, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="8cc79-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>  
  
[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)] 
  
 <span data-ttu-id="8cc79-119">В приведенном выше примере не лишнюю запятую необходим отмечающая пропущенный аргумент `age` аргумента, так как `birth` передается по имени.</span><span class="sxs-lookup"><span data-stu-id="8cc79-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>  
  
<span data-ttu-id="8cc79-120">В версиях Visual Basic до версии 15.5 Если аргументы перепутаны позиции и имя, позиционные аргументы должны быть первой.</span><span class="sxs-lookup"><span data-stu-id="8cc79-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="8cc79-121">Когда необходимо указать аргумент по имени, все остальные аргументы должны все передаваться по имени.</span><span class="sxs-lookup"><span data-stu-id="8cc79-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="8cc79-122">Например, следующий вызов `Display` метод отображает ошибку компилятора [BC30241: ожидается именованный аргумент](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="8cc79-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)] 

<span data-ttu-id="8cc79-123">Начиная с Visual Basic 15.5, позиционные аргументы можно выполнить именованных аргументов, если конечный позиционные аргументы в правильном положении.</span><span class="sxs-lookup"><span data-stu-id="8cc79-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="8cc79-124">При компиляции в Visual Basic 15.5, предыдущего вызова `Display` метод успешно компилируется и больше не создает ошибку компилятора [BC30241](../../../misc/bc30241.md).</span><span class="sxs-lookup"><span data-stu-id="8cc79-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>  

<span data-ttu-id="8cc79-125">Эта возможность смешивать и сочетать именованных и позиционных аргументов в любом порядке особенно полезна в случаях, когда вы хотите использовать именованный аргумент, чтобы сделать код более удобочитаемым.</span><span class="sxs-lookup"><span data-stu-id="8cc79-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="8cc79-126">Например, следующая `Person` конструктору класса требуется два аргумента типа `Person`, каждый из которых может быть `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8cc79-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span> 

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)] 

<span data-ttu-id="8cc79-127">С помощью смешанных именованных и позиционных аргументов, упрощает назначение кода очистки, когда значение `father` и `mother` аргументов является `Nothing`:</span><span class="sxs-lookup"><span data-stu-id="8cc79-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)] 

<span data-ttu-id="8cc79-128">Чтобы следовать за позиционными аргументами с помощью именованных аргументов, необходимо добавить следующий элемент в проект Visual Basic (\*.vbproj) файла:</span><span class="sxs-lookup"><span data-stu-id="8cc79-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="8cc79-129">Дополнительные сведения см. в разделе [параметр версии языка Visual Basic](../../../language-reference/configure-language-version.md).</span><span class="sxs-lookup"><span data-stu-id="8cc79-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="8cc79-130">Ограничения при передаче аргументов по имени</span><span class="sxs-lookup"><span data-stu-id="8cc79-130">Restrictions on Supplying Arguments by Name</span></span>  

<span data-ttu-id="8cc79-131">Нельзя передавать аргументы по имени, не следует вводить необходимые аргументы.</span><span class="sxs-lookup"><span data-stu-id="8cc79-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="8cc79-132">Можно опустить только необязательные аргументы.</span><span class="sxs-lookup"><span data-stu-id="8cc79-132">You can omit only the optional arguments.</span></span>  
  
<span data-ttu-id="8cc79-133">Невозможно передать массив параметров по имени.</span><span class="sxs-lookup"><span data-stu-id="8cc79-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="8cc79-134">Это потому, что при вызове процедуры, вы предоставляете неопределенное число разделенных запятыми аргументов для массива параметров, а компилятор не может связать более одного аргумента с одним именем.</span><span class="sxs-lookup"><span data-stu-id="8cc79-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cc79-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8cc79-135">See Also</span></span>  
 [<span data-ttu-id="8cc79-136">Процедуры</span><span class="sxs-lookup"><span data-stu-id="8cc79-136">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="8cc79-137">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="8cc79-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="8cc79-138">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="8cc79-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="8cc79-139">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="8cc79-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="8cc79-140">Необязательные параметры</span><span class="sxs-lookup"><span data-stu-id="8cc79-140">Optional Parameters</span></span>](./optional-parameters.md)  
 [<span data-ttu-id="8cc79-141">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="8cc79-141">Parameter Arrays</span></span>](./parameter-arrays.md)  
 [<span data-ttu-id="8cc79-142">Необязательный</span><span class="sxs-lookup"><span data-stu-id="8cc79-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)  
 [<span data-ttu-id="8cc79-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="8cc79-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
