---
title: "ref (Справочник по C#)"
ms.date: 03/06/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 427045317e9d7d0fe3435a486b9f761908ab5e78
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2018
---
# <a name="ref-c-reference"></a><span data-ttu-id="7edba-102">ref (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="7edba-102">ref (C# Reference)</span></span>

<span data-ttu-id="7edba-103">Ключевое слово `ref` указывает на значение, переданное по ссылке.</span><span class="sxs-lookup"><span data-stu-id="7edba-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="7edba-104">Оно используется в трех разных контекстах:</span><span class="sxs-lookup"><span data-stu-id="7edba-104">It is used in three different contexts:</span></span> 

- <span data-ttu-id="7edba-105">В сигнатуре и вызове метода для передачи аргумента в метод по ссылке.</span><span class="sxs-lookup"><span data-stu-id="7edba-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="7edba-106">Дополнительные сведения см. в разделе [Передача аргумента по ссылке](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="7edba-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>

- <span data-ttu-id="7edba-107">В сигнатуре метода для возврата значения вызывающему объекту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="7edba-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="7edba-108">Дополнительные сведения см. в разделе [Возвращаемые ссылочные значения](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="7edba-108">See [Reference return values](#reference-return-values) for more information.</span></span>

- <span data-ttu-id="7edba-109">В теле элемента для указания на то, что возвращаемые ссылочные значения хранятся локально в виде ссылки, которая может быть изменена вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="7edba-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify.</span></span> <span data-ttu-id="7edba-110">Дополнительные сведения см. в разделе [Ссылочные локальные переменные](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="7edba-110">See [Ref locals](#ref-locals) for more information.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="7edba-111">Передача аргументов по ссылке</span><span class="sxs-lookup"><span data-stu-id="7edba-111">Passing an argument by reference</span></span>

