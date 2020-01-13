---
title: Справочник по C#. Ключевое слово ref
ms.date: 03/26/2019
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 25c74317ce9033ef10735ee0087f275632b6bd17
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715187"
---
# <a name="ref-c-reference"></a><span data-ttu-id="b7b4a-102">ref (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="b7b4a-102">ref (C# Reference)</span></span>

<span data-ttu-id="b7b4a-103">Ключевое слово `ref` указывает на значение, переданное по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="b7b4a-104">Оно используется в четырех разных контекстах:</span><span class="sxs-lookup"><span data-stu-id="b7b4a-104">It is used in four different contexts:</span></span>

- <span data-ttu-id="b7b4a-105">В сигнатуре и вызове метода для передачи аргумента в метод по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="b7b4a-106">Дополнительные сведения см. в статье о [передаче аргументов по ссылке](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-106">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="b7b4a-107">В сигнатуре метода для возврата значения вызывающему объекту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="b7b4a-108">Дополнительные сведения см. в разделе [Значения, возвращаемые по ссылке](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-108">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="b7b4a-109">В теле элемента для указания на то, что возвращаемые ссылочные значения хранятся локально в виде ссылки, которая может быть изменена вызывающим объектом, или, в общем случае, что локальная переменная обращается к другому значению по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="b7b4a-110">Дополнительные сведения см. в статье о [ссылочных локальных переменных](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-110">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="b7b4a-111">В объявлении `struct`, чтобы объявить `ref struct` или `readonly ref struct`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-111">In a `struct` declaration to declare a `ref struct` or a `readonly ref struct`.</span></span> <span data-ttu-id="b7b4a-112">Дополнительные сведения см. в статье о [типах ссылочных структур](#ref-struct-types).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-112">For more information, see [ref struct types](#ref-struct-types).</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="b7b4a-113">Передача аргументов по ссылке</span><span class="sxs-lookup"><span data-stu-id="b7b4a-113">Passing an argument by reference</span></span>

<span data-ttu-id="b7b4a-114">При использовании в списке параметров метода ключевое слово `ref` указывает на то, что аргумент передается по ссылке, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-114">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="b7b4a-115">Ключевое слово `ref` позволяет превратить этот формальный параметр в псевдоним для аргумента, который должен представлять собой переменную.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-115">The `ref` keyword makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="b7b4a-116">Другими словами, любая операция в параметре осуществляется с аргументом.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-116">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="b7b4a-117">Например, если вызывающий объект передает выражение локальной переменной или выражение доступа к элементу массива и вызванный метод заменяет объект, на который ссылается параметр ref, то локальная переменная или элемент массива взывающего объекта будет ссылаться на новый объект после возврата из метода.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-117">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="b7b4a-118">Не следует путать понятие передачи по ссылке с понятием ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-118">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="b7b4a-119">Эти два понятия не совпадают.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-119">The two concepts are not the same.</span></span> <span data-ttu-id="b7b4a-120">Параметр метода может быть изменен с помощью `ref` независимо от того, принадлежит ли он к типу значения или ссылочному типу.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-120">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="b7b4a-121">При передаче по ссылке упаковка-преобразование типа значения не производится.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-121">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="b7b4a-122">Для использования параметра `ref` и при определении метода, и при вызове метода следует явно использовать ключевое слово `ref`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-122">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="b7b4a-123">Аргумент, передаваемый в параметр `ref` или `in`, нужно инициализировать перед передачей.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-123">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="b7b4a-124">В этом заключается отличие от параметров [out](out-parameter-modifier.md), аргументы которых не требуют явной инициализации перед передачей.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-124">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="b7b4a-125">Члены класса не могут иметь сигнатуры, отличающихся только `ref`, `in` или `out`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-125">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="b7b4a-126">Если единственное различие между двумя членами типа состоит в том, что один из них имеет параметр `ref`, а второй — параметр `out` или `in`, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-126">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="b7b4a-127">Например, следующий код не будет компилироваться.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-127">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded 
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="b7b4a-128">Но методы можно перегружать, если один метод имеет параметр `ref`, `in` или `out`, а другой — параметр по значению, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-128">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="b7b4a-129">В других ситуациях, требующих соответствия сигнатур, таких как скрытие или переопределение, `in`, `ref` и `out` являются частью сигнатуры и не соответствуют друг другу.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-129">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="b7b4a-130">Свойства не являются переменными.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-130">Properties are not variables.</span></span> <span data-ttu-id="b7b4a-131">Они являются методами и не могут быть переданы в параметр `ref`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-131">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="b7b4a-132">Ключевые слова `ref`, `in` и `out` запрещено использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-132">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="b7b4a-133">Асинхронные методы, которые определяются с помощью модификатора [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-133">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="b7b4a-134">Методы итератора, которые включают оператор [yield return](yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-134">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>  

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="b7b4a-135">Передача аргументов по ссылке. Пример</span><span class="sxs-lookup"><span data-stu-id="b7b4a-135">Passing an argument by reference: An example</span></span>

<span data-ttu-id="b7b4a-136">В предыдущих примерах типы значений передаются по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-136">The previous examples pass value types by reference.</span></span> <span data-ttu-id="b7b4a-137">Также можно использовать ключевое слово `ref` для передачи ссылочных типов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-137">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="b7b4a-138">Передача ссылочного типа по ссылке позволяет вызываемому методу заменять объект, на который указывает ссылочный параметр в вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-138">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="b7b4a-139">Место хранения объекта передается методу в качестве значения ссылочного параметра.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-139">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="b7b4a-140">Если изменить место хранения параметра (с указанием на новый объект), необходимо изменить место хранения, на который ссылается вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-140">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="b7b4a-141">В следующем примере экземпляр ссылочного типа передается как параметр `ref`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-141">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="b7b4a-142">Дополнительные сведения о передаче ссылочных типов по значению и по ссылке см. в разделе [Передача параметров ссылочного типа](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-142">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="b7b4a-143">Возвращаемые ссылочные значения</span><span class="sxs-lookup"><span data-stu-id="b7b4a-143">Reference return values</span></span>

<span data-ttu-id="b7b4a-144">Возвращаемые ссылочные значения — это значения, которые метод возвращает вызывающему объекту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-144">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="b7b4a-145">Это значит, что вызывающий объект может изменять значение, возвращаемое методом, и это изменение будет отражаться в состоянии объекта, содержащего этот метод.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-145">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span>

<span data-ttu-id="b7b4a-146">Возвращаемое ссылочное значение определяется с помощью ключевого слова `ref`:</span><span class="sxs-lookup"><span data-stu-id="b7b4a-146">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="b7b4a-147">В сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-147">In the method signature.</span></span> <span data-ttu-id="b7b4a-148">Например, следующая сигнатура указывает, что метод `GetCurrentPrice` возвращает значение <xref:System.Decimal> по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-148">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="b7b4a-149">Между токеном `return` и переменной, возвращенной в инструкции `return` в методе.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-149">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="b7b4a-150">Пример:</span><span class="sxs-lookup"><span data-stu-id="b7b4a-150">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="b7b4a-151">Чтобы вызывающий объект имел возможность изменять состояние объекта, возвращаемое ссылочное значение должно храниться в переменной, которая явно определена как [ссылочная локальная переменная](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-151">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="b7b4a-152">Вызываемый метод может также объявить возвращаемое значение `ref readonly`, чтобы возвращать значения по ссылке, и запретить вызывающему коду изменять возвращенное значение.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-152">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="b7b4a-153">Вызывающий метод может обойтись без копирования возвращаемого значения, сохраняя его в локальной переменной [ref readonly](#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-153">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="b7b4a-154">Пример см. в разделе [Пример использования возвращаемых ссылочных значений и ссылочных локальных переменных](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-154">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="b7b4a-155">Ссылочные локальные переменные</span><span class="sxs-lookup"><span data-stu-id="b7b4a-155">Ref locals</span></span>

<span data-ttu-id="b7b4a-156">Ссылочная локальная переменная задает ссылку на значения, возвращаемые с помощью `return ref`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-156">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="b7b4a-157">Ссылочная локальная переменная не может инициализироваться как не ссылочное возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-157">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="b7b4a-158">Другими словами, правая часть инициализации должна быть ссылкой.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-158">In other words, the right hand side of the initialization must be a reference.</span></span> <span data-ttu-id="b7b4a-159">Любые изменения в значении ссылочной локальной переменной отражаются в состоянии объекта, метод которого возвращает значение по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-159">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="b7b4a-160">Ссылочная локальная переменная определяется с помощью ключевого слова `ref` перед объявлением переменной, а также непосредственно перед вызовом метода, который возвращает значение по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-160">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="b7b4a-161">Например, следующая инструкция определяет значение ссылочной локальной переменной, которое возвращается методом `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="b7b4a-161">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="b7b4a-162">Вы можете таким же образом обратиться к значению по ссылке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-162">You can access a value by reference in the same way.</span></span> <span data-ttu-id="b7b4a-163">В некоторых случаях обращение к значению по ссылке повышает производительность, поскольку позволяет избежать потенциально затратной операции копирования.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-163">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="b7b4a-164">Например, в следующей инструкции показано, как можно определить локальное ссылочное значение, используемое для ссылки на значение.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-164">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="b7b4a-165">Обратите внимание, что в обоих примерах ключевое слово `ref` необходимо использовать в обоих местах. В противном случае возникает ошибка компилятора CS8172, "Невозможно инициализировать значением переменную по ссылке".</span><span class="sxs-lookup"><span data-stu-id="b7b4a-165">Note that in both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="b7b4a-166">Начиная с версии C# 7.3, переменная итерации инструкции `foreach` может иметь вид локальной ссылочной переменной или локальной ссылочной переменной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-166">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="b7b4a-167">Дополнительные сведения см. в статье, посвященной [инструкции foreach](foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="b7b4a-167">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="b7b4a-168">Ссылочные локальные переменные только для чтения</span><span class="sxs-lookup"><span data-stu-id="b7b4a-168">Ref readonly locals</span></span>

<span data-ttu-id="b7b4a-169">Ссылочная локальная переменная только для чтения (ref readonly) позволяет сохранить ссылку на значения, возвращаемые методом или свойством, которые имеют в сигнатуре модификатор `ref readonly` и используют `return ref`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-169">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="b7b4a-170">Переменная `ref readonly` сочетает свойства локальной переменной `ref` и переменной `readonly`. Она является псевдонимом для хранилища, которому она присвоена, и не может изменять свое значение.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-170">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span> 

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="b7b4a-171">Пример использования возвращаемых ссылочных значений и ссылочных локальных переменных</span><span class="sxs-lookup"><span data-stu-id="b7b4a-171">A ref returns and ref locals example</span></span>

<span data-ttu-id="b7b4a-172">В следующем примере определяется класс `Book`, содержащий два поля <xref:System.String>: `Title` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-172">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="b7b4a-173">Также определяется класс `BookCollection`, который включает частный массив объектов `Book`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-173">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="b7b4a-174">Отдельные объекты книг возвращаются по ссылке путем вызова метода `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-174">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="b7b4a-175">Если вызывающий объект сохраняет значение, возвращаемое методом `GetBookByTitle`, в качестве ссылочной локальной переменной, изменения, которые этот объект вносит в возвращаемое значение, отражаются в объекте `BookCollection`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-175">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="ref-struct-types"></a><span data-ttu-id="b7b4a-176">Типы ссылочных структур</span><span class="sxs-lookup"><span data-stu-id="b7b4a-176">Ref struct types</span></span>

<span data-ttu-id="b7b4a-177">Добавление модификатора `ref` в объявление `struct` определяет, что экземпляры этого типа должны размещаться в стеке.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-177">Adding the `ref` modifier to a `struct` declaration defines that instances of that type must be stack allocated.</span></span> <span data-ttu-id="b7b4a-178">Другими словами, экземпляры этих типов никогда не создаются из кучи в роли члена другого класса.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-178">In other words, instances of these types can never be created on the heap as a member of another class.</span></span> <span data-ttu-id="b7b4a-179">Главным стимулом для создания этой функции была структура <xref:System.Span%601> и связанные структуры.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-179">The primary motivation for this feature was <xref:System.Span%601> and related structures.</span></span>

<span data-ttu-id="b7b4a-180">Необходимость поддержки типа `ref struct` как выделенной в стеке переменной вводит ряд правил, применяемых компилятором ко всем типам `ref struct`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-180">The goal of keeping a `ref struct` type as a stack-allocated variable introduces several rules that the compiler enforces for all `ref struct` types.</span></span>

- <span data-ttu-id="b7b4a-181">`ref struct` не поддерживает упаковку.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-181">You can't box a `ref struct`.</span></span> <span data-ttu-id="b7b4a-182">Тип `ref struct` невозможно присвоить переменной типа `object`, `dynamic` или любому типу интерфейса.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-182">You cannot assign a `ref struct` type to a variable of type `object`, `dynamic`, or any interface type.</span></span>
- <span data-ttu-id="b7b4a-183">Типы `ref struct` не могут реализовывать интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-183">`ref struct` types cannot implement interfaces.</span></span>
- <span data-ttu-id="b7b4a-184">`ref struct` невозможно объявить как член поля класса или обычной структуры.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-184">You can't declare a `ref struct` as a field member of a class or a normal struct.</span></span> <span data-ttu-id="b7b4a-185">Сюда входит объявление автоматически реализуемого свойства, которое создает резервное поле, созданное компилятором.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-185">This includes declaring an auto-implemented property, which creates a compiler generated backing field.</span></span> 
- <span data-ttu-id="b7b4a-186">Невозможно объявить локальные переменные, которые являются типами `ref struct` в асинхронных методах.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-186">You cannot declare local variables that are `ref struct` types in async methods.</span></span> <span data-ttu-id="b7b4a-187">Вы можете объявлять их в синхронных методах, которые возвращают типы <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> или `Task`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-187">You can declare them in synchronous methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601> or `Task`-like types.</span></span>
- <span data-ttu-id="b7b4a-188">Локальные переменные `ref struct` невозможно объявить в итераторах.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-188">You cannot declare `ref struct` local variables in iterators.</span></span>
- <span data-ttu-id="b7b4a-189">Невозможно захватить переменные `ref struct` в лямбда-выражениях или локальных функциях.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-189">You cannot capture `ref struct` variables in lambda expressions or local functions.</span></span>

<span data-ttu-id="b7b4a-190">Эти ограничения позволяют избежать случайного использования `ref struct`, которое может повысить его уровень до управляемой кучи.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-190">These restrictions ensure you don't accidentally use a `ref struct` in a manner that could promote it to the managed heap.</span></span>

<span data-ttu-id="b7b4a-191">Вы можете сочетать модификаторы и объявить структуру как `readonly ref`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-191">You can combine modifiers to declare a struct as `readonly ref`.</span></span> <span data-ttu-id="b7b4a-192">Объявление `readonly ref struct` объединяет все преимущества и ограничения объявлений `ref struct` и `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="b7b4a-192">A `readonly ref struct` combines the benefits and restrictions of `ref struct` and `readonly struct` declarations.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="b7b4a-193">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="b7b4a-193">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b7b4a-194">См. также</span><span class="sxs-lookup"><span data-stu-id="b7b4a-194">See also</span></span>

- [<span data-ttu-id="b7b4a-195">Написание безопасного и эффективного кода</span><span class="sxs-lookup"><span data-stu-id="b7b4a-195">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="b7b4a-196">Возвращаемые значения ref и локальные переменные ref</span><span class="sxs-lookup"><span data-stu-id="b7b4a-196">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="b7b4a-197">Условное выражение REF</span><span class="sxs-lookup"><span data-stu-id="b7b4a-197">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="b7b4a-198">Ссылочный оператор присваивания</span><span class="sxs-lookup"><span data-stu-id="b7b4a-198">ref assignment operator</span></span>](../operators/assignment-operator.md#ref-assignment-operator)
- [<span data-ttu-id="b7b4a-199">Передача параметров</span><span class="sxs-lookup"><span data-stu-id="b7b4a-199">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="b7b4a-200">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="b7b4a-200">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="b7b4a-201">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="b7b4a-201">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b7b4a-202">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="b7b4a-202">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b7b4a-203">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="b7b4a-203">C# Keywords</span></span>](index.md)
