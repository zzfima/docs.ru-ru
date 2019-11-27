---
title: Выражение function
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: d14d7c9bc701b5e06c51202c07c3b79832aba7cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331083"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="29cf3-102">Выражение Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29cf3-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="29cf3-103">Объявляет параметры и код, определяющие лямбда-выражение функции.</span><span class="sxs-lookup"><span data-stu-id="29cf3-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29cf3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="29cf3-104">Syntax</span></span>  
  
```vb  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="29cf3-105">Части</span><span class="sxs-lookup"><span data-stu-id="29cf3-105">Parts</span></span>  
  
|<span data-ttu-id="29cf3-106">Термин</span><span class="sxs-lookup"><span data-stu-id="29cf3-106">Term</span></span>|<span data-ttu-id="29cf3-107">Определение</span><span class="sxs-lookup"><span data-stu-id="29cf3-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="29cf3-108">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="29cf3-108">Optional.</span></span> <span data-ttu-id="29cf3-109">Список имен локальных переменных, представляющих параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="29cf3-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="29cf3-110">Круглые скобки должны присутствовать, даже если список пуст.</span><span class="sxs-lookup"><span data-stu-id="29cf3-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="29cf3-111">См. [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="29cf3-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="29cf3-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="29cf3-112">Required.</span></span> <span data-ttu-id="29cf3-113">Одно выражение.</span><span class="sxs-lookup"><span data-stu-id="29cf3-113">A single expression.</span></span> <span data-ttu-id="29cf3-114">Тип выражения является типом возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="29cf3-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="29cf3-115">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="29cf3-115">Required.</span></span> <span data-ttu-id="29cf3-116">Список инструкций, которые возвращают значение с помощью оператора `Return`.</span><span class="sxs-lookup"><span data-stu-id="29cf3-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="29cf3-117">(См. раздел [оператор return](../../../visual-basic/language-reference/statements/return-statement.md).) Тип возвращаемого значения — это возвращаемый тип функции.</span><span class="sxs-lookup"><span data-stu-id="29cf3-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29cf3-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="29cf3-118">Remarks</span></span>  
 <span data-ttu-id="29cf3-119">*Лямбда-выражение* — это функция без имени, которая вычисляет и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="29cf3-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="29cf3-120">Лямбда-выражение можно использовать в любом месте, где можно использовать тип делегата, за исключением того, что в качестве аргумента для `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="29cf3-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="29cf3-121">Дополнительные сведения о делегатах и использовании лямбда-выражений с делегатами см. в разделе [оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [Преобразование неявного делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="29cf3-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="29cf3-122">Синтаксис лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="29cf3-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="29cf3-123">Синтаксис лямбда-выражения напоминает стандартную функцию.</span><span class="sxs-lookup"><span data-stu-id="29cf3-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="29cf3-124">Различия заключаются в следующем.</span><span class="sxs-lookup"><span data-stu-id="29cf3-124">The differences are as follows:</span></span>  
  
- <span data-ttu-id="29cf3-125">Лямбда-выражение не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="29cf3-125">A lambda expression does not have a name.</span></span>  
  
- <span data-ttu-id="29cf3-126">Лямбда-выражения не могут иметь модификаторы, такие как `Overloads` или `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="29cf3-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
- <span data-ttu-id="29cf3-127">Лямбда-выражения не используют предложение `As` для обозначения возвращаемого типа функции.</span><span class="sxs-lookup"><span data-stu-id="29cf3-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="29cf3-128">Вместо этого тип выводится из значения, которое принимает текст однострочного лямбда-выражения, или возвращаемое значение многострочного лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="29cf3-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="29cf3-129">Например, если текст однострочного лямбда-выражения имеет `Where cust.City = "London"`, его возвращаемый тип — `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="29cf3-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
- <span data-ttu-id="29cf3-130">Тело однострочного лямбда-выражения должно быть выражением, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="29cf3-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="29cf3-131">Тело может состоять из вызова процедуры функции, но не вызова процедуры подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="29cf3-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
- <span data-ttu-id="29cf3-132">Либо все параметры должны иметь указанные типы данных, либо все должны быть выведены.</span><span class="sxs-lookup"><span data-stu-id="29cf3-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
- <span data-ttu-id="29cf3-133">Параметры Optional и ParamArray не разрешены.</span><span class="sxs-lookup"><span data-stu-id="29cf3-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
- <span data-ttu-id="29cf3-134">Универсальные параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="29cf3-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29cf3-135">Пример</span><span class="sxs-lookup"><span data-stu-id="29cf3-135">Example</span></span>  
 <span data-ttu-id="29cf3-136">В следующих примерах показано два способа создания простых лямбда-выражений.</span><span class="sxs-lookup"><span data-stu-id="29cf3-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="29cf3-137">Первый использует `Dim` для предоставления имени функции.</span><span class="sxs-lookup"><span data-stu-id="29cf3-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="29cf3-138">Для вызова функции вы отправляете значение для параметра.</span><span class="sxs-lookup"><span data-stu-id="29cf3-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
 [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="29cf3-139">Пример</span><span class="sxs-lookup"><span data-stu-id="29cf3-139">Example</span></span>  
 <span data-ttu-id="29cf3-140">Кроме того, можно одновременно объявить и запустить функцию.</span><span class="sxs-lookup"><span data-stu-id="29cf3-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="29cf3-141">Пример</span><span class="sxs-lookup"><span data-stu-id="29cf3-141">Example</span></span>  
 <span data-ttu-id="29cf3-142">Ниже приведен пример лямбда-выражения, которое увеличивает свой аргумент и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="29cf3-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="29cf3-143">В примере показан синтаксис однострочного и многострочного лямбда-выражения для функции.</span><span class="sxs-lookup"><span data-stu-id="29cf3-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="29cf3-144">Дополнительные примеры см. в разделе [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="29cf3-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#14)]  
  
## <a name="example"></a><span data-ttu-id="29cf3-145">Пример</span><span class="sxs-lookup"><span data-stu-id="29cf3-145">Example</span></span>  
 <span data-ttu-id="29cf3-146">Лямбда-выражения лежат в основе многих операторов запроса в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]и могут использоваться явно в запросах на основе методов.</span><span class="sxs-lookup"><span data-stu-id="29cf3-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="29cf3-147">В следующем примере показан типичный [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запрос, а затем перевод запроса в формат метода.</span><span class="sxs-lookup"><span data-stu-id="29cf3-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="29cf3-148">Дополнительные сведения о методах запросов см. в разделе [запросы](../../../visual-basic/language-reference/queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="29cf3-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="29cf3-149">Дополнительные сведения о стандартных операторах запросов см. в разделе [Общие сведения о стандартных операторах запросов](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="29cf3-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29cf3-150">См. также</span><span class="sxs-lookup"><span data-stu-id="29cf3-150">See also</span></span>

- [<span data-ttu-id="29cf3-151">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="29cf3-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="29cf3-152">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="29cf3-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [<span data-ttu-id="29cf3-153">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="29cf3-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [<span data-ttu-id="29cf3-154">Операторы</span><span class="sxs-lookup"><span data-stu-id="29cf3-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
- [<span data-ttu-id="29cf3-155">Сравнения значений</span><span class="sxs-lookup"><span data-stu-id="29cf3-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)
- [<span data-ttu-id="29cf3-156">Логические выражения</span><span class="sxs-lookup"><span data-stu-id="29cf3-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)
- [<span data-ttu-id="29cf3-157">Оператор If</span><span class="sxs-lookup"><span data-stu-id="29cf3-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
- [<span data-ttu-id="29cf3-158">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="29cf3-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
