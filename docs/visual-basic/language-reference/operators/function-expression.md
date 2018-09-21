---
title: Выражение Function (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
ms.openlocfilehash: cfdd17f6f4ee6c4ddb3fa73ab3ec9c5ce46a162f
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "46525179"
---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="7d3f4-102">Выражение Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d3f4-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="7d3f4-103">Объявляет параметры и код, которые определяют функции лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d3f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d3f4-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="7d3f4-105">Части</span><span class="sxs-lookup"><span data-stu-id="7d3f4-105">Parts</span></span>  
  
|<span data-ttu-id="7d3f4-106">Термин</span><span class="sxs-lookup"><span data-stu-id="7d3f4-106">Term</span></span>|<span data-ttu-id="7d3f4-107">Определение</span><span class="sxs-lookup"><span data-stu-id="7d3f4-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="7d3f4-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-108">Optional.</span></span> <span data-ttu-id="7d3f4-109">Список имен локальных переменных, представляющих параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="7d3f4-110">Круглые скобки должен присутствовать даже в том случае, если список пуст.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="7d3f4-111">См. в разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="7d3f4-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="7d3f4-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-112">Required.</span></span> <span data-ttu-id="7d3f4-113">Одно выражение.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-113">A single expression.</span></span> <span data-ttu-id="7d3f4-114">Тип выражения — тип возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="7d3f4-115">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-115">Required.</span></span> <span data-ttu-id="7d3f4-116">Список инструкций, возвращает значение, используя `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="7d3f4-117">(См. в разделе [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).) Тип возвращаемого значения — тип возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d3f4-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d3f4-118">Remarks</span></span>  
 <span data-ttu-id="7d3f4-119">Объект *лямбда-выражение* является функцией без имени, которая вычисляет и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="7d3f4-120">Лямбда-выражения можно использовать везде, где можно использовать тип делегата, кроме как аргумент `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="7d3f4-121">Дополнительные сведения о делегатах и использование лямбда-выражений с делегатами, см. в разделе [оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="7d3f4-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="7d3f4-122">Синтаксис лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="7d3f4-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="7d3f4-123">Синтаксис лямбда-выражения похож стандартной функции.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="7d3f4-124">Ниже приведены различия.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="7d3f4-125">Лямбда-выражение не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="7d3f4-126">Лямбда-выражения не может иметь модификаторы, такие как `Overloads` или `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="7d3f4-127">Лямбда-выражения не используйте `As` предложение, чтобы указать тип возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="7d3f4-128">Вместо этого тип выводится из, тело однострочных лямбда-выражение, результатом которого является значение или возвращаемое значение многострочного лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="7d3f4-129">Например, если текст однострочное лямбда-выражения `Where cust.City = "London"`, его возвращаемый тип — `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="7d3f4-130">Тело однострочное лямбда-выражения должно быть выражением, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="7d3f4-131">Текст может состоять из вызова процедуры функции, но не вызов процедуры sub.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="7d3f4-132">Необходимо заранее указать все параметры, что необходимо определить типы данных или все.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="7d3f4-133">Optional и Paramarray параметров не разрешены.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="7d3f4-134">Универсальные параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d3f4-135">Пример</span><span class="sxs-lookup"><span data-stu-id="7d3f4-135">Example</span></span>  
 <span data-ttu-id="7d3f4-136">В следующих примерах показано два способа создания простых лямбда-выражений.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="7d3f4-137">Первый использует `Dim` для предоставления имени функции.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="7d3f4-138">Для вызова функции, вы отправляете в значение параметра.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-138">To call the function, you send in a value for the parameter.</span></span>  
  
 [!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]  
  
 [!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]  
  
## <a name="example"></a><span data-ttu-id="7d3f4-139">Пример</span><span class="sxs-lookup"><span data-stu-id="7d3f4-139">Example</span></span>  
 <span data-ttu-id="7d3f4-140">Кроме того можно объявить и запустить функцию, в то же время.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-140">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 [!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="7d3f4-141">Пример</span><span class="sxs-lookup"><span data-stu-id="7d3f4-141">Example</span></span>  
 <span data-ttu-id="7d3f4-142">Ниже приведен пример лямбда-выражения, увеличивает значение своего аргумента и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-142">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="7d3f4-143">В этом примере синтаксис однострочный и многострочный лямбда-выражения для функции.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-143">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="7d3f4-144">Дополнительные примеры см. в разделе [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7d3f4-144">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]  
  
## <a name="example"></a><span data-ttu-id="7d3f4-145">Пример</span><span class="sxs-lookup"><span data-stu-id="7d3f4-145">Example</span></span>  
 <span data-ttu-id="7d3f4-146">Лямбда-выражения лежат в основе многих операторов запроса в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]и может использоваться в запросах на основе методов явным образом.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-146">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="7d3f4-147">В следующем примере показан типичный [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса, за преобразования запроса в формат метода.</span><span class="sxs-lookup"><span data-stu-id="7d3f4-147">The following example shows a typical [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="7d3f4-148">Дополнительные сведения о методах запросов см. в разделе [запросы](../../../visual-basic/language-reference/queries/index.md).</span><span class="sxs-lookup"><span data-stu-id="7d3f4-148">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/index.md).</span></span> <span data-ttu-id="7d3f4-149">Дополнительные сведения о стандартных операторах запросов см. в разделе [Общие сведения о стандартных операторах запроса](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7d3f4-149">For more information about standard query operators, see [Standard Query Operators Overview](../../programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d3f4-150">См. также</span><span class="sxs-lookup"><span data-stu-id="7d3f4-150">See Also</span></span>  
 [<span data-ttu-id="7d3f4-151">Оператор Function</span><span class="sxs-lookup"><span data-stu-id="7d3f4-151">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="7d3f4-152">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="7d3f4-152">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="7d3f4-153">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="7d3f4-153">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="7d3f4-154">Операторы</span><span class="sxs-lookup"><span data-stu-id="7d3f4-154">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="7d3f4-155">Сравнения значений</span><span class="sxs-lookup"><span data-stu-id="7d3f4-155">Value Comparisons</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)  
 [<span data-ttu-id="7d3f4-156">Логические выражения</span><span class="sxs-lookup"><span data-stu-id="7d3f4-156">Boolean Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)  
 [<span data-ttu-id="7d3f4-157">Оператор If</span><span class="sxs-lookup"><span data-stu-id="7d3f4-157">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)  
 [<span data-ttu-id="7d3f4-158">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="7d3f4-158">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
