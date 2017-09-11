---
title: "Вариативность в делегатах (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cbab7da8c97ca202f8a4d0a1a65b8fa240cca32d
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-delegates-visual-basic"></a><span data-ttu-id="a43d5-102">Вариативность в делегатах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a43d5-102">Variance in Delegates (Visual Basic)</span></span>
<span data-ttu-id="a43d5-103">.NET framework 3.5 представила поддержка вариативности при сопоставлении сигнатур методов с типами делегатов в все делегаты в C# и Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="a43d5-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic.</span></span> <span data-ttu-id="a43d5-104">Это означает, что можно назначить делегирует не только методы, которые обладают соответствующими сигнатурами, но методы, которые возвращают более производные типы (ковариация) или принимают параметры, которые имеют менее производные типы (контравариация), чем указано в типе делегата.</span><span class="sxs-lookup"><span data-stu-id="a43d5-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="a43d5-105">Сюда входят универсальных и неуниверсальных делегатах.</span><span class="sxs-lookup"><span data-stu-id="a43d5-105">This includes both generic and non-generic delegates.</span></span>  
  
 <span data-ttu-id="a43d5-106">Например, рассмотрим следующий код, который содержит два класса и два делегата: универсальный и неуниверсальный.</span><span class="sxs-lookup"><span data-stu-id="a43d5-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>  
  
