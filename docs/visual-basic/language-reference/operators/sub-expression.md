---
title: Часть выражения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 602212e664fa3362742fb1ba0dc033610272d3af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="sub-expression-visual-basic"></a><span data-ttu-id="bfa84-102">Часть выражения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfa84-102">Sub Expression (Visual Basic)</span></span>
<span data-ttu-id="bfa84-103">Объявляет параметры и код, определяющий подпрограммы лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="bfa84-103">Declares the parameters and code that define a subroutine lambda expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa84-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfa84-104">Syntax</span></span>  
  
```  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a><span data-ttu-id="bfa84-105">Части</span><span class="sxs-lookup"><span data-stu-id="bfa84-105">Parts</span></span>  
  
|<span data-ttu-id="bfa84-106">Термин</span><span class="sxs-lookup"><span data-stu-id="bfa84-106">Term</span></span>|<span data-ttu-id="bfa84-107">Определение</span><span class="sxs-lookup"><span data-stu-id="bfa84-107">Definition</span></span>|  
|---|---|  
|`parameterlist`|<span data-ttu-id="bfa84-108">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="bfa84-108">Optional.</span></span> <span data-ttu-id="bfa84-109">Список имен локальных переменных, представляющих параметры этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="bfa84-109">A list of local variable names that represent the parameters of the procedure.</span></span> <span data-ttu-id="bfa84-110">Круглые скобки должны присутствовать даже в том случае, если список пуст.</span><span class="sxs-lookup"><span data-stu-id="bfa84-110">The parentheses must be present even when the list is empty.</span></span> <span data-ttu-id="bfa84-111">Дополнительные сведения см. в разделе [список параметров](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="bfa84-111">For more information, see [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>|  
|`statement`|<span data-ttu-id="bfa84-112">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="bfa84-112">Required.</span></span> <span data-ttu-id="bfa84-113">Один оператор.</span><span class="sxs-lookup"><span data-stu-id="bfa84-113">A single statement.</span></span>|  
|`statements`|<span data-ttu-id="bfa84-114">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="bfa84-114">Required.</span></span> <span data-ttu-id="bfa84-115">Список инструкций.</span><span class="sxs-lookup"><span data-stu-id="bfa84-115">A list of statements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfa84-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="bfa84-116">Remarks</span></span>  
 <span data-ttu-id="bfa84-117">Объект *лямбда-выражение* представляет собой подпрограмму, которая не имеет имени и которое выполняется один или несколько операторов.</span><span class="sxs-lookup"><span data-stu-id="bfa84-117">A *lambda expression* is a subroutine that does not have a name and that executes one or more statements.</span></span> <span data-ttu-id="bfa84-118">Лямбда-выражение можно использовать в любом можно использовать тип делегата, за исключением того, как аргумент `RemoveHandler`.</span><span class="sxs-lookup"><span data-stu-id="bfa84-118">You can use a lambda expression anywhere that you can use a delegate type, except as an argument to `RemoveHandler`.</span></span> <span data-ttu-id="bfa84-119">Дополнительные сведения о делегатах и использование лямбда-выражений с делегатами см. в разделе [оператор Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md) и [неявное преобразование делегата](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="bfa84-119">For more information about delegates, and the use of lambda expressions with delegates, see [Delegate Statement](../../../visual-basic/language-reference/statements/delegate-statement.md) and [Relaxed Delegate Conversion](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="lambda-expression-syntax"></a><span data-ttu-id="bfa84-120">Синтаксис лямбда-выражений</span><span class="sxs-lookup"><span data-stu-id="bfa84-120">Lambda Expression Syntax</span></span>  
 <span data-ttu-id="bfa84-121">Синтаксис лямбда-выражение напоминает, стандартные подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="bfa84-121">The syntax of a lambda expression resembles that of a standard subroutine.</span></span> <span data-ttu-id="bfa84-122">Существуют следующие различия.</span><span class="sxs-lookup"><span data-stu-id="bfa84-122">The differences are as follows:</span></span>  
  
-   <span data-ttu-id="bfa84-123">Лямбда-выражение не имеет имени.</span><span class="sxs-lookup"><span data-stu-id="bfa84-123">A lambda expression does not have a name.</span></span>  
  
-   <span data-ttu-id="bfa84-124">Лямбда-выражение не может иметь модификаторы, такие как `Overloads` или `Overrides`.</span><span class="sxs-lookup"><span data-stu-id="bfa84-124">A lambda expression cannot have a modifier, such as `Overloads` or `Overrides`.</span></span>  
  
-   <span data-ttu-id="bfa84-125">Тело Однострочные лямбда-выражения должно быть инструкции, а не к выражению.</span><span class="sxs-lookup"><span data-stu-id="bfa84-125">The body of a single-line lambda expression must be a statement, not an expression.</span></span> <span data-ttu-id="bfa84-126">Текст может состоять из вызова процедуры sub, но не вызов процедуры function.</span><span class="sxs-lookup"><span data-stu-id="bfa84-126">The body can consist of a call to a sub procedure, but not a call to a function procedure.</span></span>  
  
-   <span data-ttu-id="bfa84-127">Лямбда-выражение либо все параметры необходимо задать, необходимо определить типы данных или всех параметров.</span><span class="sxs-lookup"><span data-stu-id="bfa84-127">In a lambda expression, either all parameters must have specified data types or all parameters must be inferred.</span></span>  
  
-   <span data-ttu-id="bfa84-128">Необязательный и `ParamArray` параметров в лямбда-выражения не допускается.</span><span class="sxs-lookup"><span data-stu-id="bfa84-128">Optional and `ParamArray` parameters are not permitted in lambda expressions.</span></span>  
  
-   <span data-ttu-id="bfa84-129">Универсальные параметры в лямбда-выражениях не допускаются.</span><span class="sxs-lookup"><span data-stu-id="bfa84-129">Generic parameters are not permitted in lambda expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfa84-130">Пример</span><span class="sxs-lookup"><span data-stu-id="bfa84-130">Example</span></span>  
 <span data-ttu-id="bfa84-131">Ниже приведен пример лямбда-выражения, записывающего значение на консоль.</span><span class="sxs-lookup"><span data-stu-id="bfa84-131">Following is an example of a lambda expression that writes a value to the console.</span></span> <span data-ttu-id="bfa84-132">В примере синтаксиса однострочный и многострочный лямбда-выражения для подпрограммы.</span><span class="sxs-lookup"><span data-stu-id="bfa84-132">The example shows both the single-line and multiline lambda expression syntax for a subroutine.</span></span> <span data-ttu-id="bfa84-133">Дополнительные примеры см. в разделе [лямбда-выражения](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="bfa84-133">For more examples, see [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).</span></span>  
  
 [!code-vb[VbVbalrLambdas#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/sub-expression_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bfa84-134">См. также</span><span class="sxs-lookup"><span data-stu-id="bfa84-134">See Also</span></span>  
 [<span data-ttu-id="bfa84-135">Оператор Sub</span><span class="sxs-lookup"><span data-stu-id="bfa84-135">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="bfa84-136">Лямбда-выражения</span><span class="sxs-lookup"><span data-stu-id="bfa84-136">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="bfa84-137">Операторы и выражения</span><span class="sxs-lookup"><span data-stu-id="bfa84-137">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [<span data-ttu-id="bfa84-138">Операторы</span><span class="sxs-lookup"><span data-stu-id="bfa84-138">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)  
 [<span data-ttu-id="bfa84-139">Неявное преобразование делегата</span><span class="sxs-lookup"><span data-stu-id="bfa84-139">Relaxed Delegate Conversion</span></span>](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
