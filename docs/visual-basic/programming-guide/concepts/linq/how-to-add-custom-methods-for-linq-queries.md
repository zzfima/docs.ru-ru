---
title: "Практическое руководство: Добавление пользовательских методов для запросов LINQ (Visual Basic) | Документы Microsoft"
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
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
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
ms.openlocfilehash: 166eb731d41e009c374ba55f929eed302793ecd0
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="5eadc-102">Практическое руководство: Добавление пользовательских методов для запросов LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5eadc-102">How to: Add Custom Methods for LINQ Queries (Visual Basic)</span></span>
<span data-ttu-id="5eadc-103">Можно расширить набор методов, которые можно использовать для запросов LINQ путем добавления методов расширения в <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5eadc-103">You can extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="5eadc-104">Например Помимо стандартных среднее или максимальное число операций, можно создать настраиваемый статистический метод для вычисления одного значения на основе последовательности значений.</span><span class="sxs-lookup"><span data-stu-id="5eadc-104">For example, in addition to the standard average or maximum operations, you can create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="5eadc-105">Также можно создать метод, который работает как настраиваемый фильтр или особое преобразование данных для последовательности значений и возвращает новую последовательность.</span><span class="sxs-lookup"><span data-stu-id="5eadc-105">You can also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="5eadc-106">Примерами таких методов являются <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>и <xref:System.Linq.Enumerable.Reverse%2A>.</xref:System.Linq.Enumerable.Reverse%2A> </xref:System.Linq.Enumerable.Skip%2A> </xref:System.Linq.Enumerable.Distinct%2A></span><span class="sxs-lookup"><span data-stu-id="5eadc-106">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>  
  
 <span data-ttu-id="5eadc-107">При расширении <xref:System.Collections.Generic.IEnumerable%601>интерфейс, пользовательские методы можно применять к любой перечислимой коллекции.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5eadc-107">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="5eadc-108">Дополнительные сведения см. в разделе [методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="5eadc-108">For more information, see [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).</span></span>  
  
## <a name="adding-an-aggregate-method"></a><span data-ttu-id="5eadc-109">Добавление статистического метода</span><span class="sxs-lookup"><span data-stu-id="5eadc-109">Adding an Aggregate Method</span></span>  
 <span data-ttu-id="5eadc-110">Статистический метод вычисляет одно значение из набора значений.</span><span class="sxs-lookup"><span data-stu-id="5eadc-110">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="5eadc-111">LINQ предоставляет несколько статистических методов, включая <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>и <xref:System.Linq.Enumerable.Max%2A>.</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> </xref:System.Linq.Enumerable.Average%2A></span><span class="sxs-lookup"><span data-stu-id="5eadc-111">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="5eadc-112">Статистический метод можно создать путем добавления метода расширения в <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5eadc-112">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 <span data-ttu-id="5eadc-113">В следующем примере кода показано, как создать метод расширения `Median` для вычисления медианы последовательности чисел типа `double`.</span><span class="sxs-lookup"><span data-stu-id="5eadc-113">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module LINQExtension  
  
    ' Extension method for the IEnumerable(of T) interface.   
    ' The method accepts only values of the Double type.  
    <Extension()>   
    Function Median(ByVal source As IEnumerable(Of Double)) As Double  
        If source.Count = 0 Then  
            Throw New InvalidOperationException("Cannot compute median for an empty set.")  
        End If  
  
        Dim sortedSource = From number In source   
                           Order By number  
  
        Dim itemIndex = sortedSource.Count \ 2  
  
        If sortedSource.Count Mod 2 = 0 Then  
            ' Even number of items in list.  
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2  
        Else  
            ' Odd number of items in list.  
            Return sortedSource(itemIndex)  
        End If  
    End Function  
End Module  
```  
  
 <span data-ttu-id="5eadc-114">Этот метод расширения вызывается для любой перечислимой коллекции в так же, как и другие статистические методы из <xref:System.Collections.Generic.IEnumerable%601>интерфейса.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5eadc-114">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5eadc-115">В Visual Basic можно использовать вызов метода или стандартный синтаксис запроса для `Aggregate` или `Group By` предложения.</span><span class="sxs-lookup"><span data-stu-id="5eadc-115">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="5eadc-116">Дополнительные сведения см. в разделе [предложения Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md) и [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5eadc-116">For more information, see [Aggregate Clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md).</span></span>  
  
 <span data-ttu-id="5eadc-117">В следующем примере кода показано, как использовать `Median` метод массивом типа `double`.</span><span class="sxs-lookup"><span data-stu-id="5eadc-117">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>  
  
<span data-ttu-id="5eadc-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="5eadc-118"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="5eadc-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="5eadc-119"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="5eadc-120">Перегрузка статистического метода для принятия различных типов</span><span class="sxs-lookup"><span data-stu-id="5eadc-120">Overloading an Aggregate Method to Accept Various Types</span></span>  
 <span data-ttu-id="5eadc-121">Статистический метод можно перегрузить, чтобы он принимал последовательности различных типов.</span><span class="sxs-lookup"><span data-stu-id="5eadc-121">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="5eadc-122">Стандартный подход — создание перегрузки для каждого типа.</span><span class="sxs-lookup"><span data-stu-id="5eadc-122">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="5eadc-123">Другой подход заключается в создании перегрузки, которая будет принимать универсального типа и преобразуют его в конкретный тип с помощью делегата.</span><span class="sxs-lookup"><span data-stu-id="5eadc-123">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="5eadc-124">Также можно сочетать оба подхода.</span><span class="sxs-lookup"><span data-stu-id="5eadc-124">You can also combine both approaches.</span></span>  
  
#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="5eadc-125">Создание перегрузки для каждого типа</span><span class="sxs-lookup"><span data-stu-id="5eadc-125">To create an overload for each type</span></span>  
 <span data-ttu-id="5eadc-126">Можно создать определенные перегрузки для каждого типа, который требуется поддерживать.</span><span class="sxs-lookup"><span data-stu-id="5eadc-126">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="5eadc-127">В следующем примере кода показана перегрузка `Median` метод `integer` типа.</span><span class="sxs-lookup"><span data-stu-id="5eadc-127">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>  
  
<span data-ttu-id="5eadc-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="5eadc-128"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="5eadc-129">Теперь можно вызвать `Median` перегрузки для обоих `integer` и `double` типов, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="5eadc-129">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>  
  
<span data-ttu-id="5eadc-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="5eadc-130"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="5eadc-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="5eadc-131"><CodeContentPlaceHolder>5</CodeContentPlaceHolder></span></span>  
<span data-ttu-id="5eadc-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="5eadc-132"><CodeContentPlaceHolder>6</CodeContentPlaceHolder></span></span>  
#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="5eadc-133">Чтобы создать универсальную перегрузку</span><span class="sxs-lookup"><span data-stu-id="5eadc-133">To create a generic overload</span></span>  
 <span data-ttu-id="5eadc-134">Можно также создать перегрузку, которая принимает последовательность универсальных объектов.</span><span class="sxs-lookup"><span data-stu-id="5eadc-134">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="5eadc-135">Эта перегрузка принимает делегат в качестве параметра и применяет его для преобразования последовательности объектов универсального типа для конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="5eadc-135">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>  
  
 <span data-ttu-id="5eadc-136">В следующем коде показано перегрузку `Median` метода, принимающего <xref:System.Func%602>делегат в качестве параметра.</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="5eadc-136">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="5eadc-137">Этот делегат принимает объект универсального типа T и возвращает объект типа `double`.</span><span class="sxs-lookup"><span data-stu-id="5eadc-137">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>  
  
```vb  
' Generic overload.  
  
