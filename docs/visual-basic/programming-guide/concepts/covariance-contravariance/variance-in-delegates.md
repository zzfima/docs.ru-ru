---
title: Вариативность в делегатах
ms.date: 07/20/2015
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
ms.openlocfilehash: 11146bc4a60f55fc0373f0b5dfa5d44dcf748a5b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349004"
---
# <a name="variance-in-delegates-visual-basic"></a><span data-ttu-id="4b081-102">Вариативность в делегатах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b081-102">Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="4b081-103">В .NET Framework 3,5 введена поддержка вариативности для сопоставления сигнатур методов с типами делегатов C# во всех делегатах в и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4b081-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic.</span></span> <span data-ttu-id="4b081-104">Это означает, что делегатам можно назначать не только методы, которые обладают соответствующими сигнатурами, но и методы, которые возвращают более производные типы (ковариация), или принимают параметры, которые имеют менее производные типы (контравариативность), чем указано в типе делегата.</span><span class="sxs-lookup"><span data-stu-id="4b081-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="4b081-105">Это касается не только универсальных методов-делегатов, но и методов-делегатов, не являющихся универсальными.</span><span class="sxs-lookup"><span data-stu-id="4b081-105">This includes both generic and non-generic delegates.</span></span>

<span data-ttu-id="4b081-106">Например, рассмотрим следующий код, который содержит два класса и два делегата: универсальный и неуниверсальный.</span><span class="sxs-lookup"><span data-stu-id="4b081-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>

```vb
Public Class First
End Class

Public Class Second
    Inherits First
End Class

Public Delegate Function SampleDelegate(ByVal a As Second) As First
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R
```

<span data-ttu-id="4b081-107">При создании делегатов типов `SampleDelegate` или `SampleDelegate(Of A, R)` им можно назначить любой из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="4b081-107">When you create delegates of the `SampleDelegate` or `SampleDelegate(Of A, R)` types, you can assign any one of the following methods to those delegates.</span></span>

```vb
' Matching signature.
Public Shared Function ASecondRFirst(
    ByVal second As Second) As First
    Return New First()
End Function

' The return type is more derived.
Public Shared Function ASecondRSecond(
    ByVal second As Second) As Second
    Return New Second()
End Function

' The argument type is less derived.
Public Shared Function AFirstRFirst(
    ByVal first As First) As First
    Return New First()
End Function

' The return type is more derived
' and the argument type is less derived.
Public Shared Function AFirstRSecond(
    ByVal first As First) As Second
    Return New Second()
End Function
```

<span data-ttu-id="4b081-108">В следующем примере кода показано неявное преобразование между сигнатурой метода и типом делегата.</span><span class="sxs-lookup"><span data-stu-id="4b081-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>

```vb
' Assigning a method with a matching signature
' to a non-generic delegate. No conversion is necessary.
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a non-generic delegate.
' The implicit conversion is used.
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond

' Assigning a method with a matching signature to a generic delegate.
' No conversion is necessary.
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a generic delegate.
' The implicit conversion is used.
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond
```

