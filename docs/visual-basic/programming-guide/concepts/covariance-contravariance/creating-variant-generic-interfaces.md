---
title: "Создание вариативных универсальных интерфейсов (Visual Basic) | Документы Microsoft"
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
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a2cbf0a204a5a3af45f55a14c011518c7021f5b4
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="creating-variant-generic-interfaces-visual-basic"></a><span data-ttu-id="38cd1-102">Создание вариативных универсальных интерфейсов (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38cd1-102">Creating Variant Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="38cd1-103">Можно объявить параметры универсального типа в интерфейсах как ковариантные или контравариантные.</span><span class="sxs-lookup"><span data-stu-id="38cd1-103">You can declare generic type parameters in interfaces as covariant or contravariant.</span></span> <span data-ttu-id="38cd1-104">*Ковариация* позволяет методам интерфейса иметь более производные типы возвращаемых значений, чем указано параметрами универсального типа.</span><span class="sxs-lookup"><span data-stu-id="38cd1-104">*Covariance* allows interface methods to have more derived return types than that defined by the generic type parameters.</span></span> <span data-ttu-id="38cd1-105">*Контрвариантность* позволяет методам интерфейса иметь типы аргументов, для которых меньше, чем указано параметрами универсального.</span><span class="sxs-lookup"><span data-stu-id="38cd1-105">*Contravariance* allows interface methods to have argument types that are less derived than that specified by the generic parameters.</span></span> <span data-ttu-id="38cd1-106">Универсальный интерфейс, который имеет ковариантные или контравариантные параметры универсального типа, называется *вариант*.</span><span class="sxs-lookup"><span data-stu-id="38cd1-106">A generic interface that has covariant or contravariant generic type parameters is called *variant*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38cd1-107">Платформа .NET framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="38cd1-107">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="38cd1-108">Список вариативных интерфейсов в платформе .NET Framework см. в разделе [Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="38cd1-108">For the list of the variant interfaces in the .NET Framework, see [Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).</span></span>  
  
## <a name="declaring-variant-generic-interfaces"></a><span data-ttu-id="38cd1-109">Объявление вариативных универсальных интерфейсов</span><span class="sxs-lookup"><span data-stu-id="38cd1-109">Declaring Variant Generic Interfaces</span></span>  
 <span data-ttu-id="38cd1-110">Вариативные универсальные интерфейсы можно объявить с помощью `in` и `out` ключевые слова для параметров универсального типа.</span><span class="sxs-lookup"><span data-stu-id="38cd1-110">You can declare variant generic interfaces by using the `in` and `out` keywords for generic type parameters.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="38cd1-111"> `ByRef`в Visual Basic не может быть типа variant.</span><span class="sxs-lookup"><span data-stu-id="38cd1-111"> `ByRef` parameters in Visual Basic cannot be variant.</span></span> <span data-ttu-id="38cd1-112">Типы значений также не поддерживают вариативность.</span><span class="sxs-lookup"><span data-stu-id="38cd1-112">Value types also do not support variance.</span></span>  
  
 <span data-ttu-id="38cd1-113">Параметр универсального типа можно объявить ковариантный с помощью `out` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="38cd1-113">You can declare a generic type parameter covariant by using the `out` keyword.</span></span> <span data-ttu-id="38cd1-114">Ковариантный тип должен удовлетворять следующим условиям:</span><span class="sxs-lookup"><span data-stu-id="38cd1-114">The covariant type must satisfy the following conditions:</span></span>  
  
-   <span data-ttu-id="38cd1-115">Тип используется только как тип возвращаемого значения методов интерфейса и не используется в качестве типа аргументов метода.</span><span class="sxs-lookup"><span data-stu-id="38cd1-115">The type is used only as a return type of interface methods and not used as a type of method arguments.</span></span> <span data-ttu-id="38cd1-116">Это показано в следующем примере, в котором тип `R` объявлен ковариантным.</span><span class="sxs-lookup"><span data-stu-id="38cd1-116">This is illustrated in the following example, in which the type `R` is declared covariant.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     <span data-ttu-id="38cd1-117">Существует одно исключение из данного правила.</span><span class="sxs-lookup"><span data-stu-id="38cd1-117">There is one exception to this rule.</span></span> <span data-ttu-id="38cd1-118">Если контравариантный универсальный делегат в качестве параметра метода, можно использовать тип параметра универсального типа для делегата.</span><span class="sxs-lookup"><span data-stu-id="38cd1-118">If you have a contravariant generic delegate as a method parameter, you can use the type as a generic type parameter for the delegate.</span></span> <span data-ttu-id="38cd1-119">Это показано с помощью типа `R` в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="38cd1-119">This is illustrated by the type `R` in the following example.</span></span> <span data-ttu-id="38cd1-120">Дополнительные сведения см. в разделе [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) и [с помощью дисперсию Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="38cd1-120">For more information, see [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   <span data-ttu-id="38cd1-121">Тип не используется в качестве универсального ограничения для методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="38cd1-121">The type is not used as a generic constraint for the interface methods.</span></span> <span data-ttu-id="38cd1-122">Это показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="38cd1-122">This is illustrated in the following code.</span></span>  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 <span data-ttu-id="38cd1-123">Контравариантного параметра универсального типа можно объявить с помощью `in` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="38cd1-123">You can declare a generic type parameter contravariant by using the `in` keyword.</span></span> <span data-ttu-id="38cd1-124">Контравариантный тип можно использовать только в качестве типа аргументов метода, а не как тип возвращаемого значения методов интерфейса.</span><span class="sxs-lookup"><span data-stu-id="38cd1-124">The contravariant type can be used only as a type of method arguments and not as a return type of interface methods.</span></span> <span data-ttu-id="38cd1-125">Контравариантный тип можно использовать также для универсальных ограничений.</span><span class="sxs-lookup"><span data-stu-id="38cd1-125">The contravariant type can also be used for generic constraints.</span></span> <span data-ttu-id="38cd1-126">В следующем коде показано объявление контравариантного интерфейса и использование универсального ограничения для одного из его методов.</span><span class="sxs-lookup"><span data-stu-id="38cd1-126">The following code shows how to declare a contravariant interface and use a generic constraint for one of its methods.</span></span>  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 <span data-ttu-id="38cd1-127">Это также можно реализовать поддержку ковариации и контравариации в тот же интерфейс, но для разных параметров типа, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="38cd1-127">It is also possible to support both covariance and contravariance in the same interface, but for different type parameters, as shown in the following code example.</span></span>  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 <span data-ttu-id="38cd1-128">В Visual Basic нельзя объявлять события в вариативных интерфейсах без указания типа делегата.</span><span class="sxs-lookup"><span data-stu-id="38cd1-128">In Visual Basic, you can't declare events in variant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="38cd1-129">Кроме того вариантный интерфейс не может включать вложенные классы, перечисления или структуры, но он может включать вложенные интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="38cd1-129">Also, a variant interface can't have nested classes, enums, or structures, but it can have nested interfaces.</span></span> <span data-ttu-id="38cd1-130">Это показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="38cd1-130">This is illustrated in the following code.</span></span>  
  
```vb  
Interface ICovariant(Of Out R)  
    ' The following statement generates a compiler error.  
    ' Event SampleEvent()  
    ' The following statement specifies the delegate type and   
    ' does not generate an error.  
    Event AnotherEvent As EventHandler  
  
    ' The following statements generate compiler errors,  
    ' because a variant interface cannot have  
    ' nested enums, classes, or structures.  
  
    'Enum SampleEnum : test : End Enum  
    'Class SampleClass : End Class  
    'Structure SampleStructure : Dim value As Integer : End Structure  
  
    ' Variant interfaces can have nested interfaces.  
    Interface INested : End Interface  
End Interface  
```  
  
## <a name="implementing-variant-generic-interfaces"></a><span data-ttu-id="38cd1-131">Реализация вариативных универсальных интерфейсов</span><span class="sxs-lookup"><span data-stu-id="38cd1-131">Implementing Variant Generic Interfaces</span></span>  
 <span data-ttu-id="38cd1-132">Для реализации вариативных универсальных интерфейсов в классах, используя тот же синтаксис, используемый для инвариантных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="38cd1-132">You implement variant generic interfaces in classes by using the same syntax that is used for invariant interfaces.</span></span> <span data-ttu-id="38cd1-133">В следующем примере кода показана реализация ковариантного интерфейса в универсальном классе.</span><span class="sxs-lookup"><span data-stu-id="38cd1-133">The following code example shows how to implement a covariant interface in a generic class.</span></span>  
  
```vb  
Interface ICovariant(Of Out R)  
    Function GetSomething() As R  
End Interface  
  
Class SampleImplementation(Of R)  
    Implements ICovariant(Of R)  
    Public Function GetSomething() As R _  
    Implements ICovariant(Of R).GetSomething  
        ' Some code.  
    End Function  
End Class  
```  
  
 <span data-ttu-id="38cd1-134">Классы, которые реализуют вариативные интерфейсы, являются инвариантными.</span><span class="sxs-lookup"><span data-stu-id="38cd1-134">Classes that implement variant interfaces are invariant.</span></span> <span data-ttu-id="38cd1-135">Например, рассмотрим следующий код.</span><span class="sxs-lookup"><span data-stu-id="38cd1-135">For example, consider the following code.</span></span>  
  
```vb  
 The interface is covariant.  
Dim ibutton As ICovariant(Of Button) =  
    New SampleImplementation(Of Button)  
Dim iobj As ICovariant(Of Object) = ibutton  
  
' The class is invariant.  
Dim button As SampleImplementation(Of Button) =  
    New SampleImplementation(Of Button)  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim obj As SampleImplementation(Of Object) = button  
```  
  
## <a name="extending-variant-generic-interfaces"></a><span data-ttu-id="38cd1-136">Расширение вариативных универсальных интерфейсов</span><span class="sxs-lookup"><span data-stu-id="38cd1-136">Extending Variant Generic Interfaces</span></span>  
 <span data-ttu-id="38cd1-137">При расширении вариативных универсальных интерфейсов необходимо использовать `in` и `out` ключевые слова для явного указания того, поддерживает ли вариативность производный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="38cd1-137">When you extend a variant generic interface, you have to use the `in` and `out` keywords to explicitly specify whether the derived interface supports variance.</span></span> <span data-ttu-id="38cd1-138">Компилятор не подразумевает вариативность интерфейса, который расширяется.</span><span class="sxs-lookup"><span data-stu-id="38cd1-138">The compiler does not infer the variance from the interface that is being extended.</span></span> <span data-ttu-id="38cd1-139">Например рассмотрим следующие интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="38cd1-139">For example, consider the following interfaces.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T)  
End Interface  
  
Interface IExtCovariant(Of Out T)  
    Inherits ICovariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="38cd1-140">В `Invariant(Of T)` интерфейса параметра универсального типа `T` является инвариантным, тогда как в `IExtCovariant (Of Out T)`параметр типа является ковариантным, хотя оба интерфейса расширяют тот же интерфейс.</span><span class="sxs-lookup"><span data-stu-id="38cd1-140">In the `Invariant(Of T)` interface, the generic type parameter `T` is invariant, whereas in `IExtCovariant (Of Out T)`the type parameter is covariant, although both interfaces extend the same interface.</span></span> <span data-ttu-id="38cd1-141">То же правило применяется к контравариантные параметры универсального типа.</span><span class="sxs-lookup"><span data-stu-id="38cd1-141">The same rule is applied to contravariant generic type parameters.</span></span>  
  
 <span data-ttu-id="38cd1-142">Можно создать интерфейс, который расширяет и интерфейс, в котором параметр универсального типа `T` является ковариантным, и интерфейс, где является контравариантным, если в расширяемом интерфейсе параметр универсального типа `T` является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="38cd1-142">You can create an interface that extends both the interface where the generic type parameter `T` is covariant and the interface where it is contravariant if in the extending interface the generic type parameter `T` is invariant.</span></span> <span data-ttu-id="38cd1-143">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="38cd1-143">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 <span data-ttu-id="38cd1-144">Тем не менее если параметр универсального типа `T` является объявлен ковариантным в одном интерфейсе, его нельзя объявить контравариантным в расширенном интерфейсе и наоборот.</span><span class="sxs-lookup"><span data-stu-id="38cd1-144">However, if a generic type parameter `T` is declared covariant in one interface, you cannot declare it contravariant in the extending interface, or vice versa.</span></span> <span data-ttu-id="38cd1-145">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="38cd1-145">This is illustrated in the following code example.</span></span>  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a><span data-ttu-id="38cd1-146">Чтобы избежать неоднозначности</span><span class="sxs-lookup"><span data-stu-id="38cd1-146">Avoiding Ambiguity</span></span>  
 <span data-ttu-id="38cd1-147">При реализации вариативных универсальных интерфейсов вариативность может привести к неоднозначности.</span><span class="sxs-lookup"><span data-stu-id="38cd1-147">When you implement variant generic interfaces, variance can sometimes lead to ambiguity.</span></span> <span data-ttu-id="38cd1-148">Этого следует избегать.</span><span class="sxs-lookup"><span data-stu-id="38cd1-148">This should be avoided.</span></span>  
  
 <span data-ttu-id="38cd1-149">Например если же вариантных универсальных интерфейсов с разными обобщенными параметрами явно реализовать в один класс, можно создать неоднозначности.</span><span class="sxs-lookup"><span data-stu-id="38cd1-149">For example, if you explicitly implement the same variant generic interface with different generic type parameters in one class, it can create ambiguity.</span></span> <span data-ttu-id="38cd1-150">Компилятор сообщает об ошибке, в данном случае, но не указано, какая реализация интерфейса будет выбрана во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="38cd1-150">The compiler does not produce an error in this case, but it is not specified which interface implementation will be chosen at runtime.</span></span> <span data-ttu-id="38cd1-151">Это может привести к возникновению неявных ошибок в коде.</span><span class="sxs-lookup"><span data-stu-id="38cd1-151">This could lead to subtle bugs in your code.</span></span> <span data-ttu-id="38cd1-152">Рассмотрим следующий пример кода.</span><span class="sxs-lookup"><span data-stu-id="38cd1-152">Consider the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38cd1-153">С `Option Strict Off`, Visual Basic создаст предупреждение компилятора при наличии неоднозначной реализации интерфейса.</span><span class="sxs-lookup"><span data-stu-id="38cd1-153">With `Option Strict Off`, Visual Basic generates a compiler warning when there is an ambiguous interface implementation.</span></span> <span data-ttu-id="38cd1-154">С `Option Strict On`, Visual Basic создает ошибку компилятора.</span><span class="sxs-lookup"><span data-stu-id="38cd1-154">With `Option Strict On`, Visual Basic generates a compiler error.</span></span>  
  
```vb  
' Simple class hierarchy.  
Class Animal  
End Class  
  
Class Cat  
    Inherits Animal  
End Class  
  
Class Dog  
    Inherits Animal  
End Class  
  
' This class introduces ambiguity  
' because IEnumerable(Of Out T) is covariant.  
Class Pets  
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)  
  
    Public Function GetEnumerator() As IEnumerator(Of Cat) _  
        Implements IEnumerable(Of Cat).GetEnumerator  
        Console.WriteLine("Cat")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator(Of Dog) _  
        Implements IEnumerable(Of Dog).GetEnumerator  
        Console.WriteLine("Dog")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator2() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
        ' Some code.  
    End Function  
End Class  
  
Sub Main()  
    Dim pets As IEnumerable(Of Animal) = New Pets()  
    pets.GetEnumerator()  
End Sub  
```  
  
 <span data-ttu-id="38cd1-155">В этом примере не указано как `pets.GetEnumerator` метод выбирает между `Cat` и `Dog`.</span><span class="sxs-lookup"><span data-stu-id="38cd1-155">In this example, it is unspecified how the `pets.GetEnumerator` method chooses between `Cat` and `Dog`.</span></span> <span data-ttu-id="38cd1-156">Это может вызвать проблемы в коде.</span><span class="sxs-lookup"><span data-stu-id="38cd1-156">This could cause problems in your code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cd1-157">См. также</span><span class="sxs-lookup"><span data-stu-id="38cd1-157">See Also</span></span>  
 <span data-ttu-id="38cd1-158">[Вариативность в универсальных интерфейсах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="38cd1-158">[Variance in Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) </span></span>  
<span data-ttu-id="38cd1-159"> [Использование вариативности в Func и Action универсальные делегаты (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="38cd1-159"> [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)</span></span>