<Extension()>   
Function Median(Of T)(ByVal source As IEnumerable(Of T),   
                      ByVal selector As Func(Of T, Double)) As Double  
    Return Aggregate num In source Select selector(num) Into med = Median()  
End Function  
```  
  
 <span data-ttu-id="5eadc-138">Теперь можно вызвать `Median` метод для последовательности объектов любого типа.</span><span class="sxs-lookup"><span data-stu-id="5eadc-138">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="5eadc-139">Если тип не имеет свой собственный перегруженный метод, необходимо передать параметр-делегат.</span><span class="sxs-lookup"><span data-stu-id="5eadc-139">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="5eadc-140">В Visual Basic можно использовать лямбда-выражение для этой цели.</span><span class="sxs-lookup"><span data-stu-id="5eadc-140">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="5eadc-141">Кроме того при использовании `Aggregate` или `Group By` предложение вместо вызова метода можно передать любое значение или выражение, которое находится в области видимости этого предложения.</span><span class="sxs-lookup"><span data-stu-id="5eadc-141">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>  
  
 <span data-ttu-id="5eadc-142">В следующем примере кода показано, как вызвать `Median` метод массив целых чисел и массива строк.</span><span class="sxs-lookup"><span data-stu-id="5eadc-142">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="5eadc-143">Для строк вычисляется Медиана длин строк в массиве.</span><span class="sxs-lookup"><span data-stu-id="5eadc-143">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="5eadc-144">В примере для передачи <xref:System.Func%602>параметр-делегат `Median` метод для каждого случая.</xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="5eadc-144">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>  
  
<span data-ttu-id="5eadc-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="5eadc-145"><CodeContentPlaceHolder>8</CodeContentPlaceHolder></span></span>  
## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="5eadc-146">Добавление метода, возвращающего коллекцию</span><span class="sxs-lookup"><span data-stu-id="5eadc-146">Adding a Method That Returns a Collection</span></span>  
 <span data-ttu-id="5eadc-147">Вы можете расширить <xref:System.Collections.Generic.IEnumerable%601>интерфейса с помощью пользовательского запроса метода, который возвращает последовательность значений.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5eadc-147">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="5eadc-148">В этом случае метод должен возвращать коллекцию типа <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5eadc-148">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="5eadc-149">Эти методы можно использовать для применения фильтров или преобразований данных к последовательности значений.</span><span class="sxs-lookup"><span data-stu-id="5eadc-149">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>  
  
 <span data-ttu-id="5eadc-150">Приведенный ниже показано, как создать метод расширения с именем `AlternateElements` , возвращает каждый второй элемент в коллекции, начиная с первого элемента.</span><span class="sxs-lookup"><span data-stu-id="5eadc-150">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>  
  
<span data-ttu-id="5eadc-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="5eadc-151"><CodeContentPlaceHolder>9</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="5eadc-152">Этот метод расширения можно вызвать для любой перечислимой коллекции так же, как и другие методы из <xref:System.Collections.Generic.IEnumerable%601>интерфейс, как показано в следующем коде:</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5eadc-152">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>  
  
```vb  
Dim strings() As String = {"a", "b", "c", "d", "e"}  
  
Dim query = strings.AlternateElements()  
  
For Each element In query  
    Console.WriteLine(element)  
Next  
  
' This code produces the following output:  
'  
' a  
' c  
' e  
```  
  
## <a name="see-also"></a><span data-ttu-id="5eadc-153">См. также</span><span class="sxs-lookup"><span data-stu-id="5eadc-153">See Also</span></span>  
 <span data-ttu-id="5eadc-154"><xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="5eadc-154"><xref:System.Collections.Generic.IEnumerable%601></span></span>   
<span data-ttu-id="5eadc-155"> [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span><span class="sxs-lookup"><span data-stu-id="5eadc-155"> [Extension Methods](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)</span></span>
