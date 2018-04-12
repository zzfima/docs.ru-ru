---
title: Оператор TryCast (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6be11b49eb3b9d98e3bf147e9b1026d4ffc860c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="8c643-102">Оператор TryCast (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c643-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="8c643-103">Вводит операцию преобразования типа, не вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="8c643-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c643-104">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c643-104">Remarks</span></span>  
 <span data-ttu-id="8c643-105">Если попытка преобразования завершается ошибкой, `CType` и `DirectCast` оба throw <xref:System.InvalidCastException> ошибки.</span><span class="sxs-lookup"><span data-stu-id="8c643-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="8c643-106">Это может отрицательно сказаться на производительности приложения.</span><span class="sxs-lookup"><span data-stu-id="8c643-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="8c643-107">`TryCast`Возвращает [ничего](../../../visual-basic/language-reference/nothing.md)таким образом, вместо того, для обработки возможных исключений, требуется только протестировать возвращенный результат от `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="8c643-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="8c643-108">Вы используете `TryCast` ключевое слово так же, как [функция CType](../../../visual-basic/language-reference/functions/ctype-function.md) и [оператор DirectCast](../../../visual-basic/language-reference/operators/directcast-operator.md) ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="8c643-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="8c643-109">Можно указать выражение в качестве первого аргумента и тип для преобразования его в качестве второго аргумента.</span><span class="sxs-lookup"><span data-stu-id="8c643-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="8c643-110">`TryCast`работает только со ссылочными типами, таких как классы и интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="8c643-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="8c643-111">Требуется отношение наследования или реализации между двумя типами.</span><span class="sxs-lookup"><span data-stu-id="8c643-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="8c643-112">Это означает, что один тип должен реализовывать или наследовать из другого.</span><span class="sxs-lookup"><span data-stu-id="8c643-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="8c643-113">Ошибки и сбои</span><span class="sxs-lookup"><span data-stu-id="8c643-113">Errors and Failures</span></span>  
 <span data-ttu-id="8c643-114">`TryCast`создает ошибку компилятора, если он обнаруживает, что существует отношение наследования или реализации.</span><span class="sxs-lookup"><span data-stu-id="8c643-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="8c643-115">Однако отсутствие ошибки компилятора не гарантирует успешное преобразование.</span><span class="sxs-lookup"><span data-stu-id="8c643-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="8c643-116">Если требуемое преобразование будет сужающим, то возможен сбой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8c643-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="8c643-117">В этом случае `TryCast` возвращает [ничего не](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="8c643-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="8c643-118">Ключевые слова преобразований</span><span class="sxs-lookup"><span data-stu-id="8c643-118">Conversion Keywords</span></span>  
 <span data-ttu-id="8c643-119">Сравнение ключевых слов преобразования типов выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="8c643-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="8c643-120">Ключевое слово</span><span class="sxs-lookup"><span data-stu-id="8c643-120">Keyword</span></span>|<span data-ttu-id="8c643-121">Типы данных</span><span class="sxs-lookup"><span data-stu-id="8c643-121">Data types</span></span>|<span data-ttu-id="8c643-122">Отношение аргументов</span><span class="sxs-lookup"><span data-stu-id="8c643-122">Argument relationship</span></span>|<span data-ttu-id="8c643-123">Ошибка времени выполнения</span><span class="sxs-lookup"><span data-stu-id="8c643-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="8c643-124">Функция CType</span><span class="sxs-lookup"><span data-stu-id="8c643-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="8c643-125">Типы данных</span><span class="sxs-lookup"><span data-stu-id="8c643-125">Any data types</span></span>|<span data-ttu-id="8c643-126">Должен быть определен расширяющее или сужающее преобразование между двумя типами данных</span><span class="sxs-lookup"><span data-stu-id="8c643-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="8c643-127">Создает исключение<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="8c643-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="8c643-128">Оператор DirectCast</span><span class="sxs-lookup"><span data-stu-id="8c643-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="8c643-129">Типы данных</span><span class="sxs-lookup"><span data-stu-id="8c643-129">Any data types</span></span>|<span data-ttu-id="8c643-130">Один тип должен наследовать или реализовывать другой</span><span class="sxs-lookup"><span data-stu-id="8c643-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="8c643-131">Создает исключение<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="8c643-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="8c643-132">Только ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="8c643-132">Reference types only</span></span>|<span data-ttu-id="8c643-133">Один тип должен наследовать или реализовывать другой</span><span class="sxs-lookup"><span data-stu-id="8c643-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="8c643-134">Возвращает [Nothing](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="8c643-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8c643-135">Пример</span><span class="sxs-lookup"><span data-stu-id="8c643-135">Example</span></span>  
 <span data-ttu-id="8c643-136">В следующем примере показано, как использовать `TryCast`.</span><span class="sxs-lookup"><span data-stu-id="8c643-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="8c643-137">См. также</span><span class="sxs-lookup"><span data-stu-id="8c643-137">See Also</span></span>  
 [<span data-ttu-id="8c643-138">Расширяющие и сужающие преобразования</span><span class="sxs-lookup"><span data-stu-id="8c643-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="8c643-139">Явные и неявные преобразования</span><span class="sxs-lookup"><span data-stu-id="8c643-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
