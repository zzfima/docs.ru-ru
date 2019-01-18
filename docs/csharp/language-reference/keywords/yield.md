---
title: Справочник по C#. Контекстное ключевое слово yield
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: cfeef1d84a443163f4bbeda863682335d9cd1fcd
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222628"
---
# <a name="yield-c-reference"></a><span data-ttu-id="53880-102">yield (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="53880-102">yield (C# Reference)</span></span>

<span data-ttu-id="53880-103">Использование в операторе [контекстного ключевого](index.md#contextual-keywords) слова `yield` означает, что метод, оператор или метод доступа `get`, в котором присутствует это ключевое слово, является итератором.</span><span class="sxs-lookup"><span data-stu-id="53880-103">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="53880-104">Использование `yield` для определения итератора исключает необходимость применения явного дополнительного класса (в котором содержится состояние перечисления; в качестве примера см. <xref:System.Collections.Generic.IEnumerator%601>) при реализации шаблонов <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> для пользовательского типа коллекции.</span><span class="sxs-lookup"><span data-stu-id="53880-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="53880-105">В следующем примере показаны две формы оператора `yield`.</span><span class="sxs-lookup"><span data-stu-id="53880-105">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="53880-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="53880-106">Remarks</span></span>

<span data-ttu-id="53880-107">Оператор `yield return` используется для возврата каждого элемента по одному.</span><span class="sxs-lookup"><span data-stu-id="53880-107">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="53880-108">Метод итератора используется путем применения оператора [foreach](foreach-in.md) или запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="53880-108">You consume an iterator method by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="53880-109">Каждая итерация цикла `foreach` вызывает метод итератора.</span><span class="sxs-lookup"><span data-stu-id="53880-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="53880-110">При достижении в методе итератора оператора `yield return` возвращается `expression` и сохраняется текущее расположение в коде.</span><span class="sxs-lookup"><span data-stu-id="53880-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="53880-111">При следующем вызове функции итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="53880-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="53880-112">Для завершения итерации можно использовать оператор `yield break`.</span><span class="sxs-lookup"><span data-stu-id="53880-112">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="53880-113">Дополнительные сведения об итераторах см. в разделе [Итераторы](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="53880-113">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="53880-114">Методы итератора и методы доступа get</span><span class="sxs-lookup"><span data-stu-id="53880-114">Iterator methods and get accessors</span></span>

<span data-ttu-id="53880-115">Объявление итератора должно соответствовать следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="53880-115">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="53880-116">Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="53880-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="53880-117">Объявление не должно содержать параметры [in](in-parameter-modifier.md), [ref](ref.md) или [out](out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="53880-117">The declaration can't have any [in](in-parameter-modifier.md) [ref](ref.md) or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="53880-118">Тип `yield` итератора, который возвращает <xref:System.Collections.IEnumerable> или <xref:System.Collections.IEnumerator>, — `object`.</span><span class="sxs-lookup"><span data-stu-id="53880-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="53880-119">Если итератор возвращает <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Collections.Generic.IEnumerator%601>, необходимо выполнить неявное преобразование из типа выражения в операторе `yield return` в параметр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="53880-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="53880-120">Ниже указаны методы, в которых операторы `yield return` и `yield break` использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="53880-120">You can't include a `yield return` or `yield break` statement in methods that have the following characteristics:</span></span>

- <span data-ttu-id="53880-121">Анонимные методы.</span><span class="sxs-lookup"><span data-stu-id="53880-121">Anonymous methods.</span></span> <span data-ttu-id="53880-122">Дополнительные сведения см. в разделе [Анонимные методы](../../programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="53880-122">For more information, see [Anonymous Methods](../../programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>

- <span data-ttu-id="53880-123">Методы, содержащие небезопасные блоки.</span><span class="sxs-lookup"><span data-stu-id="53880-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="53880-124">Дополнительные сведения см. в разделе [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="53880-124">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="53880-125">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="53880-125">Exception handling</span></span>

<span data-ttu-id="53880-126">Оператор `yield return` нельзя размещать в блоке try-catch.</span><span class="sxs-lookup"><span data-stu-id="53880-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="53880-127">Оператор `yield return` можно размещать в блоке try оператора try-finally.</span><span class="sxs-lookup"><span data-stu-id="53880-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="53880-128">Оператор `yield break` можно размещать в блоке try или catch, но не в блоке finally.</span><span class="sxs-lookup"><span data-stu-id="53880-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="53880-129">Если тело оператора `foreach` (вне метода итератора) вызывает исключение, выполняется блок `finally` в методе итератора.</span><span class="sxs-lookup"><span data-stu-id="53880-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="53880-130">Техническая реализация</span><span class="sxs-lookup"><span data-stu-id="53880-130">Technical implementation</span></span>

<span data-ttu-id="53880-131">В следующем коде возвращается объект `IEnumerable<string>` из метода итератора и затем выполняется перебор его элементов.</span><span class="sxs-lookup"><span data-stu-id="53880-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="53880-132">При вызове `MyIteratorMethod` тело метода не выполняется.</span><span class="sxs-lookup"><span data-stu-id="53880-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="53880-133">Вместо этого вызов возвращает `IEnumerable<string>` в переменную `elements`.</span><span class="sxs-lookup"><span data-stu-id="53880-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="53880-134">В итерации цикла `foreach` метод <xref:System.Collections.IEnumerator.MoveNext%2A> вызывается для `elements`.</span><span class="sxs-lookup"><span data-stu-id="53880-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="53880-135">Этот вызов выполняет тело `MyIteratorMethod` до достижения следующего оператора `yield return`.</span><span class="sxs-lookup"><span data-stu-id="53880-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="53880-136">Выражение, возвращаемое оператором `yield return`, определяет не только значение переменной `element` для использования телом цикла, но и свойство <xref:System.Collections.Generic.IEnumerator%601.Current%2A> объекта `elements`, представляющее собой `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="53880-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="53880-137">В каждой последующей итерации цикла `foreach` выполнение тела итератора продолжается с места остановки и при достижении оператора `yield return` оно снова останавливается.</span><span class="sxs-lookup"><span data-stu-id="53880-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="53880-138">Цикл `foreach` завершается при достижении конца метода итератора или оператора `yield break`.</span><span class="sxs-lookup"><span data-stu-id="53880-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="53880-139">Пример</span><span class="sxs-lookup"><span data-stu-id="53880-139">Example</span></span>

<span data-ttu-id="53880-140">В следующем примере имеется оператор `yield return`, расположенный в цикле `for`.</span><span class="sxs-lookup"><span data-stu-id="53880-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="53880-141">Каждая итерация тела оператора `foreach` в методе `Main` создает вызов функции итератора `Power`.</span><span class="sxs-lookup"><span data-stu-id="53880-141">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="53880-142">При каждом вызове функции итератора происходит переход к следующему выполнению оператора `yield return`, которое осуществляется во время следующей итерации цикла `for`.</span><span class="sxs-lookup"><span data-stu-id="53880-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="53880-143">Возвращаемый тип метода итератора — <xref:System.Collections.IEnumerable> (тип интерфейса итератора).</span><span class="sxs-lookup"><span data-stu-id="53880-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="53880-144">При вызове метода итератора возвращается перечисляемый объект, содержащий степени числа.</span><span class="sxs-lookup"><span data-stu-id="53880-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="53880-145">Пример</span><span class="sxs-lookup"><span data-stu-id="53880-145">Example</span></span>

<span data-ttu-id="53880-146">В следующем примере демонстрируется метод доступа `get`, представляющий собой итератор.</span><span class="sxs-lookup"><span data-stu-id="53880-146">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="53880-147">В этом примере каждый оператор `yield return` возвращает экземпляр пользовательского класса.</span><span class="sxs-lookup"><span data-stu-id="53880-147">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="53880-148">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="53880-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="53880-149">См. также</span><span class="sxs-lookup"><span data-stu-id="53880-149">See also</span></span>

- [<span data-ttu-id="53880-150">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="53880-150">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="53880-151">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="53880-151">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="53880-152">foreach, in</span><span class="sxs-lookup"><span data-stu-id="53880-152">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="53880-153">Итераторы</span><span class="sxs-lookup"><span data-stu-id="53880-153">Iterators</span></span>](../../iterators.md)