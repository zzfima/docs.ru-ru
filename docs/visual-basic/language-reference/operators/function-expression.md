---
title: "Функция выражения (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Function expression [Visual Basic]
- functions [Visual Basic], function expressions
- lambda expressions [Visual Basic], function expression
ms.assetid: e8a47a45-4b8a-4f45-a623-7653625dffbc
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: c379ed1694f72243ccb8367d5b820803b4fcf190
ms.contentlocale: ru-ru
ms.lasthandoff: 05/23/2017

---
# <a name="function-expression-visual-basic"></a><span data-ttu-id="99254-102">Выражение Function (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="99254-102">Function Expression (Visual Basic)</span></span>
<span data-ttu-id="99254-103">Объявляет параметры и код, определяющий функции лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="99254-103">Declares the parameters and code that define a function lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99254-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="99254-104">Syntax</span></span>  
  
```  
Function ( [ parameterlist ] ) expression  
- or -  
Function ( [ parameterlist ] )  
  [ statements ]  
End Function  
```  
  
## <a name="parts"></a><span data-ttu-id="99254-105">Части</span><span class="sxs-lookup"><span data-stu-id="99254-105">Parts</span></span>  
  
|<span data-ttu-id="99254-106">Термин</span><span class="sxs-lookup"><span data-stu-id="99254-106">Term</span></span>|<span data-ttu-id="99254-107">Определение</span><span class="sxs-lookup"><span data-stu-id="99254-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="99254-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="99254-108">Optional.</span></span> <span data-ttu-id="99254-109">Список имен локальных переменных, представляющих параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="99254-109">A list of local variable names that represent the parameters of this procedure.</span></span> <span data-ttu-id="99254-110">Круглые скобки должны присутствовать даже в том случае, если список пуст.</span><span class="sxs-lookup"><span data-stu-id="99254-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="99254-111">В разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="99254-111">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`expression`|<span data-ttu-id="99254-112">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="99254-112">Required.</span></span> <span data-ttu-id="99254-113">Одно выражение.</span><span class="sxs-lookup"><span data-stu-id="99254-113">A single expression.</span></span> <span data-ttu-id="99254-114">Тип выражения является типом возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="99254-114">The type of the expression is the return type of the function.</span></span>|  
|`statements`|<span data-ttu-id="99254-115">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="99254-115">Required.</span></span> <span data-ttu-id="99254-116">Список инструкций, возвращает значение, используя `Return` инструкции.</span><span class="sxs-lookup"><span data-stu-id="99254-116">A list of statements that returns a value by using the `Return` statement.</span></span> <span data-ttu-id="99254-117">(См. [оператор Return](../../../visual-basic/language-reference/statements/return-statement.md).) Тип возвращаемого значения — возвращаемый тип функции.</span><span class="sxs-lookup"><span data-stu-id="99254-117">(See [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md).) The type of the value returned is the return type of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99254-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="99254-118">Remarks</span></span>  
 <span data-ttu-id="99254-119">Объект *лямбда-выражение* является функцией без имени, которая вычисляет и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="99254-119">A *lambda expression* is a function without a name that calculates and returns a value.</span></span> <span data-ttu-id="99254-120">Лямбда-выражение можно использовать везде, где можно использовать тип делегата, за исключением того, в качестве аргумента `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="99254-120">You can use a lambda expression anywhere you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="99254-121">Дополнительные сведения о делегатах и использовании лямбда-выражений с делегатами см. в разделе [оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="99254-121">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="99254-122">Синтаксис лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="99254-122">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="99254-123">Синтаксис лямбда-выражение напоминает стандартной функции.</span><span class="sxs-lookup"><span data-stu-id="99254-123">The syntax of a lambda expression resembles that of a standard function.</span></span> <span data-ttu-id="99254-124">Ниже приведены различия.</span><span class="sxs-lookup"><span data-stu-id="99254-124">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="99254-125">Лямбда-выражение не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="99254-125">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="99254-126">Лямбда-выражения не могут иметь модификаторы, такие как `Overloads` или `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="99254-126">Lambda expressions cannot have modifiers, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="99254-127">Лямбда-выражения не используйте `As` предложение для обозначения типом возвращаемого значения функции.</span><span class="sxs-lookup"><span data-stu-id="99254-127">Lambda expressions do not use an `As` clause to designate the return type of the function.</span></span> <span data-ttu-id="99254-128">Вместо этого тип выводится из, текст Однострочные лямбда-выражение, результатом которого является значение или возвращаемое значение многострочных лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="99254-128">Instead, the type is inferred from the value that the body of a single-line lambda expression evaluates to, or the return value of a multiline lambda expression.</span></span> <span data-ttu-id="99254-129">Например, если текст Однострочные лямбда-выражения `Where cust.City = "London"`, возвращается тип `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="99254-129">For example, if the body of a single-line lambda expression is `Where cust.City = "London"`, its return type is `Boolean`.</span></span>  
  
-   <span data-ttu-id="99254-130">Тело Однострочные лямбда-выражения должно быть выражением, а не оператором.</span><span class="sxs-lookup"><span data-stu-id="99254-130">The body of a single-line lambda expression must be an expression, not a statement.</span></span> <span data-ttu-id="99254-131">Текст может состоять из вызова процедуры function, но не вызов процедуры sub.</span><span class="sxs-lookup"><span data-stu-id="99254-131">The body can consist of a call to a function procedure, but not a call to a sub procedure.</span></span>  
  
-   <span data-ttu-id="99254-132">Все параметры должно было быть задано, что необходимо определить типы данных или все.</span><span class="sxs-lookup"><span data-stu-id="99254-132">Either all parameters must have specified data types or all must be inferred.</span></span>  
  
-   <span data-ttu-id="99254-133">Параметры необязательно и Paramarray не разрешены.</span><span class="sxs-lookup"><span data-stu-id="99254-133">Optional and Paramarray parameters are not permitted.</span></span>  
  
-   <span data-ttu-id="99254-134">Универсальные параметры не допускаются.</span><span class="sxs-lookup"><span data-stu-id="99254-134">Generic parameters are not permitted.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99254-135">Пример</span><span class="sxs-lookup"><span data-stu-id="99254-135">Example</span></span>  
 <span data-ttu-id="99254-136">В следующих примерах показано два способа создания простых лямбда-выражений.</span><span class="sxs-lookup"><span data-stu-id="99254-136">The following examples show two ways to create simple lambda expressions.</span></span> <span data-ttu-id="99254-137">Первый использует `Dim` для предоставления имени функции.</span><span class="sxs-lookup"><span data-stu-id="99254-137">The first uses a `Dim` to provide a name for the function.</span></span> <span data-ttu-id="99254-138">Для вызова функции, отправить значение параметра.</span><span class="sxs-lookup"><span data-stu-id="99254-138">To call the function, you send in a value for the parameter.</span></span>  
  
 <span data-ttu-id="99254-139">[!code-vb[VbVbalrLambdas&#1;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="99254-139">[!code-vb[VbVbalrLambdas#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_1.vb)]</span></span>  
  
 <span data-ttu-id="99254-140">[!code-vb[VbVbalrLambdas&#2;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="99254-140">[!code-vb[VbVbalrLambdas#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="99254-141">Пример</span><span class="sxs-lookup"><span data-stu-id="99254-141">Example</span></span>  
 <span data-ttu-id="99254-142">Кроме того можно объявить и запустить функцию одновременно.</span><span class="sxs-lookup"><span data-stu-id="99254-142">Alternatively, you can declare and run the function at the same time.</span></span>  
  
 <span data-ttu-id="99254-143">[!code-vb[VbVbalrLambdas&#3;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="99254-143">[!code-vb[VbVbalrLambdas#3](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="99254-144">Пример</span><span class="sxs-lookup"><span data-stu-id="99254-144">Example</span></span>  
 <span data-ttu-id="99254-145">Ниже приведен пример лямбда-выражения, которое увеличивает значение своего аргумента и возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="99254-145">Following is an example of a lambda expression that increments its argument and returns the value.</span></span> <span data-ttu-id="99254-146">В этом примере синтаксис однострочные и многострочные лямбда-выражений для функции.</span><span class="sxs-lookup"><span data-stu-id="99254-146">The example shows both the single-line and multiline lambda expression syntax for a function.</span></span> <span data-ttu-id="99254-147">Дополнительные примеры см. в разделе [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="99254-147">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 <span data-ttu-id="99254-148">[!code-vb[VbVbalrLambdas&#14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="99254-148">[!code-vb[VbVbalrLambdas#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/function-expression_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="99254-149">Пример</span><span class="sxs-lookup"><span data-stu-id="99254-149">Example</span></span>  
 <span data-ttu-id="99254-150">Лямбда-выражения лежат в основе многих операторов запроса в [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)]и может использоваться в запросах на основе методов явным образом.</span><span class="sxs-lookup"><span data-stu-id="99254-150">Lambda expressions underlie many of the query operators in [!INCLUDE[vbteclinqext](../../../csharp/getting-started/includes/vbteclinqext_md.md)], and can be used explicitly in method-based queries.</span></span> <span data-ttu-id="99254-151">В следующем примере показано типичное [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] запрос, с приведением результата запроса в формат метода.</span><span class="sxs-lookup"><span data-stu-id="99254-151">The following example shows a typical [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] query, followed by the translation of the query into method format.</span></span>  
  
```vb  
Dim londonCusts = From cust In db.Customers  
                       Where cust.City = "London"  
                       Select cust  
  