<span data-ttu-id="4b081-109">Дополнительные примеры см. [в разделе Использование вариативности в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) и [Использование вариативности для универсальных делегатов Func и Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="4b081-109">For more examples, see [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="4b081-110">Вариативность в параметрах универсального типа</span><span class="sxs-lookup"><span data-stu-id="4b081-110">Variance in Generic Type Parameters</span></span>

<span data-ttu-id="4b081-111">В .NET Framework 4 и более поздних версиях можно включить неявное преобразование между делегатами, чтобы универсальные делегаты с разными типами, заданными параметрами универсального типа, могли быть назначены друг другу, если типы наследуются друг от друга, как требуется для Вариация.</span><span class="sxs-lookup"><span data-stu-id="4b081-111">In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>

<span data-ttu-id="4b081-112">Чтобы включить неявное преобразование, необходимо явно объявить универсальные параметры в делегате как ковариантные или контравариантные с помощью ключевого слова `in` или `out`.</span><span class="sxs-lookup"><span data-stu-id="4b081-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>

<span data-ttu-id="4b081-113">В следующем примере кода показано, как создать делегат, который имеет ковариантный параметр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="4b081-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>

```vb
' Type T is declared covariant by using the out keyword.
Public Delegate Function SampleGenericDelegate(Of Out T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "
    ' You can assign delegates to each other,
    ' because the type T is declared covariant.
    Dim dObject As SampleGenericDelegate(Of Object) = dString
End Sub
```

<span data-ttu-id="4b081-114">Если поддержка вариативности используется только для сопоставления сигнатур методов с типами делегатов, а ключевые слова `in` и `out` не используются, можно создать экземпляры делегатов с одинаковыми лямбда-выражениями или методами, но нельзя назначить один делегат другому.</span><span class="sxs-lookup"><span data-stu-id="4b081-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>

<span data-ttu-id="4b081-115">В следующем примере кода `SampleGenericDelegate(Of String)` не может быть явно преобразован в `SampleGenericDelegate(Of Object)`, хотя `String` наследует `Object`.</span><span class="sxs-lookup"><span data-stu-id="4b081-115">In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`.</span></span> <span data-ttu-id="4b081-116">Эту проблему можно устранить, пометив универсальный параметр `T` ключевым словом `out`.</span><span class="sxs-lookup"><span data-stu-id="4b081-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>

```vb
Public Delegate Function SampleGenericDelegate(Of T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "

    ' You can assign the dObject delegate
    ' to the same lambda expression as dString delegate
    ' because of the variance support for
    ' matching method signatures with delegate types.
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "

    ' The following statement generates a compiler error
    ' because the generic type T is not marked as covariant.
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString

End Sub
```

### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="4b081-117">Универсальные методы-делегаты с вариативными параметрами типа в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4b081-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>

<span data-ttu-id="4b081-118">В платформе .NET Framework 4 появилась поддержка вариативности для параметров универсального типа в нескольких существующих методах-делегатах.</span><span class="sxs-lookup"><span data-stu-id="4b081-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>

- <span data-ttu-id="4b081-119">Делегаты `Action` из пространства имен <xref:System>, например <xref:System.Action%601> и <xref:System.Action%602></span><span class="sxs-lookup"><span data-stu-id="4b081-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>

- <span data-ttu-id="4b081-120">Делегаты `Func` из пространства имен <xref:System>, например <xref:System.Func%601> и <xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="4b081-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>

- <span data-ttu-id="4b081-121">Делегат <xref:System.Predicate%601></span><span class="sxs-lookup"><span data-stu-id="4b081-121">The <xref:System.Predicate%601> delegate</span></span>

- <span data-ttu-id="4b081-122">Делегат <xref:System.Comparison%601></span><span class="sxs-lookup"><span data-stu-id="4b081-122">The <xref:System.Comparison%601> delegate</span></span>

- <span data-ttu-id="4b081-123">Делегат <xref:System.Converter%602></span><span class="sxs-lookup"><span data-stu-id="4b081-123">The <xref:System.Converter%602> delegate</span></span>

<span data-ttu-id="4b081-124">Дополнительные сведения и примеры см. [в разделе Использование вариативности универсальных делегатов Func и Action (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="4b081-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="4b081-125">Объявление вариативных параметров типа в универсальных методах-делегатах</span><span class="sxs-lookup"><span data-stu-id="4b081-125">Declaring Variant Type Parameters in Generic Delegates</span></span>

<span data-ttu-id="4b081-126">Если универсальный метод-делегат содержит ковариантные или контравариантные параметры универсального типа, он называется *вариативным универсальным методом-делегатом*.</span><span class="sxs-lookup"><span data-stu-id="4b081-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>

<span data-ttu-id="4b081-127">Для объявления ковариантного параметра универсального типа в универсальном методе-делегате можно использовать ключевое слово `out`.</span><span class="sxs-lookup"><span data-stu-id="4b081-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="4b081-128">Ковариантный тип можно использовать только в качестве типа значения, возвращаемого методом, и нельзя использовать в качестве типа аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="4b081-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="4b081-129">В следующем примере кода показано, как объявить ковариантный универсальный метод-делегат.</span><span class="sxs-lookup"><span data-stu-id="4b081-129">The following code example shows how to declare a covariant generic delegate.</span></span>

```vb
Public Delegate Function DCovariant(Of Out R)() As R
```

<span data-ttu-id="4b081-130">Для объявления контравариантного параметра универсального типа в универсальном методе-делегате можно использовать ключевое слово `in`.</span><span class="sxs-lookup"><span data-stu-id="4b081-130">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="4b081-131">Контравариантный тип можно использовать только в качестве типа аргументов метода, и нельзя использовать в качестве типа значения, возвращаемого методом.</span><span class="sxs-lookup"><span data-stu-id="4b081-131">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="4b081-132">В следующем примере кода показано, как объявить контравариантный универсальный метод-делегат.</span><span class="sxs-lookup"><span data-stu-id="4b081-132">The following code example shows how to declare a contravariant generic delegate.</span></span>

```vb
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)
```

> [!IMPORTANT]
> <span data-ttu-id="4b081-133">`ByRef` параметры в Visual Basic не могут быть помечены как Variant.</span><span class="sxs-lookup"><span data-stu-id="4b081-133">`ByRef` parameters in Visual Basic can't be marked as variant.</span></span>

<span data-ttu-id="4b081-134">В одном делегате можно реализовать поддержку вариативности и ковариации, но для разных параметров типа.</span><span class="sxs-lookup"><span data-stu-id="4b081-134">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="4b081-135">Эти действия показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4b081-135">This is shown in the following example.</span></span>

```vb
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R
```

### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="4b081-136">Создание экземпляра и вызов вариативных универсальных методов-делегатов</span><span class="sxs-lookup"><span data-stu-id="4b081-136">Instantiating and Invoking Variant Generic Delegates</span></span>

<span data-ttu-id="4b081-137">Создание экземпляра и вызов вариативных делегатов возможен только при создании экземпляра и вызове инвариантных делегатов.</span><span class="sxs-lookup"><span data-stu-id="4b081-137">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="4b081-138">В следующем примере создается экземпляр делегата с помощью лямбда-выражения.</span><span class="sxs-lookup"><span data-stu-id="4b081-138">In the following example, the delegate is instantiated by a lambda expression.</span></span>

```vb
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "
dvariant("test")
```

### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="4b081-139">Объединение вариативных универсальных методов-делегатов</span><span class="sxs-lookup"><span data-stu-id="4b081-139">Combining Variant Generic Delegates</span></span>

<span data-ttu-id="4b081-140">Не следует объединять вариантные делегаты.</span><span class="sxs-lookup"><span data-stu-id="4b081-140">You should not combine variant delegates.</span></span> <span data-ttu-id="4b081-141">Метод <xref:System.Delegate.Combine%2A> не поддерживает преобразование вариантных делегатов и ожидает делегаты того же самого типа.</span><span class="sxs-lookup"><span data-stu-id="4b081-141">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="4b081-142">Это может привести к исключению времени выполнения при объединении делегатов с помощью метода <xref:System.Delegate.Combine%2A> (в C# и Visual Basic) или с помощью оператора `+` (в C#), как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="4b081-142">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.</span></span>

```vb
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)

' The following statement throws an exception at run time.
' Dim actCombine = [Delegate].Combine(actStr, actObj)
```

## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="4b081-143">Вариативность в параметрах универсального типа для значения и ссылочных типов</span><span class="sxs-lookup"><span data-stu-id="4b081-143">Variance in Generic Type Parameters for Value and Reference Types</span></span>

<span data-ttu-id="4b081-144">Вариативность для параметров универсального типа поддерживается только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="4b081-144">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="4b081-145">Например, `DVariant(Of Int)`нельзя неявно преобразовать в `DVariant(Of Object)` или `DVariant(Of Long)`, так как тип Integer является типом значения.</span><span class="sxs-lookup"><span data-stu-id="4b081-145">For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.</span></span>

<span data-ttu-id="4b081-146">В следующем примере показано, что вариативность в параметрах универсального типа не поддерживается для типов значения.</span><span class="sxs-lookup"><span data-stu-id="4b081-146">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>

```vb
' The type T is covariant.
Public Delegate Function DVariant(Of Out T)() As T
' The type T is invariant.
Public Delegate Function DInvariant(Of T)() As T
Sub Test()
    Dim i As Integer = 0
    Dim dInt As DInvariant(Of Integer) = Function() i
    Dim dVariantInt As DVariant(Of Integer) = Function() i

    ' All of the following statements generate a compiler error
    ' because type variance in generic parameters is not supported
    ' for value types, even if generic type parameters are declared variant.
    ' Dim dObject As DInvariant(Of Object) = dInt
    ' Dim dLong As DInvariant(Of Long) = dInt
    ' Dim dVariantObject As DInvariant(Of Object) = dInt
    ' Dim dVariantLong As DInvariant(Of Long) = dInt
End Sub
```

## <a name="relaxed-delegate-conversion-in-visual-basic"></a><span data-ttu-id="4b081-147">Неявное преобразование делегата в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b081-147">Relaxed Delegate Conversion in Visual Basic</span></span>

<span data-ttu-id="4b081-148">Неявное преобразование делегатов обеспечивает большую гибкость при сопоставлении сигнатур методов с типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="4b081-148">Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types.</span></span> <span data-ttu-id="4b081-149">Например, он позволяет опускать спецификации параметров и опускать возвращаемые значения функции при назначении метода делегату.</span><span class="sxs-lookup"><span data-stu-id="4b081-149">For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate.</span></span> <span data-ttu-id="4b081-150">Дополнительные сведения см. в разделе [неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="4b081-150">For more information, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b081-151">См. также</span><span class="sxs-lookup"><span data-stu-id="4b081-151">See also</span></span>

- [<span data-ttu-id="4b081-152">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="4b081-152">Generics</span></span>](../../../../standard/generics/index.md)
- [<span data-ttu-id="4b081-153">Использование вариативности в универсальных методах-делегатах Func и Action (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4b081-153">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
