---
title: "Оператор yield (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 393a9f4de3e801aed5932aef0e2b13d76b003965
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="yield-statement-visual-basic"></a><span data-ttu-id="ccd6d-102">Оператор Yield (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ccd6d-102">Yield Statement (Visual Basic)</span></span>
<span data-ttu-id="ccd6d-103">Отправляет следующий элемент коллекции для `For Each...Next` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-103">Sends the next element of a collection to a `For Each...Next` statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccd6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ccd6d-104">Syntax</span></span>  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ccd6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ccd6d-105">Parameters</span></span>  
  
|<span data-ttu-id="ccd6d-106">Термин</span><span class="sxs-lookup"><span data-stu-id="ccd6d-106">Term</span></span>|<span data-ttu-id="ccd6d-107">Определение</span><span class="sxs-lookup"><span data-stu-id="ccd6d-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="ccd6d-108">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-108">Required.</span></span> <span data-ttu-id="ccd6d-109">Выражение, которое может быть неявно преобразован в тип функции итератора или `Get` метод доступа, который содержит `Yield` инструкции.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-109">An expression that is implicitly convertible to the type of the iterator function or `Get` accessor that contains the `Yield` statement.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccd6d-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="ccd6d-110">Remarks</span></span>  
 <span data-ttu-id="ccd6d-111">`Yield` Инструкция возвращает один элемент коллекции одновременно.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-111">The `Yield` statement returns one element of a collection at a time.</span></span> <span data-ttu-id="ccd6d-112">`Yield` Инструкция включена в функции итератора или `Get` доступа, который будет выполнять пользовательские итерации по коллекции.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-112">The `Yield` statement is included in an iterator function or `Get` accessor, which perform custom iterations over a collection.</span></span>  
  
 <span data-ttu-id="ccd6d-113">Использование функции итератора с помощью [For Each... Следующий оператор](../../../visual-basic/language-reference/statements/for-each-next-statement.md) или запрос LINQ.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-113">You consume an iterator function by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md) or a LINQ query.</span></span> <span data-ttu-id="ccd6d-114">Каждая итерация `For Each` цикл вызывает функции итератора.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-114">Each iteration of the `For Each` loop calls the iterator function.</span></span> <span data-ttu-id="ccd6d-115">Когда `Yield` достижении оператора в функции итератора `expression` возвращается и сохраняется текущее расположение в коде.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-115">When a `Yield` statement is reached in the iterator function, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="ccd6d-116">При следующем вызове функции итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-116">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="ccd6d-117">Должно существовать неявное преобразование из типа `expression` в `Yield` инструкции в возвращаемый тип итератора.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-117">An implicit conversion must exist from the type of `expression` in the `Yield` statement to the return type of the iterator.</span></span>  
  
 <span data-ttu-id="ccd6d-118">Можно использовать `Exit Function` или `Return` инструкции для завершения итерации.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-118">You can use an `Exit Function` or `Return` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="ccd6d-119">«Доход» не является зарезервированным словом и имеет специальное значение только в том случае, если он используется в `Iterator` функции или `Get` доступа.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-119">"Yield" is not a reserved word and has special meaning only when it is used in an `Iterator` function or `Get` accessor.</span></span>  
  
 <span data-ttu-id="ccd6d-120">Дополнительные сведения о функции итератора и `Get` методы доступа, в разделе [итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="ccd6d-120">For more information about iterator functions and `Get` accessors, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-functions-and-get-accessors"></a><span data-ttu-id="ccd6d-121">Функции итератора и методы доступа Get</span><span class="sxs-lookup"><span data-stu-id="ccd6d-121">Iterator Functions and Get Accessors</span></span>  
 <span data-ttu-id="ccd6d-122">Объявление функции итератора или `Get` доступа должен соответствовать следующим требованиям:</span><span class="sxs-lookup"><span data-stu-id="ccd6d-122">The declaration of an iterator function or `Get` accessor must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="ccd6d-123">Он должен содержать [итератор](../../../visual-basic/language-reference/modifiers/iterator.md) модификатор.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-123">It must include an [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) modifier.</span></span>  
  
-   <span data-ttu-id="ccd6d-124">Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, или <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="ccd6d-124">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="ccd6d-125">Он не может содержать `ByRef` параметров.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-125">It cannot have any `ByRef` parameters.</span></span>  
  
 <span data-ttu-id="ccd6d-126">Функция итератор не может содержаться событие, конструктор экземпляра, статический конструктор или деструктор статический.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-126">An iterator function cannot occur in an event, instance constructor, static constructor, or static destructor.</span></span>  
  
 <span data-ttu-id="ccd6d-127">Функции итератора может быть анонимной функции.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-127">An iterator function can be an anonymous function.</span></span> <span data-ttu-id="ccd6d-128">Дополнительные сведения см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="ccd6d-128">For more information, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="ccd6d-129">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="ccd6d-129">Exception Handling</span></span>  
 <span data-ttu-id="ccd6d-130">Объект `Yield` инструкция может находиться внутри `Try` блока [Try... CATCH... Оператор Finally](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ccd6d-130">A `Yield` statement can be inside a `Try` block of a [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span> <span data-ttu-id="ccd6d-131">Объект `Try` блок, который имеет `Yield` инструкция может иметь `Catch` блокируется и может иметь `Finally` блок.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-131">A `Try` block that has a `Yield` statement can have `Catch` blocks, and can have a `Finally` block.</span></span>  
  
 <span data-ttu-id="ccd6d-132">Объект `Yield` оператор не может находиться внутри `Catch` блока или `Finally` блока.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-132">A `Yield` statement cannot be inside a `Catch` block or a `Finally` block.</span></span>  
  
 <span data-ttu-id="ccd6d-133">Если `For Each` текст (за пределами функции итератора) вызывает исключение, `Catch` блок в функции итератора не выполняется, но `Finally` выполняется блок в функции итератора.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-133">If the `For Each` body (outside of the iterator function) throws an exception, a `Catch` block in the iterator function is not executed, but a `Finally` block in the iterator function is executed.</span></span> <span data-ttu-id="ccd6d-134">A `Catch` блок внутри функции итератора перехватывает только исключения, которые возникают внутри функции итератора.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-134">A `Catch` block inside an iterator function catches only exceptions that occur inside the iterator function.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="ccd6d-135">Техническая реализация</span><span class="sxs-lookup"><span data-stu-id="ccd6d-135">Technical Implementation</span></span>  
 <span data-ttu-id="ccd6d-136">Следующий код возвращает `IEnumerable (Of String)` из функции итератора и перебирает элементы `IEnumerable (Of String)`.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-136">The following code returns an `IEnumerable (Of String)` from an iterator function and then iterates through the elements of the `IEnumerable (Of String)`.</span></span>  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 <span data-ttu-id="ccd6d-137">Вызов `MyIteratorFunction` тело функции не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-137">The call to `MyIteratorFunction` doesn't execute the body of the function.</span></span> <span data-ttu-id="ccd6d-138">Вместо этого вызов возвращает `IEnumerable(Of String)` в переменную `elements`.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-138">Instead the call returns an `IEnumerable(Of String)` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="ccd6d-139">В итерации `For Each` цикл, <xref:System.Collections.IEnumerator.MoveNext%2A>метод вызывается для `elements`.</xref:System.Collections.IEnumerator.MoveNext%2A></span><span class="sxs-lookup"><span data-stu-id="ccd6d-139">On an iteration of the `For Each` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="ccd6d-140">Этот вызов выполняет тело `MyIteratorFunction` до достижения следующего оператора `Yield`.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-140">This call executes the body of `MyIteratorFunction` until the next `Yield` statement is reached.</span></span> <span data-ttu-id="ccd6d-141">`Yield` Инструкция возвращает выражение, определяющее значение не только `element` переменной для использования телом цикла, но также <xref:System.Collections.Generic.IEnumerator%601.Current%2A>Свойства элементов, который является `IEnumerable (Of String)`.</xref:System.Collections.Generic.IEnumerator%601.Current%2A></span><span class="sxs-lookup"><span data-stu-id="ccd6d-141">The `Yield` statement returns an expression that determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable (Of String)`.</span></span>  
  
 <span data-ttu-id="ccd6d-142">В каждой последующей итерации цикла `For Each` выполнение тела итератора продолжается с места остановки и при достижении оператора `Yield` оно снова останавливается.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-142">On each subsequent iteration of the `For Each` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `Yield` statement.</span></span> <span data-ttu-id="ccd6d-143">`For Each` Цикл завершается, когда конец функции итератора или `Return` или `Exit Function` к оператору.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-143">The `For Each` loop completes when the end of the iterator function or a `Return` or `Exit Function` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccd6d-144">Пример</span><span class="sxs-lookup"><span data-stu-id="ccd6d-144">Example</span></span>  
 <span data-ttu-id="ccd6d-145">В следующем примере `Yield` оператор, находящийся внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-145">The following example has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="ccd6d-146">Каждая итерация [для каждого](../../../visual-basic/language-reference/statements/for-each-next-statement.md) тела оператора в `Main` создает вызов `Power` функции итератора.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-146">Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="ccd6d-147">При каждом вызове функции итератора происходит переход к следующему выполнению оператора `Yield`, которое осуществляется во время следующей итерации цикла `For…Next`.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-147">Each call to the iterator function proceeds to the next execution of the `Yield` statement, which occurs during the next iteration of the `For…Next` loop.</span></span>  
  
 <span data-ttu-id="ccd6d-148">Возвращаемый тип метода итератора — <xref:System.Collections.Generic.IEnumerable%601>, тип интерфейса итератора.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="ccd6d-148">The return type of the iterator method is <xref:System.Collections.Generic.IEnumerable%601>, an iterator interface type.</span></span> <span data-ttu-id="ccd6d-149">При вызове метода итератора возвращается перечисляемый объект, содержащий степени числа.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-149">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 <span data-ttu-id="ccd6d-150">[!code-vb[VbVbalrStatements&#98;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ccd6d-150">[!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ccd6d-151">Пример</span><span class="sxs-lookup"><span data-stu-id="ccd6d-151">Example</span></span>  
 <span data-ttu-id="ccd6d-152">В следующем примере демонстрируется метод доступа `Get`, представляющий собой итератор.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-152">The following example demonstrates a `Get` accessor that is an iterator.</span></span> <span data-ttu-id="ccd6d-153">Объявление включает в себя `Iterator` модификатор.</span><span class="sxs-lookup"><span data-stu-id="ccd6d-153">The property declaration includes an `Iterator` modifier.</span></span>  
  
 <span data-ttu-id="ccd6d-154">[!code-vb[VbVbalrStatements&#99;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ccd6d-154">[!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]</span></span>  
  
 <span data-ttu-id="ccd6d-155">Дополнительные примеры см. в разделе [итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="ccd6d-155">For additional examples, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccd6d-156">Требования</span><span class="sxs-lookup"><span data-stu-id="ccd6d-156">Requirements</span></span>  
 [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs_dev11_long_md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ccd6d-157">См. также</span><span class="sxs-lookup"><span data-stu-id="ccd6d-157">See Also</span></span>  
 <span data-ttu-id="ccd6d-158">[Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) </span><span class="sxs-lookup"><span data-stu-id="ccd6d-158">[Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7) </span></span>  
<span data-ttu-id="ccd6d-159"> [Операторы](../../../visual-basic/language-reference/statements/index.md)</span><span class="sxs-lookup"><span data-stu-id="ccd6d-159"> [Statements](../../../visual-basic/language-reference/statements/index.md)</span></span>
