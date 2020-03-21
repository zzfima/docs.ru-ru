---
title: Передача аргументов по позиции и по имени
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
ms.openlocfilehash: b6588335f7634cc87a9fc14cbfc4ba80baad1abb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401439"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="3214b-102">Передача аргументов по позиции и по имени (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3214b-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>

<span data-ttu-id="3214b-103">Когда вы `Sub` вызываете или `Function` процедуру, вы можете пройти аргументы *по позиции* - в порядке, в котором они появляются в определении процедуры - или вы можете передать их по *имени,* без учета позиции.</span><span class="sxs-lookup"><span data-stu-id="3214b-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>

<span data-ttu-id="3214b-104">Когда вы передаете аргумент по имени, вы указываете заявленное имя`:=`аргумента с последующим двоеточием и равным знаком (), за которым следует значение аргумента.</span><span class="sxs-lookup"><span data-stu-id="3214b-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="3214b-105">Вы можете предоставить именованные аргументы в любом порядке.</span><span class="sxs-lookup"><span data-stu-id="3214b-105">You can supply named arguments in any order.</span></span>

<span data-ttu-id="3214b-106">Например, следующая `Sub` процедура требует трех аргументов:</span><span class="sxs-lookup"><span data-stu-id="3214b-106">For example, the following `Sub` procedure takes three arguments:</span></span>

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

<span data-ttu-id="3214b-107">Когда вы называете эту процедуру, вы можете предоставить аргументы по позиции, по имени, или с помощью смеси обоих.</span><span class="sxs-lookup"><span data-stu-id="3214b-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>

## <a name="passing-arguments-by-position"></a><span data-ttu-id="3214b-108">Прохождение Аргументы по позиции</span><span class="sxs-lookup"><span data-stu-id="3214b-108">Passing Arguments by Position</span></span>

<span data-ttu-id="3214b-109">Вы можете `Display` назвать метод с его аргументами, передаваемыми по позиции и делимитировамыми запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3214b-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

<span data-ttu-id="3214b-110">Если вы не опускаете факультативный аргумент в позиционном списке аргументов, вы должны занять его место с запятой.</span><span class="sxs-lookup"><span data-stu-id="3214b-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="3214b-111">Следующий пример `Display` называет метод `age` без аргумента:</span><span class="sxs-lookup"><span data-stu-id="3214b-111">The following example calls the `Display` method without the `age` argument:</span></span>

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a><span data-ttu-id="3214b-112">Передача Аргументов по имени</span><span class="sxs-lookup"><span data-stu-id="3214b-112">Passing Arguments by Name</span></span>

<span data-ttu-id="3214b-113">Кроме того, вы `Display` можете позвонить с аргументами, передаваемыми по имени, также делегированными запятыми, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3214b-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

<span data-ttu-id="3214b-114">Передача аргументов по имени таким образом особенно полезна, когда вы называете процедуру, которая имеет более одного факультативного аргумента.</span><span class="sxs-lookup"><span data-stu-id="3214b-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="3214b-115">Если вы поставляете аргументы по имени, вам не придется использовать последовательные запятые для обозначения недостающих позиционных аргументов.</span><span class="sxs-lookup"><span data-stu-id="3214b-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="3214b-116">Передача аргументов по имени также облегчает отслеживание того, какие аргументы вы проходите, а какие вы опускаете.</span><span class="sxs-lookup"><span data-stu-id="3214b-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>

## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="3214b-117">Смешивание аргументов по позиции и имени</span><span class="sxs-lookup"><span data-stu-id="3214b-117">Mixing Arguments by Position and by Name</span></span>

<span data-ttu-id="3214b-118">Аргументы можно предоставить как по позиции, так и по имени в одном вызове процедуры, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="3214b-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

<span data-ttu-id="3214b-119">В предыдущем примере для удержания места опущенного `age` аргумента не требуется дополнительная запятая, так как `birth` она передается по имени.</span><span class="sxs-lookup"><span data-stu-id="3214b-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>

