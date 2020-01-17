---
title: Справочник по C#. Контекстное ключевое слово yield
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: e3c9e37e7b543eaddae837a85604c4ba91fbc744
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712784"
---
# <a name="yield-c-reference"></a><span data-ttu-id="c350a-102">yield (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="c350a-102">yield (C# Reference)</span></span>

<span data-ttu-id="c350a-103">Использование в операторе [контекстного ключевого слова](index.md#contextual-keywords) `yield` означает, что метод, оператор или метод доступа `get`, в котором присутствует это ключевое слово, является итератором.</span><span class="sxs-lookup"><span data-stu-id="c350a-103">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="c350a-104">Использование `yield` для определения итератора исключает необходимость применения явного дополнительного класса (в котором содержится состояние перечисления; в качестве примера см. <xref:System.Collections.Generic.IEnumerator%601>) при реализации шаблонов <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> для пользовательского типа коллекции.</span><span class="sxs-lookup"><span data-stu-id="c350a-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="c350a-105">В следующем примере показаны две формы оператора `yield`.</span><span class="sxs-lookup"><span data-stu-id="c350a-105">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="c350a-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c350a-106">Remarks</span></span>

<span data-ttu-id="c350a-107">Оператор `yield return` используется для возврата каждого элемента по одному.</span><span class="sxs-lookup"><span data-stu-id="c350a-107">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="c350a-108">Последовательность, которая возвращается после выполнения метода итератора, можно использовать с помощью оператора [foreach](foreach-in.md) или запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="c350a-108">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="c350a-109">Каждая итерация цикла `foreach` вызывает метод итератора.</span><span class="sxs-lookup"><span data-stu-id="c350a-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="c350a-110">При достижении в методе итератора оператора `yield return` возвращается `expression` и сохраняется текущее расположение в коде.</span><span class="sxs-lookup"><span data-stu-id="c350a-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="c350a-111">При следующем вызове функции итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="c350a-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="c350a-112">Для завершения итерации можно использовать оператор `yield break`.</span><span class="sxs-lookup"><span data-stu-id="c350a-112">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="c350a-113">Дополнительные сведения об итераторах см. в разделе [Итераторы](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="c350a-113">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="c350a-114">Методы итератора и методы доступа get</span><span class="sxs-lookup"><span data-stu-id="c350a-114">Iterator methods and get accessors</span></span>

<span data-ttu-id="c350a-115">Объявление итератора должно соответствовать следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="c350a-115">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="c350a-116">Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="c350a-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="c350a-117">Объявление не должно содержать параметры [in](in-parameter-modifier.md), [ref](ref.md) или [out](out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="c350a-117">The declaration can't have any [in](in-parameter-modifier.md) [ref](ref.md) or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="c350a-118">Тип `yield` итератора, который возвращает <xref:System.Collections.IEnumerable> или <xref:System.Collections.IEnumerator>, — `object`.</span><span class="sxs-lookup"><span data-stu-id="c350a-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="c350a-119">Если итератор возвращает <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Collections.Generic.IEnumerator%601>, необходимо выполнить неявное преобразование из типа выражения в операторе `yield return` в параметр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="c350a-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="c350a-120">Нельзя включать инструкцию `yield return` или `yield break`:</span><span class="sxs-lookup"><span data-stu-id="c350a-120">You can't include a `yield return` or `yield break` statement in:</span></span>

- <span data-ttu-id="c350a-121">[Лямбда-выражения](../../programming-guide/statements-expressions-operators/lambda-expressions.md) и [анонимные методы](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="c350a-121">[Lambda expressions](../../programming-guide/statements-expressions-operators/lambda-expressions.md) and [anonymous methods](../operators/delegate-operator.md).</span></span>

- <span data-ttu-id="c350a-122">Методы, содержащие небезопасные блоки.</span><span class="sxs-lookup"><span data-stu-id="c350a-122">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="c350a-123">Дополнительные сведения см. в разделе [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="c350a-123">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="c350a-124">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="c350a-124">Exception handling</span></span>

<span data-ttu-id="c350a-125">Оператор `yield return` нельзя размещать в блоке try-catch.</span><span class="sxs-lookup"><span data-stu-id="c350a-125">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="c350a-126">Оператор `yield return` можно размещать в блоке try оператора try-finally.</span><span class="sxs-lookup"><span data-stu-id="c350a-126">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="c350a-127">Оператор `yield break` можно размещать в блоке try или catch, но не в блоке finally.</span><span class="sxs-lookup"><span data-stu-id="c350a-127">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="c350a-128">Если тело оператора `foreach` (вне метода итератора) вызывает исключение, выполняется блок `finally` в методе итератора.</span><span class="sxs-lookup"><span data-stu-id="c350a-128">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="c350a-129">Техническая реализация</span><span class="sxs-lookup"><span data-stu-id="c350a-129">Technical implementation</span></span>

<span data-ttu-id="c350a-130">В следующем коде возвращается объект `IEnumerable<string>` из метода итератора и затем выполняется перебор его элементов.</span><span class="sxs-lookup"><span data-stu-id="c350a-130">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="c350a-131">При вызове `MyIteratorMethod` тело метода не выполняется.</span><span class="sxs-lookup"><span data-stu-id="c350a-131">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="c350a-132">Вместо этого вызов возвращает `IEnumerable<string>` в переменную `elements`.</span><span class="sxs-lookup"><span data-stu-id="c350a-132">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="c350a-133">В итерации цикла `foreach` метод <xref:System.Collections.IEnumerator.MoveNext%2A> вызывается для `elements`.</span><span class="sxs-lookup"><span data-stu-id="c350a-133">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="c350a-134">Этот вызов выполняет тело `MyIteratorMethod` до достижения следующего оператора `yield return`.</span><span class="sxs-lookup"><span data-stu-id="c350a-134">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="c350a-135">Выражение, возвращаемое оператором `yield return`, определяет не только значение переменной `element` для использования телом цикла, но и свойство <xref:System.Collections.Generic.IEnumerator%601.Current%2A> объекта `elements`, представляющее собой `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="c350a-135">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="c350a-136">В каждой последующей итерации цикла `foreach` выполнение тела итератора продолжается с места остановки и при достижении оператора `yield return` оно снова останавливается.</span><span class="sxs-lookup"><span data-stu-id="c350a-136">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="c350a-137">Цикл `foreach` завершается при достижении конца метода итератора или оператора `yield break`.</span><span class="sxs-lookup"><span data-stu-id="c350a-137">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="c350a-138">Пример</span><span class="sxs-lookup"><span data-stu-id="c350a-138">Example</span></span>

<span data-ttu-id="c350a-139">В следующем примере имеется оператор `yield return`, расположенный в цикле `for`.</span><span class="sxs-lookup"><span data-stu-id="c350a-139">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="c350a-140">Каждая итерация тела оператора `foreach` в методе `Main` создает вызов функции итератора `Power`.</span><span class="sxs-lookup"><span data-stu-id="c350a-140">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="c350a-141">При каждом вызове функции итератора происходит переход к следующему выполнению оператора `yield return`, которое осуществляется во время следующей итерации цикла `for`.</span><span class="sxs-lookup"><span data-stu-id="c350a-141">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="c350a-142">Возвращаемый тип метода итератора — <xref:System.Collections.IEnumerable> (тип интерфейса итератора).</span><span class="sxs-lookup"><span data-stu-id="c350a-142">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="c350a-143">При вызове метода итератора возвращается перечисляемый объект, содержащий степени числа.</span><span class="sxs-lookup"><span data-stu-id="c350a-143">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="c350a-144">Пример</span><span class="sxs-lookup"><span data-stu-id="c350a-144">Example</span></span>

<span data-ttu-id="c350a-145">В следующем примере демонстрируется метод доступа `get`, представляющий собой итератор.</span><span class="sxs-lookup"><span data-stu-id="c350a-145">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="c350a-146">В этом примере каждый оператор `yield return` возвращает экземпляр пользовательского класса.</span><span class="sxs-lookup"><span data-stu-id="c350a-146">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="c350a-147">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="c350a-147">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c350a-148">См. также</span><span class="sxs-lookup"><span data-stu-id="c350a-148">See also</span></span>

- [<span data-ttu-id="c350a-149">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="c350a-149">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="c350a-150">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c350a-150">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c350a-151">foreach, in</span><span class="sxs-lookup"><span data-stu-id="c350a-151">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="c350a-152">Итераторы</span><span class="sxs-lookup"><span data-stu-id="c350a-152">Iterators</span></span>](../../iterators.md)
