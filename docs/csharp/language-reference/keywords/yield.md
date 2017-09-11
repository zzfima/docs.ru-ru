---
title: "yield (справочник по C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- yield
- yield_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
caps.latest.revision: 46
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: eb55fd5b1ade48316516cda83633935abbf8dcf9
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="yield-c-reference"></a><span data-ttu-id="49a99-102">yield (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="49a99-102">yield (C# Reference)</span></span>
<span data-ttu-id="49a99-103">Использование в операторе ключевого слова `yield` означает, что метод, оператор или метод доступа `get`, в котором присутствует это ключевое слово, является итератором.</span><span class="sxs-lookup"><span data-stu-id="49a99-103">When you use the `yield` keyword in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="49a99-104">Использование `yield` для определения итератора исключает необходимость применения явного дополнительного класса (в котором содержится состояние перечисления; в качестве примера см. <xref:System.Collections.Generic.IEnumerator%601>) при реализации шаблонов <xref:System.Collections.IEnumerable> и <xref:System.Collections.IEnumerator> для пользовательского типа коллекции.</span><span class="sxs-lookup"><span data-stu-id="49a99-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>  
  
 <span data-ttu-id="49a99-105">В следующем примере показаны две формы оператора `yield`.</span><span class="sxs-lookup"><span data-stu-id="49a99-105">The following example shows the two forms of the `yield` statement.</span></span>  
  
```csharp  
yield return <expression>;  
yield break;  
```  
  
## <a name="remarks"></a><span data-ttu-id="49a99-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="49a99-106">Remarks</span></span>  
 <span data-ttu-id="49a99-107">Оператор `yield return` используется для возврата каждого элемента по одному.</span><span class="sxs-lookup"><span data-stu-id="49a99-107">You use a `yield return` statement to return each element one at a time.</span></span>  
  
 <span data-ttu-id="49a99-108">Метод итератора используется путем применения оператора [foreach](../../../csharp/language-reference/keywords/foreach-in.md) или запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="49a99-108">You consume an iterator method by using a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="49a99-109">Каждая итерация цикла `foreach` вызывает метод итератора.</span><span class="sxs-lookup"><span data-stu-id="49a99-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="49a99-110">При достижении в методе итератора оператора `yield return` возвращается `expression` и сохраняется текущее расположение в коде.</span><span class="sxs-lookup"><span data-stu-id="49a99-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="49a99-111">При следующем вызове функции итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="49a99-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>  
  
 <span data-ttu-id="49a99-112">Для завершения итерации можно использовать оператор `yield break`.</span><span class="sxs-lookup"><span data-stu-id="49a99-112">You can use a `yield break` statement to end the iteration.</span></span>  
  
 <span data-ttu-id="49a99-113">Дополнительные сведения об итераторах см. в разделе [Итераторы](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="49a99-113">For more information about iterators, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="49a99-114">Методы итератора и методы доступа get</span><span class="sxs-lookup"><span data-stu-id="49a99-114">Iterator Methods and get Accessors</span></span>  
 <span data-ttu-id="49a99-115">Объявление итератора должно соответствовать следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="49a99-115">The declaration of an iterator must meet the following requirements:</span></span>  
  
-   <span data-ttu-id="49a99-116">Возвращаемый тип должен быть <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> или <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="49a99-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>  
  
-   <span data-ttu-id="49a99-117">Объявление не должно содержать параметры [ref](../../../csharp/language-reference/keywords/ref.md) и [out](../../../csharp/language-reference/keywords/out.md).</span><span class="sxs-lookup"><span data-stu-id="49a99-117">The declaration can't have any [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out.md) parameters.</span></span>  
  
 <span data-ttu-id="49a99-118">Тип `yield` итератора, который возвращает <xref:System.Collections.IEnumerable> или <xref:System.Collections.IEnumerator>, — `object`.</span><span class="sxs-lookup"><span data-stu-id="49a99-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="49a99-119">Если итератор возвращает <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Collections.Generic.IEnumerator%601>, необходимо выполнить неявное преобразование из типа выражения в операторе `yield return` в параметр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="49a99-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>  
  
 <span data-ttu-id="49a99-120">Ниже указаны методы, в которых операторы `yield return` и `yield break` использовать нельзя.</span><span class="sxs-lookup"><span data-stu-id="49a99-120">You can't include a `yield return` or `yield break` statement in methods that have the following characteristics:</span></span>  
  
-   <span data-ttu-id="49a99-121">Анонимные методы.</span><span class="sxs-lookup"><span data-stu-id="49a99-121">Anonymous methods.</span></span> <span data-ttu-id="49a99-122">Дополнительные сведения см. в разделе [Анонимные методы](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span><span class="sxs-lookup"><span data-stu-id="49a99-122">For more information, see [Anonymous Methods](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md).</span></span>  
  
-   <span data-ttu-id="49a99-123">Методы, содержащие небезопасные блоки.</span><span class="sxs-lookup"><span data-stu-id="49a99-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="49a99-124">Дополнительные сведения см. в разделе [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="49a99-124">For more information, see [unsafe](../../../csharp/language-reference/keywords/unsafe.md).</span></span>  
  
## <a name="exception-handling"></a><span data-ttu-id="49a99-125">Обработка исключений</span><span class="sxs-lookup"><span data-stu-id="49a99-125">Exception Handling</span></span>  
 <span data-ttu-id="49a99-126">Оператор `yield return` нельзя размещать в блоке try-catch.</span><span class="sxs-lookup"><span data-stu-id="49a99-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="49a99-127">Оператор `yield return` можно размещать в блоке try оператора try-finally.</span><span class="sxs-lookup"><span data-stu-id="49a99-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>  
  
 <span data-ttu-id="49a99-128">Оператор `yield break` можно размещать в блоке try или catch, но не в блоке finally.</span><span class="sxs-lookup"><span data-stu-id="49a99-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>  
  
 <span data-ttu-id="49a99-129">Если тело оператора `foreach` (вне метода итератора) вызывает исключение, выполняется блок `finally` в методе итератора.</span><span class="sxs-lookup"><span data-stu-id="49a99-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>  
  
## <a name="technical-implementation"></a><span data-ttu-id="49a99-130">Техническая реализация</span><span class="sxs-lookup"><span data-stu-id="49a99-130">Technical Implementation</span></span>  
 <span data-ttu-id="49a99-131">В следующем коде возвращается объект `IEnumerable<string>` из метода итератора и затем выполняется перебор его элементов.</span><span class="sxs-lookup"><span data-stu-id="49a99-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>  
  
```csharp  
IEnumerable<string> elements = MyIteratorMethod();  
foreach (string element in elements)  
{  
   ...  
}  
```  
  
 <span data-ttu-id="49a99-132">При вызове `MyIteratorMethod` тело метода не выполняется.</span><span class="sxs-lookup"><span data-stu-id="49a99-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="49a99-133">Вместо этого вызов возвращает `IEnumerable<string>` в переменную `elements`.</span><span class="sxs-lookup"><span data-stu-id="49a99-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>  
  
 <span data-ttu-id="49a99-134">В итерации цикла `foreach` метод <xref:System.Collections.IEnumerator.MoveNext%2A> вызывается для `elements`.</span><span class="sxs-lookup"><span data-stu-id="49a99-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="49a99-135">Этот вызов выполняет тело `MyIteratorMethod` до достижения следующего оператора `yield return`.</span><span class="sxs-lookup"><span data-stu-id="49a99-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="49a99-136">Выражение, возвращаемое оператором `yield return`, определяет не только значение переменной `element` для использования телом цикла, но и свойство <xref:System.Collections.Generic.IEnumerator%601.Current%2A> элементов, представляющее собой `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="49a99-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of elements, which is an `IEnumerable<string>`.</span></span>  
  
 <span data-ttu-id="49a99-137">В каждой последующей итерации цикла `foreach` выполнение тела итератора продолжается с места остановки и при достижении оператора `yield return` оно снова останавливается.</span><span class="sxs-lookup"><span data-stu-id="49a99-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="49a99-138">Цикл `foreach` завершается при достижении конца метода итератора или оператора `yield break`.</span><span class="sxs-lookup"><span data-stu-id="49a99-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49a99-139">Пример</span><span class="sxs-lookup"><span data-stu-id="49a99-139">Example</span></span>  
 <span data-ttu-id="49a99-140">В следующем примере имеется оператор `yield return`, расположенный в цикле `for`.</span><span class="sxs-lookup"><span data-stu-id="49a99-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="49a99-141">Каждая итерация тела оператора `foreach` в `Process` создает вызов функции итератора `Power`.</span><span class="sxs-lookup"><span data-stu-id="49a99-141">Each iteration of the `foreach` statement body in `Process` creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="49a99-142">При каждом вызове функции итератора происходит переход к следующему выполнению оператора `yield return`, которое осуществляется во время следующей итерации цикла `for`.</span><span class="sxs-lookup"><span data-stu-id="49a99-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>  
  
 <span data-ttu-id="49a99-143">Возвращаемый тип метода итератора — <xref:System.Collections.IEnumerable> (тип интерфейса итератора).</span><span class="sxs-lookup"><span data-stu-id="49a99-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="49a99-144">При вызове метода итератора возвращается перечисляемый объект, содержащий степени числа.</span><span class="sxs-lookup"><span data-stu-id="49a99-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>  
  
 <span data-ttu-id="49a99-145">[!code-cs[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="49a99-145">[!code-cs[csrefKeywordsContextual#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="49a99-146">Пример</span><span class="sxs-lookup"><span data-stu-id="49a99-146">Example</span></span>  
 <span data-ttu-id="49a99-147">В следующем примере демонстрируется метод доступа `get`, представляющий собой итератор.</span><span class="sxs-lookup"><span data-stu-id="49a99-147">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="49a99-148">В этом примере каждый оператор `yield return` возвращает экземпляр пользовательского класса.</span><span class="sxs-lookup"><span data-stu-id="49a99-148">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>  
  
 <span data-ttu-id="49a99-149">[!code-cs[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="49a99-149">[!code-cs[csrefKeywordsContextual#21](../../../csharp/language-reference/keywords/codesnippet/CSharp/yield_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="49a99-150">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="49a99-150">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="49a99-151">См. также</span><span class="sxs-lookup"><span data-stu-id="49a99-151">See Also</span></span>  
 <span data-ttu-id="49a99-152">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="49a99-152">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="49a99-153">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="49a99-153">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="49a99-154">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="49a99-154">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 [<span data-ttu-id="49a99-155">Итераторы</span><span class="sxs-lookup"><span data-stu-id="49a99-155">Iterators</span></span>](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)