' This query is compiled to the following code:  
Dim londonCusts = db.Customers.  
                  Where(Function(cust) cust.City = "London").  
                  Select(Function(cust) cust)  
```  
  
 <span data-ttu-id="99254-152">Дополнительные сведения о методах запросов см. в разделе [запросов](../../../visual-basic/language-reference/queries/queries.md).</span><span class="sxs-lookup"><span data-stu-id="99254-152">For more information about query methods, see [Queries](../../../visual-basic/language-reference/queries/queries.md).</span></span> <span data-ttu-id="99254-153">Дополнительные сведения о стандартных операторах запросов см. в разделе [Общие сведения о стандартных операторах запроса](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span><span class="sxs-lookup"><span data-stu-id="99254-153">For more information about standard query operators, see [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99254-154">См. также</span><span class="sxs-lookup"><span data-stu-id="99254-154">See Also</span></span>  
 <span data-ttu-id="99254-155">[Оператор Function](../../../visual-basic/language-reference/statements/function-statement.md) </span><span class="sxs-lookup"><span data-stu-id="99254-155">[Function Statement](../../../visual-basic/language-reference/statements/function-statement.md) </span></span>  
<span data-ttu-id="99254-156"> [Лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="99254-156"> [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) </span></span>  
<span data-ttu-id="99254-157"> [Операторы и выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span><span class="sxs-lookup"><span data-stu-id="99254-157"> [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md) </span></span>  
<span data-ttu-id="99254-158"> [Инструкции](../../../visual-basic/programming-guide/language-features/statements.md) </span><span class="sxs-lookup"><span data-stu-id="99254-158"> [Statements](../../../visual-basic/programming-guide/language-features/statements.md) </span></span>  
<span data-ttu-id="99254-159"> [Сравнение значений](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span><span class="sxs-lookup"><span data-stu-id="99254-159"> [Value Comparisons](../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) </span></span>  
<span data-ttu-id="99254-160"> [Логические выражения](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="99254-160"> [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md) </span></span>  
<span data-ttu-id="99254-161"> [Если оператор](../../../visual-basic/language-reference/operators/if-operator.md) </span><span class="sxs-lookup"><span data-stu-id="99254-161"> [If Operator](../../../visual-basic/language-reference/operators/if-operator.md) </span></span>  
<span data-ttu-id="99254-162"> [Неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span><span class="sxs-lookup"><span data-stu-id="99254-162"> [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)</span></span>

