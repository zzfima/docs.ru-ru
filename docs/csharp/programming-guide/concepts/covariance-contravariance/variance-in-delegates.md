---
title: Вариативность в делегатах (C#)
ms.date: 07/20/2015
ms.assetid: 19de89d2-8224-4406-8964-2965b732b890
ms.openlocfilehash: fd1b4824dc3d8f12347e01b804a6e39fe2e086c8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169718"
---
# <a name="variance-in-delegates-c"></a><span data-ttu-id="59199-102">Вариативность в делегатах (C#)</span><span class="sxs-lookup"><span data-stu-id="59199-102">Variance in Delegates (C#)</span></span>
<span data-ttu-id="59199-103">В платформе .NET Framework 3.5 появилась поддержка вариативности при сопоставлении сигнатур методов с типами делегатов во всех делегатах в C#.</span><span class="sxs-lookup"><span data-stu-id="59199-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C#.</span></span> <span data-ttu-id="59199-104">Это означает, что делегатам можно назначать не только методы, которые обладают соответствующими сигнатурами, но и методы, которые возвращают более производные типы (ковариация), или принимают параметры, которые имеют менее производные типы (контравариативность), чем указано в типе делегата.</span><span class="sxs-lookup"><span data-stu-id="59199-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="59199-105">Это касается не только универсальных методов-делегатов, но и методов-делегатов, не являющихся универсальными.</span><span class="sxs-lookup"><span data-stu-id="59199-105">This includes both generic and non-generic delegates.</span></span>  
  
 <span data-ttu-id="59199-106">Например, рассмотрим следующий код, который содержит два класса и два делегата: универсальный и неуниверсальный.</span><span class="sxs-lookup"><span data-stu-id="59199-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>  
  
```csharp  
public class First { }  
public class Second : First { }  
public delegate First SampleDelegate(Second a);  
public delegate R SampleGenericDelegate<A, R>(A a);  
```  
  
 <span data-ttu-id="59199-107">При создании делегатов типов `SampleDelegate` или `SampleGenericDelegate<A, R>` им можно назначить любой из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="59199-107">When you create delegates of the `SampleDelegate` or `SampleGenericDelegate<A, R>` types, you can assign any one of the following methods to those delegates.</span></span>  
  
```csharp  
// Matching signature.  
public static First ASecondRFirst(Second second)  
{ return new First(); }  
  
// The return type is more derived.  
public static Second ASecondRSecond(Second second)  
{ return new Second(); }  
  
// The argument type is less derived.  
public static First AFirstRFirst(First first)  
{ return new First(); }  
  
// The return type is more derived
// and the argument type is less derived.  
public static Second AFirstRSecond(First first)  
{ return new Second(); }  
```  
  
 <span data-ttu-id="59199-108">В следующем примере кода показано неявное преобразование между сигнатурой метода и типом делегата.</span><span class="sxs-lookup"><span data-stu-id="59199-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>  
  
```csharp  
// Assigning a method with a matching signature
// to a non-generic delegate. No conversion is necessary.  
SampleDelegate dNonGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type
// and less derived argument type to a non-generic delegate.  
// The implicit conversion is used.  
SampleDelegate dNonGenericConversion = AFirstRSecond;  
  
// Assigning a method with a matching signature to a generic delegate.  
// No conversion is necessary.  
SampleGenericDelegate<Second, First> dGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type
// and less derived argument type to a generic delegate.  
// The implicit conversion is used.  
SampleGenericDelegate<Second, First> dGenericConversion = AFirstRSecond;  
```  
  
 <span data-ttu-id="59199-109">Дополнительные примеры см. в разделах [Использование вариативности в делегатах (C#)](./using-variance-in-delegates.md) и [Использование вариативности в универсальных методах-делегатах Func и Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="59199-109">For more examples, see [Using Variance in Delegates (C#)](./using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="59199-110">Вариативность в параметрах универсального типа</span><span class="sxs-lookup"><span data-stu-id="59199-110">Variance in Generic Type Parameters</span></span>  
 <span data-ttu-id="59199-111">В платформе .NET Framework 4 и более поздних версиях можно включить неявное преобразование между делегатами, которое позволит универсальным методам-делегатам, имеющим разные типы, указанные параметрами универсального типа, быть назначенными друг другу, если типы наследуются друг от друга так, как того требует вариативность.</span><span class="sxs-lookup"><span data-stu-id="59199-111">In .NET Framework 4 or later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>  
  
 <span data-ttu-id="59199-112">Чтобы включить неявное преобразование, необходимо явно объявить универсальные параметры в делегате как ковариантные или контравариантные с помощью ключевого слова `in` или `out`.</span><span class="sxs-lookup"><span data-stu-id="59199-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>  
  
 <span data-ttu-id="59199-113">В следующем примере кода показано, как создать делегат, который имеет ковариантный параметр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="59199-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>  
  
```csharp  
// Type T is declared covariant by using the out keyword.  
public delegate T SampleGenericDelegate <out T>();  
  
public static void Test()  
{  
    SampleGenericDelegate <String> dString = () => " ";  
  
    // You can assign delegates to each other,  
    // because the type T is declared covariant.  
    SampleGenericDelegate <Object> dObject = dString;
}  
```  
  
 <span data-ttu-id="59199-114">Если поддержка вариативности используется только для сопоставления сигнатур методов с типами делегатов, а ключевые слова `in` и `out` не используются, можно создать экземпляры делегатов с одинаковыми лямбда-выражениями или методами, но нельзя назначить один делегат другому.</span><span class="sxs-lookup"><span data-stu-id="59199-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>  
  
 <span data-ttu-id="59199-115">В следующем примере кода `SampleGenericDelegate<String>` нельзя явно преобразовать в `SampleGenericDelegate<Object>`, хотя `String` наследует `Object`.</span><span class="sxs-lookup"><span data-stu-id="59199-115">In the following code example, `SampleGenericDelegate<String>` cannot be explicitly converted to `SampleGenericDelegate<Object>`, although `String` inherits `Object`.</span></span> <span data-ttu-id="59199-116">Эту проблему можно устранить, пометив универсальный параметр `T` ключевым словом `out`.</span><span class="sxs-lookup"><span data-stu-id="59199-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>  
  
```csharp  
public delegate T SampleGenericDelegate<T>();  
  
public static void Test()  
{  
    SampleGenericDelegate<String> dString = () => " ";  
  
    // You can assign the dObject delegate  
    // to the same lambda expression as dString delegate  
    // because of the variance support for
    // matching method signatures with delegate types.  
    SampleGenericDelegate<Object> dObject = () => " ";  
  
    // The following statement generates a compiler error  
    // because the generic type T is not marked as covariant.  
    // SampleGenericDelegate <Object> dObject = dString;  
  
}  
```  
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="59199-117">Универсальные методы-делегаты с вариативными параметрами типа в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="59199-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>  
 <span data-ttu-id="59199-118">В платформе .NET Framework 4 появилась поддержка вариативности для параметров универсального типа в нескольких существующих методах-делегатах.</span><span class="sxs-lookup"><span data-stu-id="59199-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>  
  
- <span data-ttu-id="59199-119">Делегаты `Action` из пространства имен <xref:System>, например <xref:System.Action%601> и <xref:System.Action%602></span><span class="sxs-lookup"><span data-stu-id="59199-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>  
  
- <span data-ttu-id="59199-120">Делегаты `Func` из пространства имен <xref:System>, например <xref:System.Func%601> и <xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="59199-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>  
  
- <span data-ttu-id="59199-121">Делегат <xref:System.Predicate%601></span><span class="sxs-lookup"><span data-stu-id="59199-121">The <xref:System.Predicate%601> delegate</span></span>  
  
- <span data-ttu-id="59199-122">Делегат <xref:System.Comparison%601></span><span class="sxs-lookup"><span data-stu-id="59199-122">The <xref:System.Comparison%601> delegate</span></span>  
  
- <span data-ttu-id="59199-123">Делегат <xref:System.Converter%602></span><span class="sxs-lookup"><span data-stu-id="59199-123">The <xref:System.Converter%602> delegate</span></span>  
  
 <span data-ttu-id="59199-124">Дополнительные примеры см. в разделе [Использование вариативности в универсальных методах-делегатах Func и Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="59199-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (C#)](./using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="59199-125">Объявление вариативных параметров типа в универсальных методах-делегатах</span><span class="sxs-lookup"><span data-stu-id="59199-125">Declaring Variant Type Parameters in Generic Delegates</span></span>  
 <span data-ttu-id="59199-126">Если универсальный метод-делегат содержит ковариантные или контравариантные параметры универсального типа, он называется *вариативным универсальным методом-делегатом*.</span><span class="sxs-lookup"><span data-stu-id="59199-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>  
  
 <span data-ttu-id="59199-127">Для объявления ковариантного параметра универсального типа в универсальном методе-делегате можно использовать ключевое слово `out`.</span><span class="sxs-lookup"><span data-stu-id="59199-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="59199-128">Ковариантный тип можно использовать только в качестве типа значения, возвращаемого методом, и нельзя использовать в качестве типа аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="59199-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="59199-129">В следующем примере кода показано, как объявить ковариантный универсальный метод-делегат.</span><span class="sxs-lookup"><span data-stu-id="59199-129">The following code example shows how to declare a covariant generic delegate.</span></span>  
  
```csharp  
public delegate R DCovariant<out R>();  
```  
  
 <span data-ttu-id="59199-130">Для объявления контравариантного параметра универсального типа в универсальном методе-делегате можно использовать ключевое слово `in`.</span><span class="sxs-lookup"><span data-stu-id="59199-130">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="59199-131">Контравариантный тип можно использовать только в качестве типа аргументов метода, и нельзя использовать в качестве типа значения, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="59199-131">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="59199-132">В следующем примере кода показано, как объявить контравариантный универсальный метод-делегат.</span><span class="sxs-lookup"><span data-stu-id="59199-132">The following code example shows how to declare a contravariant generic delegate.</span></span>  
  
```csharp  
public delegate void DContravariant<in A>(A a);  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="59199-133">Параметры `ref`, `in` и `out` в C# невозможно пометить как вариативные.</span><span class="sxs-lookup"><span data-stu-id="59199-133">`ref`, `in`, and `out` parameters in C# can't be marked as variant.</span></span>  
  
 <span data-ttu-id="59199-134">В одном делегате можно реализовать поддержку вариативности и ковариации, но для разных параметров типа.</span><span class="sxs-lookup"><span data-stu-id="59199-134">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="59199-135">Это показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="59199-135">This is shown in the following example.</span></span>  
  
```csharp  
public delegate R DVariant<in A, out R>(A a);  
```  
  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="59199-136">Создание экземпляра и вызов вариативных универсальных методов-делегатов</span><span class="sxs-lookup"><span data-stu-id="59199-136">Instantiating and Invoking Variant Generic Delegates</span></span>  
 <span data-ttu-id="59199-137">Создание экземпляра и вызов вариативных делегатов возможен только при создании экземпляра и вызове инвариантных делегатов.</span><span class="sxs-lookup"><span data-stu-id="59199-137">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="59199-138">В следующем примере создается экземпляр делегата с помощью лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="59199-138">In the following example, the delegate is instantiated by a lambda expression.</span></span>  
  
```csharp  
DVariant<String, String> dvariant = (String str) => str + " ";  
dvariant("test");  
```  
  
### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="59199-139">Объединение вариативных универсальных методов-делегатов</span><span class="sxs-lookup"><span data-stu-id="59199-139">Combining Variant Generic Delegates</span></span>  
 <span data-ttu-id="59199-140">Не следует объединять вариантные делегаты.</span><span class="sxs-lookup"><span data-stu-id="59199-140">You should not combine variant delegates.</span></span> <span data-ttu-id="59199-141">Метод <xref:System.Delegate.Combine%2A> не поддерживает преобразование вариантных делегатов и ожидает делегаты того же самого типа.</span><span class="sxs-lookup"><span data-stu-id="59199-141">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="59199-142">Это может вызвать исключение времени выполнения при объединении делегатов с помощью метода <xref:System.Delegate.Combine%2A> или оператора `+`, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="59199-142">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method or by using the `+` operator, as shown in the following code example.</span></span>  
  
```csharp  
Action<object> actObj = x => Console.WriteLine("object: {0}", x);  
Action<string> actStr = x => Console.WriteLine("string: {0}", x);  
// All of the following statements throw exceptions at run time.  
// Action<string> actCombine = actStr + actObj;  
// actStr += actObj;  
// Delegate.Combine(actStr, actObj);  
```  
  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="59199-143">Вариативность в параметрах универсального типа для значения и ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="59199-143">Variance in Generic Type Parameters for Value and Reference Types</span></span>  
 <span data-ttu-id="59199-144">Вариативность для параметров универсального типа поддерживается только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="59199-144">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="59199-145">Например, `DVariant<int>` нельзя неявно преобразовать в `DVariant<Object>` или `DVariant<long>`, поскольку integer является типом значения.</span><span class="sxs-lookup"><span data-stu-id="59199-145">For example, `DVariant<int>` can't be implicitly converted to `DVariant<Object>` or `DVariant<long>`, because integer is a value type.</span></span>  
  
 <span data-ttu-id="59199-146">В следующем примере показано, что вариативность в параметрах универсального типа не поддерживается для типов значения.</span><span class="sxs-lookup"><span data-stu-id="59199-146">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>  
  
```csharp  
// The type T is covariant.  
public delegate T DVariant<out T>();  
  
// The type T is invariant.  
public delegate T DInvariant<T>();  
  
public static void Test()  
{  
    int i = 0;  
    DInvariant<int> dInt = () => i;  
    DVariant<int> dVariantInt = () => i;  
  
    // All of the following statements generate a compiler error  
    // because type variance in generic parameters is not supported  
    // for value types, even if generic type parameters are declared variant.  
    // DInvariant<Object> dObject = dInt;  
    // DInvariant<long> dLong = dInt;  
    // DVariant<Object> dVariantObject = dVariantInt;  
    // DVariant<long> dVariantLong = dVariantInt;
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="59199-147">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="59199-147">See also</span></span>

- [<span data-ttu-id="59199-148">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="59199-148">Generics</span></span>](../../../../standard/generics/index.md)
- [<span data-ttu-id="59199-149">Использование вариативности в универсальных методах-делегатах Func и Action (C#)</span><span class="sxs-lookup"><span data-stu-id="59199-149">Using Variance for Func and Action Generic Delegates (C#)</span></span>](./using-variance-for-func-and-action-generic-delegates.md)
- [<span data-ttu-id="59199-150">Практическое руководство. Объединение делегатов (многоадресные делегаты)</span><span class="sxs-lookup"><span data-stu-id="59199-150">How to combine delegates (Multicast Delegates)</span></span>](../../delegates/how-to-combine-delegates-multicast-delegates.md)