<span data-ttu-id="3214b-120">В версиях Visual Basic до 15.5, когда вы поставляете аргументы по смеси позиции и имени, позиционные аргументы должны быть на первом месте.</span><span class="sxs-lookup"><span data-stu-id="3214b-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="3214b-121">Как только вы поставите аргумент по имени, все оставшиеся аргументы должны быть переданы по имени.</span><span class="sxs-lookup"><span data-stu-id="3214b-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="3214b-122">Например, следующий вызов `Display` метода отображает ошибку компилятора [BC30241: Именованный аргумент ожидаемый.](../../../misc/bc30241.md)</span><span class="sxs-lookup"><span data-stu-id="3214b-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

<span data-ttu-id="3214b-123">Начиная с Visual Basic 15.5, позиционные аргументы могут следовать названным аргументам, если окончание позиционных аргументов находятся в правильном положении.</span><span class="sxs-lookup"><span data-stu-id="3214b-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="3214b-124">Если компилируется в соответствии с Visual `Display` Basic 15.5, предыдущий вызов метода успешно компилируется и больше не генерирует ошибку компилятора [BC30241.](../../../misc/bc30241.md)</span><span class="sxs-lookup"><span data-stu-id="3214b-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>

<span data-ttu-id="3214b-125">Эта способность смешивать и сочетать названные и позиционные аргументы в любом порядке особенно полезна, когда вы хотите использовать названный аргумент, чтобы сделать ваш код более читаемым.</span><span class="sxs-lookup"><span data-stu-id="3214b-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="3214b-126">Например, следующий `Person` конструктор класса требует двух `Person`аргументов типа, `Nothing`оба из которых могут быть.</span><span class="sxs-lookup"><span data-stu-id="3214b-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

<span data-ttu-id="3214b-127">Использование смешанных именованных и позиционных аргументов помогает сделать `mother` цель `Nothing`кода ясным, когда значение `father` и аргументы:</span><span class="sxs-lookup"><span data-stu-id="3214b-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

<span data-ttu-id="3214b-128">Чтобы следовать позиционным аргументам с названными аргументами, необходимо\*добавить следующий элемент в файл Visual Basic Project (.vbproj):</span><span class="sxs-lookup"><span data-stu-id="3214b-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="3214b-129">Для получения дополнительной информации [см.](../../../language-reference/configure-language-version.md)</span><span class="sxs-lookup"><span data-stu-id="3214b-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="3214b-130">Ограничения на поставку аргументов по имени</span><span class="sxs-lookup"><span data-stu-id="3214b-130">Restrictions on Supplying Arguments by Name</span></span>

<span data-ttu-id="3214b-131">Вы не можете передавать аргументы по имени, чтобы избежать ввода необходимых аргументов.</span><span class="sxs-lookup"><span data-stu-id="3214b-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="3214b-132">Вы можете пропустить только факультативные аргументы.</span><span class="sxs-lookup"><span data-stu-id="3214b-132">You can omit only the optional arguments.</span></span>

<span data-ttu-id="3214b-133">Вы не можете передать параметр по имени.</span><span class="sxs-lookup"><span data-stu-id="3214b-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="3214b-134">Это происходит потому, что при вызове процедуры вы поставляете неопределенное количество аргументов, разделенных запятой, для массива параметров, и компилятор не может связать более одного аргумента с одним именем.</span><span class="sxs-lookup"><span data-stu-id="3214b-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>

## <a name="see-also"></a><span data-ttu-id="3214b-135">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3214b-135">See also</span></span>

- [<span data-ttu-id="3214b-136">Процедуры</span><span class="sxs-lookup"><span data-stu-id="3214b-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="3214b-137">Параметры и аргументы процедуры</span><span class="sxs-lookup"><span data-stu-id="3214b-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3214b-138">Практическое руководство. Передача аргументов в процедуру</span><span class="sxs-lookup"><span data-stu-id="3214b-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="3214b-139">Передача аргументов по значению и по ссылке</span><span class="sxs-lookup"><span data-stu-id="3214b-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="3214b-140">Дополнительные параметры</span><span class="sxs-lookup"><span data-stu-id="3214b-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="3214b-141">Массивы параметров</span><span class="sxs-lookup"><span data-stu-id="3214b-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="3214b-142">Дополнительные</span><span class="sxs-lookup"><span data-stu-id="3214b-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
- [<span data-ttu-id="3214b-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="3214b-143">ParamArray</span></span>](../../../../visual-basic/language-reference/modifiers/paramarray.md)
