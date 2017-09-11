---
title: "ref (Справочник по C#)"
ms.date: 2017-05-30
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ref_CSharpKeyword
- ref
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.assetid: b8a5e59c-907d-4065-b41d-95bf4273c0bd
caps.latest.revision: 32
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
ms.openlocfilehash: 003125ca6218d42a919d8bb592b5454a7cb387c7
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="ref-c-reference"></a><span data-ttu-id="f16c9-102">ref (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="f16c9-102">ref (C# Reference)</span></span>

<span data-ttu-id="f16c9-103">Ключевое слово `ref` указывает на значение, переданное по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f16c9-103">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="f16c9-104">Оно используется в трех разных контекстах:</span><span class="sxs-lookup"><span data-stu-id="f16c9-104">It is used in three different contexts:</span></span> 

- <span data-ttu-id="f16c9-105">В сигнатуре и вызове метода для передачи аргумента в метод по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f16c9-105">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="f16c9-106">Дополнительные сведения см. в разделе [Передача аргумента по ссылке](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="f16c9-106">See [Passing an argument by reference](#passing-an-argument-by-reference) for more information.</span></span>

- <span data-ttu-id="f16c9-107">В сигнатуре метода для возврата значения вызывающему объекту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f16c9-107">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="f16c9-108">Дополнительные сведения см. в разделе [Возвращаемые ссылочные значения](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="f16c9-108">See [Reference return values](#reference-return-values) for more information.</span></span>

- <span data-ttu-id="f16c9-109">В теле элемента для указания на то, что возвращаемые ссылочные значения хранятся локально в виде ссылки, которая может быть изменена вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="f16c9-109">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify.</span></span> <span data-ttu-id="f16c9-110">Дополнительные сведения см. в разделе [Ссылочные локальные переменные](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="f16c9-110">See [Ref locals](#ref-locals) for more information.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="f16c9-111">Передача аргументов по ссылке</span><span class="sxs-lookup"><span data-stu-id="f16c9-111">Passing an argument by reference</span></span>

<span data-ttu-id="f16c9-112">При использовании в списке параметров метода ключевое слово `ref` указывает на то, что аргумент передается по ссылке, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="f16c9-112">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="f16c9-113">Эффект передачи по ссылке в том, что все изменения аргумента в вызываемом методе отражаются в вызывающем методе.</span><span class="sxs-lookup"><span data-stu-id="f16c9-113">The effect of passing by reference is that any change to the argument in the called method is reflected in the calling method.</span></span> <span data-ttu-id="f16c9-114">Например, если вызывающий объект передает выражение локальной переменной или выражение доступа к элементу массива и вызванный метод заменяет объект, на который ссылается параметр ref, то локальная переменная или элемент массива взывающего объекта будет ссылаться на новый объект после возврата из метода.</span><span class="sxs-lookup"><span data-stu-id="f16c9-114">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller’s local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
>  <span data-ttu-id="f16c9-115">Не следует путать понятие передачи по ссылке с понятием ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="f16c9-115">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="f16c9-116">Эти два понятия не совпадают.</span><span class="sxs-lookup"><span data-stu-id="f16c9-116">The two concepts are not the same.</span></span> <span data-ttu-id="f16c9-117">Параметр метода может быть изменен с помощью `ref` независимо от того, принадлежит ли он к типу значения или ссылочному типу.</span><span class="sxs-lookup"><span data-stu-id="f16c9-117">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="f16c9-118">При передаче по ссылке упаковка-преобразование типа значения не производится.</span><span class="sxs-lookup"><span data-stu-id="f16c9-118">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="f16c9-119">Для использования параметра `ref` и при определении метода, и при вызове метода следует явно использовать ключевое слово `ref`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f16c9-119">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

<span data-ttu-id="f16c9-120">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f16c9-120">[!code-cs[csrefKeywordsMethodParams#6](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-1.cs)]</span></span>

<span data-ttu-id="f16c9-121">Аргумент, передаваемый в параметр `ref`, перед передачей должен быть инициализирован.</span><span class="sxs-lookup"><span data-stu-id="f16c9-121">An argument that is passed to a `ref` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="f16c9-122">В этом заключается отличие от параметров [out](out.md), аргументы которых не требуют явной инициализации перед передачей.</span><span class="sxs-lookup"><span data-stu-id="f16c9-122">This differs from [out](out.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="f16c9-123">Члены класса не могут иметь сигнатуры, отличие которых заключается только в `ref` и `out`.</span><span class="sxs-lookup"><span data-stu-id="f16c9-123">Members of a class can't have signatures that differ only by `ref` and `out`.</span></span> <span data-ttu-id="f16c9-124">Если единственное различие между двумя членами типа состоит в том, что один из них имеет параметр `ref`, а второй имеет параметр `out`, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="f16c9-124">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out` parameter.</span></span> <span data-ttu-id="f16c9-125">Например, следующий код не будет компилироваться.</span><span class="sxs-lookup"><span data-stu-id="f16c9-125">The following code, for example, doesn't compile.</span></span>  
  
 <span data-ttu-id="f16c9-126">[!code-cs[csrefKeywordsMethodParams#2](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f16c9-126">[!code-cs[csrefKeywordsMethodParams#2](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-2.cs)]</span></span>
  
 <span data-ttu-id="f16c9-127">Однако методы можно перегружать, если один метод принимает параметр `ref` или `out`, а другой — параметр по значению, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f16c9-127">However, methods can be overloaded when one method has a `ref` or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
 <span data-ttu-id="f16c9-128">[!code-cs[ref-and-overloads](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f16c9-128">[!code-cs[ref-and-overloads](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-3.cs)]</span></span>
  
 <span data-ttu-id="f16c9-129">В других ситуациях, требующих соответствия сигнатур, таких как скрытие или переопределение, `ref` и `out` являются частью сигнатуры и не соответствуют друг другу.</span><span class="sxs-lookup"><span data-stu-id="f16c9-129">In other situations that require signature matching, such as hiding or overriding, `ref` and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="f16c9-130">Свойства не являются переменными.</span><span class="sxs-lookup"><span data-stu-id="f16c9-130">Properties are not variables.</span></span> <span data-ttu-id="f16c9-131">Они являются методами и не могут быть переданы в параметр `ref`.</span><span class="sxs-lookup"><span data-stu-id="f16c9-131">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="f16c9-132">Сведения о передаче массивов см. в разделе [Передача массивов при помощи параметров ref и out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span><span class="sxs-lookup"><span data-stu-id="f16c9-132">For information about how to pass arrays, see [Passing Arrays Using ref and out](../../../csharp/programming-guide/arrays/passing-arrays-using-ref-and-out.md).</span></span>  
  
 <span data-ttu-id="f16c9-133">Ключевые слова `ref` и `out` нельзя использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="f16c9-133">You can't use the `ref` and `out` keywords for the following kinds of methods:</span></span>  
  
-   <span data-ttu-id="f16c9-134">Асинхронные методы, которые определяются с помощью модификатора [async](../../../csharp/language-reference/keywords/async.md).</span><span class="sxs-lookup"><span data-stu-id="f16c9-134">Async methods, which you define by using the [async](../../../csharp/language-reference/keywords/async.md) modifier.</span></span>  
  
-   <span data-ttu-id="f16c9-135">Методы итератора, которые включают оператор [yield return](../../../csharp/language-reference/keywords/yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="f16c9-135">Iterator methods, which include a [yield return](../../../csharp/language-reference/keywords/yield.md) or `yield break` statement.</span></span>  
  
## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="f16c9-136">Пример передачи аргументов по ссылке</span><span class="sxs-lookup"><span data-stu-id="f16c9-136">Passing an argument by reference: An example</span></span>

<span data-ttu-id="f16c9-137">В предыдущих примерах типы значений передаются по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f16c9-137">The previous examples pass value types by reference.</span></span> <span data-ttu-id="f16c9-138">Также можно использовать ключевое слово `ref` для передачи ссылочных типов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f16c9-138">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="f16c9-139">Передача ссылочного типа по ссылке позволяет вызываемому методу заменять объект, на который указывает ссылочный параметр в вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="f16c9-139">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="f16c9-140">Место хранения объекта передается методу в качестве значения ссылочного параметра.</span><span class="sxs-lookup"><span data-stu-id="f16c9-140">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="f16c9-141">Если изменить место хранения параметра (с указанием на новый объект), необходимо изменить место хранения, на который ссылается вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="f16c9-141">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="f16c9-142">В следующем примере экземпляр ссылочного типа передается как параметр `ref`.</span><span class="sxs-lookup"><span data-stu-id="f16c9-142">The following example passes an instance of a reference type as a `ref` parameter.</span></span>   
  
 <span data-ttu-id="f16c9-143">[!code-cs[ReferencesByRef](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f16c9-143">[!code-cs[ReferencesByRef](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-4.cs)]</span></span>  

<span data-ttu-id="f16c9-144">Дополнительные сведения о передаче ссылочных типов по значению и по ссылке см. в разделе [Передача параметров ссылочного типа](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="f16c9-144">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../../csharp/programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="f16c9-145">Возвращаемые ссылочные значения</span><span class="sxs-lookup"><span data-stu-id="f16c9-145">Reference return values</span></span>

<span data-ttu-id="f16c9-146">Возвращаемые ссылочные значения — это значения, которые метод возвращает вызывающему объекту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f16c9-146">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="f16c9-147">Это значит, что вызывающий объект может изменять значение, возвращаемое методом, и это изменение будет отражаться в состоянии объекта, содержащего этот метод.</span><span class="sxs-lookup"><span data-stu-id="f16c9-147">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object that contains the method.</span></span> 

<span data-ttu-id="f16c9-148">Возвращаемое ссылочное значение определяется с помощью ключевого слова `ref`:</span><span class="sxs-lookup"><span data-stu-id="f16c9-148">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="f16c9-149">В сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="f16c9-149">In the method signature.</span></span> <span data-ttu-id="f16c9-150">Например, следующая сигнатура указывает, что метод `GetCurrentPrice` возвращает значение <xref:System.Decimal> по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f16c9-150">For example, the following method signature inidicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

   ```csharp
   public ref decimal GetCurrentValue()
   ``` 
- <span data-ttu-id="f16c9-151">Перед каждой инструкцией `return` в методе.</span><span class="sxs-lookup"><span data-stu-id="f16c9-151">Before each `return` statement in the method.</span></span> <span data-ttu-id="f16c9-152">Пример:</span><span class="sxs-lookup"><span data-stu-id="f16c9-152">For example:</span></span>
 
   ```csharp
   ref return Decimal.Zero;
   ``` 

<span data-ttu-id="f16c9-153">Чтобы вызывающий объект имел возможность изменять состояние объекта, возвращаемое ссылочное значение должно храниться в переменной, которая явно определена как [ссылочная локальная переменная](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="f16c9-153">In order for the caller to modify the an object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span> 

<span data-ttu-id="f16c9-154">Пример см. в разделе [Пример использования возвращаемых ссылочных значений и ссылочных локальных переменных](#a-ref-returns-and-ref-locals-example)</span><span class="sxs-lookup"><span data-stu-id="f16c9-154">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example)</span></span>

## <a name="ref-locals"></a><span data-ttu-id="f16c9-155">Ссылочные локальные переменные</span><span class="sxs-lookup"><span data-stu-id="f16c9-155">Ref locals</span></span>

<span data-ttu-id="f16c9-156">Ссылочная локальная переменная задает ссылку на значения, возвращаемые с помощью `ref return`.</span><span class="sxs-lookup"><span data-stu-id="f16c9-156">A ref local variable is used to refer to values returned using `ref return`.</span></span>  <span data-ttu-id="f16c9-157">После инициализации ссылочной локальной переменной необходимо присвоить ей возвращаемое ссылочное значение.</span><span class="sxs-lookup"><span data-stu-id="f16c9-157">A ref local variable must be initialized and assigned to a ref return value.</span></span> <span data-ttu-id="f16c9-158">Любые изменения в значении ссылочной локальной переменной отражаются в состоянии объекта, метод которого возвращает значение по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f16c9-158">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="f16c9-159">Ссылочная локальная переменная определяется с помощью ключевого слова `ref` перед объявлением переменной, а также непосредственно перед вызовом метода, который возвращает значение по ссылке.</span><span class="sxs-lookup"><span data-stu-id="f16c9-159">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span> 

<span data-ttu-id="f16c9-160">Например, следующая инструкция определяет значение ссылочной локальной переменной, которое возвращается методом `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="f16c9-160">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="f16c9-161">Обратите внимание, что ключевое слово `ref` необходимо использовать в обоих местах. В противном случае возникает ошибка компилятора CS8172, "Невозможно инициализировать значением переменную по ссылке".</span><span class="sxs-lookup"><span data-stu-id="f16c9-161">Note that the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span> 
 
## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="f16c9-162">Пример использования возвращаемых ссылочных значений и ссылочных локальных переменных</span><span class="sxs-lookup"><span data-stu-id="f16c9-162">A ref returns and ref locals example</span></span>

<span data-ttu-id="f16c9-163">В следующем примере определяется класс `Book`, содержащий два поля <xref:System.String>: `Title` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="f16c9-163">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="f16c9-164">Также определяется класс `BookCollection`, который включает частный массив объектов `Book`.</span><span class="sxs-lookup"><span data-stu-id="f16c9-164">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="f16c9-165">Отдельные объекты книг возвращаются по ссылке путем вызова метода `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="f16c9-165">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

<span data-ttu-id="f16c9-166">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="f16c9-166">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#1)]</span></span>  

<span data-ttu-id="f16c9-167">Если вызывающий объект сохраняет значение, возвращаемое методом `GetBookByTitle`, в качестве ссылочной локальной переменной, изменения, которые этот объект вносит в возвращаемое значение, отражаются в объекте `BookCollection`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f16c9-167">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

<span data-ttu-id="f16c9-168">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#2)]</span><span class="sxs-lookup"><span data-stu-id="f16c9-168">[!code-cs[csrefreturns](../../../../samples/snippets/csharp/language-reference/keywords/ref/ref-5.cs#2)]</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="f16c9-169">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="f16c9-169">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f16c9-170">См. также</span><span class="sxs-lookup"><span data-stu-id="f16c9-170">See Also</span></span>  
 <span data-ttu-id="f16c9-171">[Справочник по C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f16c9-171">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f16c9-172">[Руководство по программированию на C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f16c9-172">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f16c9-173">[Передача параметров](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="f16c9-173">[Passing Parameters](../../../csharp/programming-guide/classes-and-structs/passing-parameters.md) </span></span>  
 <span data-ttu-id="f16c9-174">[Параметры методов](../../../csharp/language-reference/keywords/method-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="f16c9-174">[Method Parameters](../../../csharp/language-reference/keywords/method-parameters.md) </span></span>  
 [<span data-ttu-id="f16c9-175">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="f16c9-175">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)