<span data-ttu-id="7edba-112">При использовании в списке параметров метода ключевое слово `ref` указывает на то, что аргумент передается по ссылке, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="7edba-112">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="7edba-113">Эффект передачи по ссылке в том, что все изменения аргумента в вызываемом методе отражаются в вызывающем методе.</span><span class="sxs-lookup"><span data-stu-id="7edba-113">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="7edba-114">Например, если вызывающий объект передает выражение локальной переменной или выражение доступа к элементу массива и вызванный метод заменяет объект, на который ссылается параметр ref, то локальная переменная или элемент массива взывающего объекта будет ссылаться на новый объект после возврата из метода.</span><span class="sxs-lookup"><span data-stu-id="7edba-114">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
>  <span data-ttu-id="7edba-115">Не следует путать понятие передачи по ссылке с понятием ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="7edba-115">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="7edba-116">Эти два понятия не совпадают.</span><span class="sxs-lookup"><span data-stu-id="7edba-116">The two concepts are not the same.</span></span> <span data-ttu-id="7edba-117">Параметр метода может быть изменен с помощью `ref` независимо от того, принадлежит ли он к типу значения или ссылочному типу.</span><span class="sxs-lookup"><span data-stu-id="7edba-117">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="7edba-118">При передаче по ссылке упаковка-преобразование типа значения не производится.</span><span class="sxs-lookup"><span data-stu-id="7edba-118">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="7edba-119">Для использования параметра `ref` и при определении метода, и при вызове метода следует явно использовать ключевое слово `ref`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7edba-119">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="7edba-120">Аргумент, передаваемый в параметр `ref` или `in`, нужно инициализировать перед передачей.</span><span class="sxs-lookup"><span data-stu-id="7edba-120">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="7edba-121">В этом заключается отличие от параметров [out](out-parameter-modifier.md), аргументы которых не требуют явной инициализации перед передачей.</span><span class="sxs-lookup"><span data-stu-id="7edba-121">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="7edba-122">Члены класса не могут иметь сигнатуры, отличающихся только `ref`, `in` или `out`.</span><span class="sxs-lookup"><span data-stu-id="7edba-122">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="7edba-123">Если единственное различие между двумя членами типа состоит в том, что один из них имеет параметр `ref`, а второй — параметр `out` или `in`, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="7edba-123">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="7edba-124">Например, следующий код не будет компилироваться.</span><span class="sxs-lookup"><span data-stu-id="7edba-124">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
<span data-ttu-id="7edba-125">Но методы можно перегружать, если один метод имеет параметр `ref`, `in` или `out`, а другой — параметр по значению, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="7edba-125">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="7edba-126">В других ситуациях, требующих соответствия сигнатур, таких как скрытие или переопределение, `in`, `ref` и `out` являются частью сигнатуры и не соответствуют друг другу.</span><span class="sxs-lookup"><span data-stu-id="7edba-126">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="7edba-127">Свойства не являются переменными.</span><span class="sxs-lookup"><span data-stu-id="7edba-127">Properties are not variables.</span></span> <span data-ttu-id="7edba-128">Они являются методами и не могут быть переданы в параметр `ref`.</span><span class="sxs-lookup"><span data-stu-id="7edba-128">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="7edba-129">Сведения о передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="7edba-129">For information about how to pass arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="7edba-130">Ключевые слова `ref`, `in` и `out` запрещено использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="7edba-130">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="7edba-131">Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="7edba-131">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
- <span data-ttu-id="7edba-132">Методы итератора, которые включают оператор [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="7edba-132">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="7edba-133">Пример передачи аргументов по ссылке</span><span class="sxs-lookup"><span data-stu-id="7edba-133">Passing an argument by reference: An example</span></span>

<span data-ttu-id="7edba-134">В предыдущих примерах типы значений передаются по ссылке.</span><span class="sxs-lookup"><span data-stu-id="7edba-134">The previous examples pass value types by reference.</span></span> <span data-ttu-id="7edba-135">Также можно использовать ключевое слово `ref` для передачи ссылочных типов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="7edba-135">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="7edba-136">Передача ссылочного типа по ссылке позволяет вызываемому методу заменять объект, на который указывает ссылочный параметр в вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="7edba-136">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="7edba-137">Место хранения объекта передается методу в качестве значения ссылочного параметра.</span><span class="sxs-lookup"><span data-stu-id="7edba-137">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="7edba-138">Если изменить место хранения параметра (с указанием на новый объект), необходимо изменить место хранения, на который ссылается вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="7edba-138">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="7edba-139">В следующем примере экземпляр ссылочного типа передается как параметр `ref`.</span><span class="sxs-lookup"><span data-stu-id="7edba-139">The following example passes an instance of a reference type as a `ref` parameter.</span></span>   
  
[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="7edba-140">Дополнительные сведения о передаче ссылочных типов по значению и по ссылке см. в разделе [Передача параметров ссылочного типа](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7edba-140">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="7edba-141">Возвращаемые ссылочные значения</span><span class="sxs-lookup"><span data-stu-id="7edba-141">Reference return values</span></span>

<span data-ttu-id="7edba-142">Возвращаемые ссылочные значения — это значения, которые метод возвращает вызывающему объекту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="7edba-142">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="7edba-143">Это значит, что вызывающий объект может изменять значение, возвращаемое методом, и это изменение будет отражаться в состоянии объекта, содержащего этот метод.</span><span class="sxs-lookup"><span data-stu-id="7edba-143">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span> 

<span data-ttu-id="7edba-144">Возвращаемое ссылочное значение определяется с помощью ключевого слова `ref`:</span><span class="sxs-lookup"><span data-stu-id="7edba-144">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="7edba-145">В сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="7edba-145">In the method signature.</span></span> <span data-ttu-id="7edba-146">Например, следующая сигнатура указывает, что метод `GetCurrentPrice` возвращает значение <xref:System.Decimal> по ссылке.</span><span class="sxs-lookup"><span data-stu-id="7edba-146">For example, the following method signature inidicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

   ```csharp
   public ref decimal GetCurrentValue()
   ``` 
- <span data-ttu-id="7edba-147">Между токеном `return` и переменной, возвращенной в инструкции `return` в методе.</span><span class="sxs-lookup"><span data-stu-id="7edba-147">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="7edba-148">Пример:</span><span class="sxs-lookup"><span data-stu-id="7edba-148">For example:</span></span>
 
   ```csharp
   return ref DecimalArray[0];
   ``` 

<span data-ttu-id="7edba-149">Чтобы вызывающий объект имел возможность изменять состояние объекта, возвращаемое ссылочное значение должно храниться в переменной, которая явно определена как [ссылочная локальная переменная](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="7edba-149">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span> 

<span data-ttu-id="7edba-150">Пример см. в разделе [Пример использования возвращаемых ссылочных значений и ссылочных локальных переменных](#a-ref-returns-and-ref-locals-example)</span><span class="sxs-lookup"><span data-stu-id="7edba-150">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="7edba-151">Ссылочные локальные переменные</span><span class="sxs-lookup"><span data-stu-id="7edba-151">Ref locals</span></span>

<span data-ttu-id="7edba-152">Ссылочная локальная переменная задает ссылку на значения, возвращаемые с помощью `return ref`.</span><span class="sxs-lookup"><span data-stu-id="7edba-152">A ref local variable is used to refer to values returned using `return ref`.</span></span>  <span data-ttu-id="7edba-153">После инициализации ссылочной локальной переменной необходимо присвоить ей возвращаемое ссылочное значение.</span><span class="sxs-lookup"><span data-stu-id="7edba-153">A ref local variable must be initialized and assigned to a ref return value.</span></span> <span data-ttu-id="7edba-154">Любые изменения в значении ссылочной локальной переменной отражаются в состоянии объекта, метод которого возвращает значение по ссылке.</span><span class="sxs-lookup"><span data-stu-id="7edba-154">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="7edba-155">Ссылочная локальная переменная определяется с помощью ключевого слова `ref` перед объявлением переменной, а также непосредственно перед вызовом метода, который возвращает значение по ссылке.</span><span class="sxs-lookup"><span data-stu-id="7edba-155">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span> 

<span data-ttu-id="7edba-156">Например, следующая инструкция определяет значение ссылочной локальной переменной, которое возвращается методом `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="7edba-156">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="7edba-157">Обратите внимание, что ключевое слово `ref` необходимо использовать в обоих местах. В противном случае возникает ошибка компилятора CS8172, "Невозможно инициализировать значением переменную по ссылке".</span><span class="sxs-lookup"><span data-stu-id="7edba-157">Note that the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="7edba-158">Пример использования возвращаемых ссылочных значений и ссылочных локальных переменных</span><span class="sxs-lookup"><span data-stu-id="7edba-158">A ref returns and ref locals example</span></span>

<span data-ttu-id="7edba-159">В следующем примере определяется класс `Book`, содержащий два поля <xref:System.String>: `Title` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="7edba-159">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="7edba-160">Также определяется класс `BookCollection`, который включает частный массив объектов `Book`.</span><span class="sxs-lookup"><span data-stu-id="7edba-160">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="7edba-161">Отдельные объекты книг возвращаются по ссылке путем вызова метода `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="7edba-161">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="7edba-162">Если вызывающий объект сохраняет значение, возвращаемое методом `GetBookByTitle`, в качестве ссылочной локальной переменной, изменения, которые этот объект вносит в возвращаемое значение, отражаются в объекте `BookCollection`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7edba-162">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="7edba-163">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7edba-163">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7edba-164">См. также</span><span class="sxs-lookup"><span data-stu-id="7edba-164">See Also</span></span>  
 [<span data-ttu-id="7edba-165">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="7edba-165">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7edba-166">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7edba-166">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7edba-167">Передача параметров</span><span class="sxs-lookup"><span data-stu-id="7edba-167">Passing Parameters</span></span>](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md)  
 [<span data-ttu-id="7edba-168">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="7edba-168">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)  
 [<span data-ttu-id="7edba-169">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="7edba-169">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