```vb  
Public Class First  
End Class  
  
Public Class Second  
    Inherits First  
End Class  
  
Public Delegate Function SampleDelegate(ByVal a As Second) As First  
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R  
```  
  
 <span data-ttu-id="a43d5-107">При создании делегатов `SampleDelegate` или `SampleDelegate(Of A, R)` типов, можно назначить один из следующих методов этих делегатов.</span><span class="sxs-lookup"><span data-stu-id="a43d5-107">When you create delegates of the `SampleDelegate` or `SampleDelegate(Of A, R)` types, you can assign any one of the following methods to those delegates.</span></span>  
  
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
  
 <span data-ttu-id="a43d5-108">В следующем примере кода показано неявное преобразование между сигнатуру метода и тип делегата.</span><span class="sxs-lookup"><span data-stu-id="a43d5-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>  
  
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
  
 <span data-ttu-id="a43d5-109">Дополнительные примеры см. в разделе [с помощью Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) и [с помощью дисперсию Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="a43d5-109">For more examples, see [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="a43d5-110">Вариативность в параметрах универсального типа</span><span class="sxs-lookup"><span data-stu-id="a43d5-110">Variance in Generic Type Parameters</span></span>  
 <span data-ttu-id="a43d5-111">В .NET Framework 4 и более поздних версий неявное преобразование между делегатами, можно включить, чтобы универсальные делегаты, которые имеют разные типы, указанные параметрами универсального типа можно назначить друг к другу, если типы наследуются друг от друга, как требует вариативность.</span><span class="sxs-lookup"><span data-stu-id="a43d5-111">In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>  
  
 <span data-ttu-id="a43d5-112">Чтобы включить неявное преобразование, необходимо явно объявить универсальные параметры в делегате как ковариантные или контравариантные с помощью `in` или `out` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="a43d5-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>  
  
 <span data-ttu-id="a43d5-113">В следующем примере кода показано, как можно создать делегат, который имеет ковариантный параметр универсального типа.</span><span class="sxs-lookup"><span data-stu-id="a43d5-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>  
  
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
  
 <span data-ttu-id="a43d5-114">Если только поддержка вариативности используется для сопоставления сигнатур методов с типами делегатов, а не используйте `in` и `out` ключевые слова, вы обнаружите, что можно создать экземпляры делегатов с одинаковыми лямбда-выражениями или методами, но нельзя назначить один делегат другому.</span><span class="sxs-lookup"><span data-stu-id="a43d5-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>  
  
 <span data-ttu-id="a43d5-115">В следующем примере кода `SampleGenericDelegate(Of String)` не может быть явно преобразованы `SampleGenericDelegate(Of Object)`, хотя `String` наследует `Object`.</span><span class="sxs-lookup"><span data-stu-id="a43d5-115">In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`.</span></span> <span data-ttu-id="a43d5-116">Эту проблему можно устранить, пометив универсальный параметр `T` с `out` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="a43d5-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>  
  
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
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="a43d5-117">Универсальные делегаты, которые имеют вариант параметрами типа в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="a43d5-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>  
 <span data-ttu-id="a43d5-118">Платформа .NET framework 4 появилась поддержка вариативности для параметров универсального типа в нескольких существующих универсальных методов-делегатов:</span><span class="sxs-lookup"><span data-stu-id="a43d5-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>  
  
-   <span data-ttu-id="a43d5-119">`Action`делегирует с <xref:System>пространства имен, например, <xref:System.Action%601>и <xref:System.Action%602></xref:System.Action%602> </xref:System.Action%601> </xref:System></span><span class="sxs-lookup"><span data-stu-id="a43d5-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>  
  
-   <span data-ttu-id="a43d5-120">`Func`делегирует с <xref:System>пространства имен, например, <xref:System.Func%601>и <xref:System.Func%602></xref:System.Func%602> </xref:System.Func%601> </xref:System></span><span class="sxs-lookup"><span data-stu-id="a43d5-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>  
  
-   <span data-ttu-id="a43d5-121"><xref:System.Predicate%601>Делегат</xref:System.Predicate%601></span><span class="sxs-lookup"><span data-stu-id="a43d5-121">The <xref:System.Predicate%601> delegate</span></span>  
  
-   <span data-ttu-id="a43d5-122"><xref:System.Comparison%601>Делегат</xref:System.Comparison%601></span><span class="sxs-lookup"><span data-stu-id="a43d5-122">The <xref:System.Comparison%601> delegate</span></span>  
  
-   <span data-ttu-id="a43d5-123"><xref:System.Converter%602>Делегат</xref:System.Converter%602></span><span class="sxs-lookup"><span data-stu-id="a43d5-123">The <xref:System.Converter%602> delegate</span></span>  
  
 <span data-ttu-id="a43d5-124">Дополнительные сведения и примеры см. в разделе [с помощью дисперсию Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="a43d5-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="a43d5-125">Объявление параметров типа Variant в универсальных методах-делегатах</span><span class="sxs-lookup"><span data-stu-id="a43d5-125">Declaring Variant Type Parameters in Generic Delegates</span></span>  
 <span data-ttu-id="a43d5-126">Если универсальный метод-делегат содержит ковариантные или контравариантные параметры универсального типа, он может называться *вариантных универсальных делегатов*.</span><span class="sxs-lookup"><span data-stu-id="a43d5-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>  
  
 <span data-ttu-id="a43d5-127">Параметр универсального типа можно объявить ковариантный универсальный делегат с помощью `out` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="a43d5-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="a43d5-128">Параметры ковариантного типа может использоваться только в качестве типа возвращаемого значения метода, а не как тип аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="a43d5-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="a43d5-129">В следующем примере кода показано, как объявить ковариантный универсальный делегат.</span><span class="sxs-lookup"><span data-stu-id="a43d5-129">The following code example shows how to declare a covariant generic delegate.</span></span>  
  
<span data-ttu-id="a43d5-130"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a43d5-130"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="a43d5-131">Контравариантного параметра универсального типа в универсальный делегат можно объявить с помощью `in` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="a43d5-131">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="a43d5-132">Контравариантный тип можно использовать только в качестве типа аргументов метода, а не как тип возвращаемого значения метода.</span><span class="sxs-lookup"><span data-stu-id="a43d5-132">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="a43d5-133">В следующем примере кода показано, как объявить контравариантный универсальный делегат.</span><span class="sxs-lookup"><span data-stu-id="a43d5-133">The following code example shows how to declare a contravariant generic delegate.</span></span>  
  
<span data-ttu-id="a43d5-134"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a43d5-134"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
> [!IMPORTANT]
> <span data-ttu-id="a43d5-135"> `ByRef`в Visual Basic не может быть помечен как данные variant.</span><span class="sxs-lookup"><span data-stu-id="a43d5-135"> `ByRef` parameters in Visual Basic can't be marked as variant.</span></span>  
  
 <span data-ttu-id="a43d5-136">Также можно реализовать поддержку вариативности и ковариации в тот же делегат, но для разных параметров типа.</span><span class="sxs-lookup"><span data-stu-id="a43d5-136">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="a43d5-137">Эти действия показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a43d5-137">This is shown in the following example.</span></span>  
  
<span data-ttu-id="a43d5-138"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a43d5-138"><CodeContentPlaceHolder>7</CodeContentPlaceHolder></span></span>  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="a43d5-139">Создание экземпляра и вызов вариативных универсальных методов-делегатов</span><span class="sxs-lookup"><span data-stu-id="a43d5-139">Instantiating and Invoking Variant Generic Delegates</span></span>  
 <span data-ttu-id="a43d5-140">Можно создать и вызов вариативных делегатов как экземпляра и вызове инвариантных делегатов.</span><span class="sxs-lookup"><span data-stu-id="a43d5-140">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="a43d5-141">В следующем примере создается экземпляр делегата, лямбда-выражение.</span><span class="sxs-lookup"><span data-stu-id="a43d5-141">In the following example, the delegate is instantiated by a lambda expression.</span></span>  
  
<span data-ttu-id="a43d5-142"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a43d5-142"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="a43d5-143">Объединение вариативных универсальных методов-делегатов</span><span class="sxs-lookup"><span data-stu-id="a43d5-143">Combining Variant Generic Delegates</span></span>  
 <span data-ttu-id="a43d5-144">Не следует объединять вариантные делегаты.</span><span class="sxs-lookup"><span data-stu-id="a43d5-144">You should not combine variant delegates.</span></span> <span data-ttu-id="a43d5-145"><xref:System.Delegate.Combine%2A>Метод не поддерживает преобразование вариантных делегатов и ожидает делегаты точно того же типа.</xref:System.Delegate.Combine%2A></span><span class="sxs-lookup"><span data-stu-id="a43d5-145">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="a43d5-146">Это может привести к исключение времени выполнения при объединении делегатов с помощью <xref:System.Delegate.Combine%2A>метод (в C# и Visual Basic) или с помощью `+` оператора (в C#), как показано в следующем примере кода.</xref:System.Delegate.Combine%2A></span><span class="sxs-lookup"><span data-stu-id="a43d5-146">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.</span></span>  
  
<span data-ttu-id="a43d5-147"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="a43d5-147"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="a43d5-148">Вариативность в параметрах универсального типа для значений и ссылочные типы</span><span class="sxs-lookup"><span data-stu-id="a43d5-148">Variance in Generic Type Parameters for Value and Reference Types</span></span>  
 <span data-ttu-id="a43d5-149">Вариативность для параметров универсального типа поддерживается только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="a43d5-149">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="a43d5-150">Например `DVariant(Of Int)`не может быть неявно преобразован к `DVariant(Of Object)` или `DVariant(Of Long)`, так как целое число — это тип значения.</span><span class="sxs-lookup"><span data-stu-id="a43d5-150">For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.</span></span>  
  
 <span data-ttu-id="a43d5-151">В следующем примере показано, что Вариативность в универсальных типов параметров не поддерживается для типов значений.</span><span class="sxs-lookup"><span data-stu-id="a43d5-151">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>  
  
```vb  
' The type T is covariant.  
Public Delegate Function DVariant(Of Out T)() As T  
' The type T is invariant.  
Public Delegate Function DInvariant(Of T)() As T  
Sub Test()  
    Dim i As Integer = 0  
    Dim dInt As DInvariant(Of Integer) = Function() i  
    Dim dVaraintInt As DVariant(Of Integer) = Function() i  
  
    ' All of the following statements generate a compiler error  
    ' because type variance in generic parameters is not supported  
    ' for value types, even if generic type parameters are declared variant.  
    ' Dim dObject As DInvariant(Of Object) = dInt  
    ' Dim dLong As DInvariant(Of Long) = dInt  
    ' Dim dVaraintObject As DInvariant(Of Object) = dInt  
    ' Dim dVaraintLong As DInvariant(Of Long) = dInt  
End Sub  
```  
  
## <a name="relaxed-delegate-conversion-in-visual-basic"></a><span data-ttu-id="a43d5-152">Неявное преобразование делегата в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a43d5-152">Relaxed Delegate Conversion in Visual Basic</span></span>  
 <span data-ttu-id="a43d5-153">Неявное преобразование делегата обеспечивает большую гибкость при сопоставлении сигнатур методов с типами делегатов.</span><span class="sxs-lookup"><span data-stu-id="a43d5-153">Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types.</span></span> <span data-ttu-id="a43d5-154">Например он позволяет опустить спецификации параметров и опустить возвращаемые значения функции при назначении метода делегату.</span><span class="sxs-lookup"><span data-stu-id="a43d5-154">For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate.</span></span> <span data-ttu-id="a43d5-155">Дополнительные сведения см. в разделе [неявное преобразование делегата](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="a43d5-155">For more information, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a43d5-156">См. также</span><span class="sxs-lookup"><span data-stu-id="a43d5-156">See Also</span></span>  
 <span data-ttu-id="a43d5-157">[Универсальные шаблоны](https://msdn.microsoft.com/library/ms172192) </span><span class="sxs-lookup"><span data-stu-id="a43d5-157">[Generics](https://msdn.microsoft.com/library/ms172192) </span></span>  
<span data-ttu-id="a43d5-158"> [Использование вариативности в Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="a43d5-158"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
