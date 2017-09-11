---
title: "Коллекции (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b3c8de3e22075d576f86bcd4eb599946740ebe16
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="collections-visual-basic"></a><span data-ttu-id="4a4cf-102">Коллекции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a4cf-102">Collections (Visual Basic)</span></span>
<span data-ttu-id="4a4cf-103">Во многих приложениях требуется создавать группы связанных объектов и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-103">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="4a4cf-104">Существует два способа группировки объектов: создать массив объектов и создать коллекцию.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-104">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>  
  
 <span data-ttu-id="4a4cf-105">Массивы удобнее всего использовать для создания и работы с фиксированным числом строго типизированных объектов.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-105">Arrays are most useful for creating and working with a fixed number of strongly-typed objects.</span></span> <span data-ttu-id="4a4cf-106">Сведения о массивах см. в разделе [массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a4cf-106">For information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
 <span data-ttu-id="4a4cf-107">Коллекции предоставляют более гибкий способ работы с группами объектов.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-107">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="4a4cf-108">В отличие от массивов, коллекция, с которой вы работаете, может расти или уменьшаться динамически при необходимости.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-108">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="4a4cf-109">Некоторые коллекции допускают назначение ключа любому объекту, который добавляется в коллекцию, чтобы в дальнейшем можно было быстро извлечь связанный с ключом объект из коллекции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-109">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>  
  
 <span data-ttu-id="4a4cf-110">Коллекция является классом, поэтому необходимо объявить экземпляр класса перед добавлением в коллекцию элементов.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-110">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>  
  
 <span data-ttu-id="4a4cf-111">Если коллекция содержит элементы только одного типа данных, можно использовать один из классов в <xref:System.Collections.Generic?displayProperty=fullName>имен.</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4a4cf-111">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=fullName> namespace.</span></span> <span data-ttu-id="4a4cf-112">Универсальная коллекция обеспечивает строгую типизацию, так что в нее нельзя добавить другие типы данных.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-112">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="4a4cf-113">При извлечении элемента из универсальной коллекции не нужно определять или преобразовывать его тип данных.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-113">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a4cf-114">Примеры в этом разделе, включают [импорта](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) инструкции для `System.Collections.Generic` и `System.Linq` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-114">For the examples in this topic, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>  
  
 <span data-ttu-id="4a4cf-115">**Содержание раздела**</span><span class="sxs-lookup"><span data-stu-id="4a4cf-115">**In this topic**</span></span>  
  
-   [<span data-ttu-id="4a4cf-116">С помощью простой коллекции</span><span class="sxs-lookup"><span data-stu-id="4a4cf-116">Using a Simple Collection</span></span>](#BKMK_SimpleCollection)  
  
-   [<span data-ttu-id="4a4cf-117">Типы коллекций</span><span class="sxs-lookup"><span data-stu-id="4a4cf-117">Kinds of Collections</span></span>](#BKMK_KindsOfCollections)  
  
    -   [<span data-ttu-id="4a4cf-118">Классы System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="4a4cf-118">System.Collections.Generic Classes</span></span>](#BKMK_Generic)  
  
    -   [<span data-ttu-id="4a4cf-119">Классы System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="4a4cf-119">System.Collections.Concurrent Classes</span></span>](#BKMK_Concurrent)  
  
    -   [<span data-ttu-id="4a4cf-120">Классы System.Collections</span><span class="sxs-lookup"><span data-stu-id="4a4cf-120">System.Collections Classes</span></span>](#BKMK_Collections)  
  
    -   [<span data-ttu-id="4a4cf-121">Класс коллекции Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a4cf-121">Visual Basic Collection Class</span></span>](#BKMK_VisualBasic)  
  
-   [<span data-ttu-id="4a4cf-122">Реализации коллекции пар «ключ значение»</span><span class="sxs-lookup"><span data-stu-id="4a4cf-122">Implementing a Collection of Key/Value Pairs</span></span>](#BKMK_KeyValuePairs)  
  
-   [<span data-ttu-id="4a4cf-123">Использование LINQ для доступа к коллекции</span><span class="sxs-lookup"><span data-stu-id="4a4cf-123">Using LINQ to Access a Collection</span></span>](#BKMK_LINQ)  
  
-   [<span data-ttu-id="4a4cf-124">Сортировка коллекции</span><span class="sxs-lookup"><span data-stu-id="4a4cf-124">Sorting a Collection</span></span>](#BKMK_Sorting)  
  
-   [<span data-ttu-id="4a4cf-125">Определение настраиваемой коллекции</span><span class="sxs-lookup"><span data-stu-id="4a4cf-125">Defining a Custom Collection</span></span>](#BKMK_CustomCollection)  
  
-   [<span data-ttu-id="4a4cf-126">Итераторы</span><span class="sxs-lookup"><span data-stu-id="4a4cf-126">Iterators</span></span>](#BKMK_Iterators)  
  
<a name="BKMK_SimpleCollection"></a>
## <a name="using-a-simple-collection"></a><span data-ttu-id="4a4cf-127">Использование простой коллекции</span><span class="sxs-lookup"><span data-stu-id="4a4cf-127">Using a Simple Collection</span></span>  
 <span data-ttu-id="4a4cf-128">В примерах этого раздела используется универсальный <xref:System.Collections.Generic.List%601>класс, который позволяет работать со строго типизированный список объектов.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-128">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>  
  
 <span data-ttu-id="4a4cf-129">В следующем примере создается список строк и затем выполняется перебор строк с помощью [For Each... Далее](../../../visual-basic/language-reference/statements/for-each-next-statement.md) инструкции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-129">The following example creates a list of strings and then iterates through the strings by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span>  
  
```vb  
' Create a list of strings.  
Dim salmons As New List(Of String)  
salmons.Add("chinook")  
salmons.Add("coho")  
salmons.Add("pink")  
salmons.Add("sockeye")  
  
' Iterate through the list.  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="4a4cf-130">Если содержимое коллекции известны заранее, можно использовать *инициализатора коллекции* для инициализации коллекции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-130">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="4a4cf-131">Дополнительные сведения см. в разделе [инициализаторы](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a4cf-131">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>  
  
 <span data-ttu-id="4a4cf-132">Следующий пример аналогичен предыдущему за исключением того, что для добавления элементов в коллекцию используется инициализатор коллекции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-132">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="4a4cf-133">Можно использовать [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) инструкции вместо `For Each` инструкции для прохода по коллекции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-133">You can use a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement instead of a `For Each` statement to iterate through a collection.</span></span> <span data-ttu-id="4a4cf-134">Для этого доступ к элементам коллекции осуществляется по позиции индекса.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-134">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="4a4cf-135">Индекс элементов начинается с 0 и заканчивается числом, равным количеству элементов минус 1.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-135">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>  
  
 <span data-ttu-id="4a4cf-136">Следующий пример итерацию по элементам коллекции с помощью `For…Next` вместо `For Each`.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-136">The following example iterates through the elements of a collection by using `For…Next` instead of `For Each`.</span></span>  
  
```vb  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For index = 0 To salmons.Count - 1  
    Console.Write(salmons(index) & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 <span data-ttu-id="4a4cf-137">В приведенном ниже примере элемент удаляется из коллекции путем указания удаляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-137">The following example removes an element from the collection by specifying the object to remove.</span></span>  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
' Remove an element in the list by specifying  
' the object.  
salmons.Remove("coho")  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook pink sockeye  
```  
  
 <span data-ttu-id="4a4cf-138">В приведенном ниже примере удаляются элементы из универсального списка.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-138">The following example removes elements from a generic list.</span></span> <span data-ttu-id="4a4cf-139">Вместо `For Each` инструкции [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) используется инструкция, проходящий по убыванию.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-139">Instead of a `For Each` statement, a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="4a4cf-140">Это вызвано <xref:System.Collections.Generic.List%601.RemoveAt%2A>метод вызывает элементы после удаленный элемент должен иметь значение нижнего индекса.</xref:System.Collections.Generic.List%601.RemoveAt%2A></span><span class="sxs-lookup"><span data-stu-id="4a4cf-140">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>  
  
```vb  
Dim numbers As New List(Of Integer) From  
    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}  
  
' Remove odd numbers.  
For index As Integer = numbers.Count - 1 To 0 Step -1  
    If numbers(index) Mod 2 = 1 Then  
        ' Remove the element by specifying  
        ' the zero-based index in the list.  
        numbers.RemoveAt(index)  
    End If  
Next  
  
' Iterate through the list.  
' A lambda expression is placed in the ForEach method  
' of the List(T) object.  
numbers.ForEach(  
    Sub(number) Console.Write(number & " "))  
' Output: 0 2 4 6 8  
```  
  
 <span data-ttu-id="4a4cf-141">Для типа элементов массива <xref:System.Collections.Generic.List%601>можно также определить собственный класс.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-141">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="4a4cf-142">В следующем примере `Galaxy` класс, используемый <xref:System.Collections.Generic.List%601>определяется в коде.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-142">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>  
  
```vb  
Private Sub IterateThroughList()  
    Dim theGalaxies As New List(Of Galaxy) From  
        {  
            New Galaxy With {.Name = "Tadpole", .MegaLightYears = 400},  
            New Galaxy With {.Name = "Pinwheel", .MegaLightYears = 25},  
            New Galaxy With {.Name = "Milky Way", .MegaLightYears = 0},  
            New Galaxy With {.Name = "Andromeda", .MegaLightYears = 3}  
        }  
  
    For Each theGalaxy In theGalaxies  
        With theGalaxy  
            Console.WriteLine(.Name & "  " & .MegaLightYears)  
        End With  
    Next  
  
    ' Output:  
    '  Tadpole  400  
    '  Pinwheel  25  
    '  Milky Way  0  
    '  Andromeda  3  
End Sub  
  
Public Class Galaxy  
    Public Property Name As String  
    Public Property MegaLightYears As Integer  
End Class  
```  
  
<a name="BKMK_KindsOfCollections"></a>
## <a name="kinds-of-collections"></a><span data-ttu-id="4a4cf-143">Виды коллекций</span><span class="sxs-lookup"><span data-stu-id="4a4cf-143">Kinds of Collections</span></span>   
 <span data-ttu-id="4a4cf-144">Многие типовые коллекции предоставляются платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-144">Many common collections are provided by the .NET Framework.</span></span> <span data-ttu-id="4a4cf-145">Каждый тип коллекции предназначен для определенной цели.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-145">Each type of collection is designed for a specific purpose.</span></span>  
  
 <span data-ttu-id="4a4cf-146">В этом разделе описываются следующие часто используемые классы коллекций:</span><span class="sxs-lookup"><span data-stu-id="4a4cf-146">Some of the common collection classes are described in this section:</span></span>  
  
-   <span data-ttu-id="4a4cf-147">@System.Collections.Genericклассы</span><span class="sxs-lookup"><span data-stu-id="4a4cf-147">@System.Collections.Generic classes</span></span>  
  
-   <span data-ttu-id="4a4cf-148">@System.Collections.Concurrentклассы</span><span class="sxs-lookup"><span data-stu-id="4a4cf-148">@System.Collections.Concurrent classes</span></span>  
  
-   <span data-ttu-id="4a4cf-149">@System.Collectionsклассы</span><span class="sxs-lookup"><span data-stu-id="4a4cf-149">@System.Collections classes</span></span>  
  
-   <span data-ttu-id="4a4cf-150">Visual Basic `Collection` класса</span><span class="sxs-lookup"><span data-stu-id="4a4cf-150">Visual Basic `Collection` class</span></span>  
  
<a name="BKMK_Generic"></a>
### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="4a4cf-151">Классы System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="4a4cf-151">System.Collections.Generic Classes</span></span>  

 <span data-ttu-id="4a4cf-152">Можно создать универсальную коллекцию с помощью одного из классов в <xref:System.Collections.Generic>имен.</xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="4a4cf-152">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="4a4cf-153">Универсальная коллекция применяется в том случае, если все элементы в коллекции имеют одинаковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-153">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="4a4cf-154">Универсальная коллекция обеспечивает строгую типизацию, позволяя добавлять данные только необходимого типа.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-154">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>  
  
 <span data-ttu-id="4a4cf-155">В следующей таблице перечислены некоторые часто используемые классы <xref:System.Collections.Generic?displayProperty=fullName>пространство имен:</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4a4cf-155">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="4a4cf-156">Класс</span><span class="sxs-lookup"><span data-stu-id="4a4cf-156">Class</span></span>|<span data-ttu-id="4a4cf-157">Описание</span><span class="sxs-lookup"><span data-stu-id="4a4cf-157">Description</span></span>|  
|---|---|  
|<span data-ttu-id="4a4cf-158"><xref:System.Collections.Generic.Dictionary%602></xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="4a4cf-158"><xref:System.Collections.Generic.Dictionary%602></span></span>|<span data-ttu-id="4a4cf-159">Предоставляет коллекцию пар «ключ-значение», которые упорядочены по ключу.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-159">Represents a collection of key/value pairs that are organized based on the key.</span></span>|  
|<span data-ttu-id="4a4cf-160"><xref:System.Collections.Generic.List%601></xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-160"><xref:System.Collections.Generic.List%601></span></span>|<span data-ttu-id="4a4cf-161">Представляет список объектов, доступных по индексу.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-161">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="4a4cf-162">Предоставляет методы для поиска по списку, его сортировки и изменения.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-162">Provides methods to search, sort, and modify lists.</span></span>|  
|<span data-ttu-id="4a4cf-163"><xref:System.Collections.Generic.Queue%601></xref:System.Collections.Generic.Queue%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-163"><xref:System.Collections.Generic.Queue%601></span></span>|<span data-ttu-id="4a4cf-164">Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).</span><span class="sxs-lookup"><span data-stu-id="4a4cf-164">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<span data-ttu-id="4a4cf-165"><xref:System.Collections.Generic.SortedList%602></xref:System.Collections.Generic.SortedList%602></span><span class="sxs-lookup"><span data-stu-id="4a4cf-165"><xref:System.Collections.Generic.SortedList%602></span></span>|<span data-ttu-id="4a4cf-166">Представляет коллекцию пар "ключ значение", упорядоченных по ключу на основе <xref:System.Collections.Generic.IComparer%601>реализацию.</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-166">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|  
|<span data-ttu-id="4a4cf-167"><xref:System.Collections.Generic.Stack%601></xref:System.Collections.Generic.Stack%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-167"><xref:System.Collections.Generic.Stack%601></span></span>|<span data-ttu-id="4a4cf-168">Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).</span><span class="sxs-lookup"><span data-stu-id="4a4cf-168">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="4a4cf-169">Дополнительные сведения см. в разделе [часто используемые типы коллекций](http://msdn.microsoft.com/library/f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55), [Выбор класса коллекции](../../../standard/collections/selecting-a-collection-class.md)и <xref:System.Collections.Generic?displayProperty=fullName>.</xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4a4cf-169">For additional information, see [Commonly Used Collection Types](http://msdn.microsoft.com/library/f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and <xref:System.Collections.Generic?displayProperty=fullName>.</span></span>  
  
<a name="BKMK_Concurrent"></a>
### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="4a4cf-170">Классы System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="4a4cf-170">System.Collections.Concurrent Classes</span></span>   
 <span data-ttu-id="4a4cf-171">В платформе .NET Framework 4 или более поздней версии, в коллекции <xref:System.Collections.Concurrent>пространства имен предоставляют эффективный потокобезопасные операции для доступа к элементам коллекций из нескольких потоков.</xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="4a4cf-171">In the .NET Framework 4 or newer, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>  
  
 <span data-ttu-id="4a4cf-172">Классы в <xref:System.Collections.Concurrent>имен следует использовать вместо соответствующих типов в <xref:System.Collections.Generic?displayProperty=fullName>и <xref:System.Collections?displayProperty=fullName>пространства имен, когда несколько потоков параллельно обращаются к коллекции.</xref:System.Collections?displayProperty=fullName> </xref:System.Collections.Generic?displayProperty=fullName> </xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="4a4cf-172">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=fullName> and <xref:System.Collections?displayProperty=fullName> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="4a4cf-173">Дополнительные сведения см. в разделе [потокобезопасных коллекций](../../../standard/collections/threadsafe/index.md) и <xref:System.Collections.Concurrent>.</xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="4a4cf-173">For more information, see [Thread-Safe Collections](../../../standard/collections/threadsafe/index.md) and <xref:System.Collections.Concurrent>.</span></span>  
  
 <span data-ttu-id="4a4cf-174">Некоторые классы, включенные в <xref:System.Collections.Concurrent>пространства имен являются <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>и <xref:System.Collections.Concurrent.ConcurrentStack%601>.</xref:System.Collections.Concurrent.ConcurrentStack%601> </xref:System.Collections.Concurrent.ConcurrentQueue%601> </xref:System.Collections.Concurrent.ConcurrentDictionary%602> </xref:System.Collections.Concurrent.BlockingCollection%601> </xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="4a4cf-174">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>  
  
<a name="BKMK_Collections"></a>
### <a name="systemcollections-classes"></a><span data-ttu-id="4a4cf-175">Классы System.Collections</span><span class="sxs-lookup"><span data-stu-id="4a4cf-175">System.Collections Classes</span></span>    
 <span data-ttu-id="4a4cf-176">Классы в <xref:System.Collections?displayProperty=fullName>пространства имен не храните элементы конкретно типизированных объектов, а объекты типа `Object`.</xref:System.Collections?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4a4cf-176">The classes in the <xref:System.Collections?displayProperty=fullName> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>  
  
 <span data-ttu-id="4a4cf-177">По возможности следует использовать универсальные коллекции в <xref:System.Collections.Generic?displayProperty=fullName>пространства имен или <xref:System.Collections.Concurrent>имен вместо устаревших типов в `System.Collections` имен.</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4a4cf-177">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=fullName> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>  
  
 <span data-ttu-id="4a4cf-178">В следующей таблице перечислены некоторые часто используемые классы в `System.Collections` пространство имен:</span><span class="sxs-lookup"><span data-stu-id="4a4cf-178">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>  
  
|<span data-ttu-id="4a4cf-179">Класс</span><span class="sxs-lookup"><span data-stu-id="4a4cf-179">Class</span></span>|<span data-ttu-id="4a4cf-180">Описание</span><span class="sxs-lookup"><span data-stu-id="4a4cf-180">Description</span></span>|  
|---|---|  
|<span data-ttu-id="4a4cf-181"><xref:System.Collections.ArrayList></xref:System.Collections.ArrayList></span><span class="sxs-lookup"><span data-stu-id="4a4cf-181"><xref:System.Collections.ArrayList></span></span>|<span data-ttu-id="4a4cf-182">Представляет массив объектов, размер которого динамически увеличивается по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-182">Represents an array of objects whose size is dynamically increased as required.</span></span>|  
|<span data-ttu-id="4a4cf-183"><xref:System.Collections.Hashtable></xref:System.Collections.Hashtable></span><span class="sxs-lookup"><span data-stu-id="4a4cf-183"><xref:System.Collections.Hashtable></span></span>|<span data-ttu-id="4a4cf-184">Представляет коллекцию пар «ключ-значение», которые упорядочены по хэш-коду ключа.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-184">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|  
|<span data-ttu-id="4a4cf-185"><xref:System.Collections.Queue></xref:System.Collections.Queue></span><span class="sxs-lookup"><span data-stu-id="4a4cf-185"><xref:System.Collections.Queue></span></span>|<span data-ttu-id="4a4cf-186">Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).</span><span class="sxs-lookup"><span data-stu-id="4a4cf-186">Represents a first in, first out (FIFO) collection of objects.</span></span>|  
|<span data-ttu-id="4a4cf-187"><xref:System.Collections.Stack></xref:System.Collections.Stack></span><span class="sxs-lookup"><span data-stu-id="4a4cf-187"><xref:System.Collections.Stack></span></span>|<span data-ttu-id="4a4cf-188">Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).</span><span class="sxs-lookup"><span data-stu-id="4a4cf-188">Represents a last in, first out (LIFO) collection of objects.</span></span>|  
  
 <span data-ttu-id="4a4cf-189"><xref:System.Collections.Specialized>Пространство имен предоставляет классы, специализированные и строго типизированные коллекции, такие как коллекции строк и связанные списки и гибридные словари.</xref:System.Collections.Specialized></span><span class="sxs-lookup"><span data-stu-id="4a4cf-189">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>  

<a name="BKMK_VisualBasic"></a> 
###  <a name="visual-basic-collection-class"></a><span data-ttu-id="4a4cf-190">Класс Collection в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a4cf-190">Visual Basic Collection Class</span></span>  
 <span data-ttu-id="4a4cf-191">Можно использовать Visual Basic <xref:Microsoft.VisualBasic.Collection>класса для доступа к коллекции элементов с помощью числовой индекс или объект `String` ключ.</xref:Microsoft.VisualBasic.Collection></span><span class="sxs-lookup"><span data-stu-id="4a4cf-191">You can use the Visual Basic <xref:Microsoft.VisualBasic.Collection> class to access a collection item by using either a numeric index or a `String` key.</span></span> <span data-ttu-id="4a4cf-192">Элементы можно добавлять в объект коллекции с указанием или без указания ключа.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-192">You can add items to a collection object either with or without specifying a key.</span></span> <span data-ttu-id="4a4cf-193">Если добавить объект без ключа, необходимо использовать его числовой индекс для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-193">If you add an item without a key, you must use its numeric index to access it.</span></span>  
  
 <span data-ttu-id="4a4cf-194">Visual Basic `Collection` класс хранит все его элементы как тип `Object`, поэтому можно добавить элемент любого типа данных.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-194">The Visual Basic `Collection` class stores all its elements as type `Object`, so you can add an item of any data type.</span></span> <span data-ttu-id="4a4cf-195">Нет никакой защиты от добавления неподходящих типов данных.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-195">There is no safeguard against inappropriate data types being added.</span></span>  
  
 <span data-ttu-id="4a4cf-196">При использовании Visual Basic `Collection` класс, первый элемент в коллекции имеет индекс 1.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-196">When you use the Visual Basic `Collection` class, the first item in a collection has an index of 1.</span></span> <span data-ttu-id="4a4cf-197">Этим он отличается от классов коллекций платформы .NET Framework, для которых начальный индекс равен 0.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-197">This differs from the .NET Framework collection classes, for which the starting index is 0.</span></span>  
  
 <span data-ttu-id="4a4cf-198">По возможности следует использовать универсальные коллекции в <xref:System.Collections.Generic?displayProperty=fullName>пространства имен или <xref:System.Collections.Concurrent>имен вместо Visual Basic `Collection` класса</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4a4cf-198">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=fullName> namespace or the <xref:System.Collections.Concurrent> namespace instead of the Visual Basic `Collection` class.</span></span>  
  
 <span data-ttu-id="4a4cf-199">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Collection>.</xref:Microsoft.VisualBasic.Collection></span><span class="sxs-lookup"><span data-stu-id="4a4cf-199">For more information, see <xref:Microsoft.VisualBasic.Collection>.</span></span>  
  
<a name="BKMK_KeyValuePairs"></a>
## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="4a4cf-200">Реализация коллекции пар «ключ-значение»</span><span class="sxs-lookup"><span data-stu-id="4a4cf-200">Implementing a Collection of Key/Value Pairs</span></span>   
 <span data-ttu-id="4a4cf-201"><xref:System.Collections.Generic.Dictionary%602>Обеспечивает доступ к элементам в коллекции с помощью ключа каждого элемента универсальной коллекции.</xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="4a4cf-201">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="4a4cf-202">Каждый элемент, добавляемый в словарь, состоит из значения и связанного с ним ключа.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-202">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="4a4cf-203">Получение значения, используя свой ключ — быстро, так как `Dictionary` класс реализован в виде хэш-таблицы.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-203">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>  
  
 <span data-ttu-id="4a4cf-204">В следующем примере создается `Dictionary` коллекции и перебор элементов словаря с помощью `For Each` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-204">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `For Each` statement.</span></span>  
  
```vb  
Private Sub IterateThroughDictionary()  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    For Each kvp As KeyValuePair(Of String, Element) In elements  
        Dim theElement As Element = kvp.Value  
  
        Console.WriteLine("key: " & kvp.Key)  
        With theElement  
            Console.WriteLine("values: " & .Symbol & " " &  
                .Name & " " & .AtomicNumber)  
        End With  
    Next  
End Sub  
  
Private Function BuildDictionary() As Dictionary(Of String, Element)  
    Dim elements As New Dictionary(Of String, Element)  
  
    AddToDictionary(elements, "K", "Potassium", 19)  
    AddToDictionary(elements, "Ca", "Calcium", 20)  
    AddToDictionary(elements, "Sc", "Scandium", 21)  
    AddToDictionary(elements, "Ti", "Titanium", 22)  
  
    Return elements  
End Function  
  
Private Sub AddToDictionary(ByVal elements As Dictionary(Of String, Element),  
ByVal symbol As String, ByVal name As String, ByVal atomicNumber As Integer)  
    Dim theElement As New Element  
  
    theElement.Symbol = symbol  
    theElement.Name = name  
    theElement.AtomicNumber = atomicNumber  
  
    elements.Add(Key:=theElement.Symbol, value:=theElement)  
End Sub  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 <span data-ttu-id="4a4cf-205">Вместо этого использовать инициализатор коллекции для создания `Dictionary` коллекции, можно заменить `BuildDictionary` и `AddToDictionary` методов, с помощью следующего метода.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-205">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>  
  
```vb  
Private Function BuildDictionary2() As Dictionary(Of String, Element)  
    Return New Dictionary(Of String, Element) From  
        {  
            {"K", New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {"Ca", New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {"Sc", New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {"Ti", New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
```  
  
 <span data-ttu-id="4a4cf-206">В следующем примере используется <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A>метод и <xref:System.Collections.Generic.Dictionary%602.Item%2A>Свойства `Dictionary` быстро найти элемент с ключом.</xref:System.Collections.Generic.Dictionary%602.Item%2A> </xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A></span><span class="sxs-lookup"><span data-stu-id="4a4cf-206">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="4a4cf-207">`Item` Позволяет доступ к элементу в `elements` коллекции с помощью `elements(symbol)` кода в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-207">The `Item` property enables you to access an item in the `elements` collection by using the `elements(symbol)` code in Visual Basic.</span></span>  
  
```vb  
Private Sub FindInDictionary(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    If elements.ContainsKey(symbol) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Dim theElement = elements(symbol)  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
 <span data-ttu-id="4a4cf-208">В следующем примере используется вместо <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>метод быстро найти элемент с ключом.</xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A></span><span class="sxs-lookup"><span data-stu-id="4a4cf-208">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>  
  
```vb  
Private Sub FindInDictionary2(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    Dim theElement As Element = Nothing  
    If elements.TryGetValue(symbol, theElement) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
<a name="BKMK_LINQ"></a> 
##  <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="4a4cf-209">Использование LINQ для доступа к коллекции</span><span class="sxs-lookup"><span data-stu-id="4a4cf-209">Using LINQ to Access a Collection</span></span>  
 <span data-ttu-id="4a4cf-210">Для доступа к коллекции можно использовать язык LINQ.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-210">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="4a4cf-211">Запросы LINQ обеспечивают возможности фильтрации, упорядочения и группировки.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-211">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="4a4cf-212">Дополнительные сведения см. в разделе [Приступая к работе с LINQ в Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="4a4cf-212">For more information, see [Getting Started with LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="4a4cf-213">В следующем примере выполняется запрос LINQ к универсальным `List`.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-213">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="4a4cf-214">Запрос LINQ возвращает другую коллекцию, содержащую результаты.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-214">The LINQ query returns a different collection that contains the results.</span></span>  
  
```vb  
Private Sub ShowLINQ()  
    Dim elements As List(Of Element) = BuildList()  
  
    ' LINQ Query.  
    Dim subset = From theElement In elements  
                  Where theElement.AtomicNumber < 22  
                  Order By theElement.Name  
  
    For Each theElement In subset  
        Console.WriteLine(theElement.Name & " " & theElement.AtomicNumber)  
    Next  
  
    ' Output:  
    '  Calcium 20  
    '  Potassium 19  
    '  Scandium 21  
End Sub  
  
Private Function BuildList() As List(Of Element)  
    Return New List(Of Element) From  
        {  
            {New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 <a name="BKMK_Sorting"></a> 
## <a name="sorting-a-collection"></a><span data-ttu-id="4a4cf-215">Сортировка коллекции</span><span class="sxs-lookup"><span data-stu-id="4a4cf-215">Sorting a Collection</span></span>  
 <span data-ttu-id="4a4cf-216">Приведенный ниже пример демонстрирует процедуру сортировки коллекции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-216">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="4a4cf-217">В примере выполняется сортировка экземпляров `Car` класса, которые хранятся в папке <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-217">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="4a4cf-218">`Car` Реализует <xref:System.IComparable%601>интерфейс, который требует <xref:System.IComparable%601.CompareTo%2A>метод будет реализован.</xref:System.IComparable%601.CompareTo%2A> </xref:System.IComparable%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-218">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="4a4cf-219">Каждый вызов <xref:System.IComparable%601.CompareTo%2A>метод делает одну сравнения, используемый для сортировки.</xref:System.IComparable%601.CompareTo%2A></span><span class="sxs-lookup"><span data-stu-id="4a4cf-219">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="4a4cf-220">Пользовательский код в `CompareTo` метод возвращает значение для каждого сравнения текущего объекта с другим объектом.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-220">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="4a4cf-221">Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-221">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="4a4cf-222">Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».</span><span class="sxs-lookup"><span data-stu-id="4a4cf-222">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>  
  
 <span data-ttu-id="4a4cf-223">В `ListCars` метода `cars.Sort()` инструкция сортирует список.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-223">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="4a4cf-224">Этот вызов <xref:System.Collections.Generic.List%601.Sort%2A>метод <xref:System.Collections.Generic.List%601>вызывает `CompareTo` метод, который вызывается автоматически для `Car` объектов в `List`.</xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.List%601.Sort%2A></span><span class="sxs-lookup"><span data-stu-id="4a4cf-224">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>  
  
```vb  
Public Sub ListCars()  
  
    ' Create some new cars.  
    Dim cars As New List(Of Car) From  
    {  
        New Car With {.Name = "car1", .Color = "blue", .Speed = 20},  
        New Car With {.Name = "car2", .Color = "red", .Speed = 50},  
        New Car With {.Name = "car3", .Color = "green", .Speed = 10},  
        New Car With {.Name = "car4", .Color = "blue", .Speed = 50},  
        New Car With {.Name = "car5", .Color = "blue", .Speed = 30},  
        New Car With {.Name = "car6", .Color = "red", .Speed = 60},  
        New Car With {.Name = "car7", .Color = "green", .Speed = 50}  
    }  
  
    ' Sort the cars by color alphabetically, and then by speed  
    ' in descending order.  
    cars.Sort()  
  
    ' View all of the cars.  
    For Each thisCar As Car In cars  
        Console.Write(thisCar.Color.PadRight(5) & " ")  
        Console.Write(thisCar.Speed.ToString & " ")  
        Console.Write(thisCar.Name)  
        Console.WriteLine()  
    Next  
  
    ' Output:  
    '  blue  50 car4  
    '  blue  30 car5  
    '  blue  20 car1  
    '  green 50 car7  
    '  green 10 car3  
    '  red   60 car6  
    '  red   50 car2  
End Sub  
  
Public Class Car  
    Implements IComparable(Of Car)  
  
    Public Property Name As String  
    Public Property Speed As Integer  
    Public Property Color As String  
  
    Public Function CompareTo(ByVal other As Car) As Integer _  
        Implements System.IComparable(Of Car).CompareTo  
        ' A call to this method makes a single comparison that is  
        ' used for sorting.  
  
        ' Determine the relative order of the objects being compared.  
        ' Sort by color alphabetically, and then by speed in  
        ' descending order.  
  
        ' Compare the colors.  
        Dim compare As Integer  
        compare = String.Compare(Me.Color, other.Color, True)  
  
        ' If the colors are the same, compare the speeds.  
        If compare = 0 Then  
            compare = Me.Speed.CompareTo(other.Speed)  
  
            ' Use descending order for speed.  
            compare = -compare  
        End If  
  
        Return compare  
    End Function  
End Class  
```  
  
<a name="BKMK_CustomCollection"></a> 
## <a name="defining-a-custom-collection"></a><span data-ttu-id="4a4cf-225">Определение настраиваемой коллекции</span><span class="sxs-lookup"><span data-stu-id="4a4cf-225">Defining a Custom Collection</span></span>  
 <span data-ttu-id="4a4cf-226">Можно определить коллекцию путем реализации <xref:System.Collections.Generic.IEnumerable%601>или <xref:System.Collections.IEnumerable>интерфейса.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="4a4cf-226">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="4a4cf-227">Дополнительные сведения см. в разделе [перечисление коллекции](http://msdn.microsoft.com/en-us/71807ea7-9180-48a6-916f-35a5251d477f).</span><span class="sxs-lookup"><span data-stu-id="4a4cf-227">For additional information, see [Enumerating a Collection](http://msdn.microsoft.com/en-us/71807ea7-9180-48a6-916f-35a5251d477f).</span></span>  
  
 <span data-ttu-id="4a4cf-228">Несмотря на то, что можно определить пользовательскую коллекцию, обычно лучше вместо этого использовать коллекций, включенных в .NET Framework, которые описаны в [типов коллекций](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-228">Although you can define a custom collection, it is usually better to instead use the collections that are included in the .NET Framework, which are described in [Kinds of Collections](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) earlier in this topic.</span></span>  
  
 <span data-ttu-id="4a4cf-229">В следующем примере определяется пользовательский класс коллекции с именем `AllColors`.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-229">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="4a4cf-230">Этот класс реализует <xref:System.Collections.IEnumerable>интерфейс, который требует <xref:System.Collections.IEnumerable.GetEnumerator%2A>метод будет реализован.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="4a4cf-230">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>  
  
 <span data-ttu-id="4a4cf-231">`GetEnumerator` Метод возвращает экземпляр `ColorEnumerator` класса.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-231">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="4a4cf-232">`ColorEnumerator`реализует <xref:System.Collections.IEnumerator>интерфейс, который требует <xref:System.Collections.IEnumerator.Current%2A>свойство, <xref:System.Collections.IEnumerator.MoveNext%2A>метод, и <xref:System.Collections.IEnumerator.Reset%2A>метод будет реализован.</xref:System.Collections.IEnumerator.Reset%2A> </xref:System.Collections.IEnumerator.MoveNext%2A> </xref:System.Collections.IEnumerator.Current%2A> </xref:System.Collections.IEnumerator></span><span class="sxs-lookup"><span data-stu-id="4a4cf-232">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>  
  
```vb  
Public Sub ListColors()  
    Dim colors As New AllColors()  
  
    For Each theColor As Color In colors  
        Console.Write(theColor.Name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: red blue green  
End Sub  
  
' Collection class.  
Public Class AllColors  
    Implements System.Collections.IEnumerable  
  
    Private _colors() As Color =  
    {  
        New Color With {.Name = "red"},  
        New Color With {.Name = "blue"},  
        New Color With {.Name = "green"}  
    }  
  
    Public Function GetEnumerator() As System.Collections.IEnumerator _  
        Implements System.Collections.IEnumerable.GetEnumerator  
  
        Return New ColorEnumerator(_colors)  
  
        ' Instead of creating a custom enumerator, you could  
        ' use the GetEnumerator of the array.  
        'Return _colors.GetEnumerator  
    End Function  
  
    ' Custom enumerator.  
    Private Class ColorEnumerator  
        Implements System.Collections.IEnumerator  
  
        Private _colors() As Color  
        Private _position As Integer = -1  
  
        Public Sub New(ByVal colors() As Color)  
            _colors = colors  
        End Sub  
  
        Public ReadOnly Property Current() As Object _  
            Implements System.Collections.IEnumerator.Current  
            Get  
                Return _colors(_position)  
            End Get  
        End Property  
  
        Public Function MoveNext() As Boolean _  
            Implements System.Collections.IEnumerator.MoveNext  
            _position += 1  
            Return (_position < _colors.Length)  
        End Function  
  
        Public Sub Reset() Implements System.Collections.IEnumerator.Reset  
            _position = -1  
        End Sub  
    End Class  
End Class  
  
' Element class.  
Public Class Color  
    Public Property Name As String  
End Class  
```  
  
<a name="BKMK_Iterators"></a>
##  <a name="iterators"></a><span data-ttu-id="4a4cf-233">Итераторы</span><span class="sxs-lookup"><span data-stu-id="4a4cf-233">Iterators</span></span>  
 <span data-ttu-id="4a4cf-234">*Итератор* используется для выполнения пользовательских итерации по коллекции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-234">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="4a4cf-235">Метод может быть итератора или `get` доступа.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-235">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="4a4cf-236">Использует итератор [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) инструкции для возврата каждого элемента коллекции одной за раз.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-236">An iterator uses a [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element of the collection one at a time.</span></span>  
  
 <span data-ttu-id="4a4cf-237">Итератор вызывается с помощью [For Each... Далее](../../../visual-basic/language-reference/statements/for-each-next-statement.md) инструкции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-237">You call an iterator by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span> <span data-ttu-id="4a4cf-238">Каждая итерация `For Each` цикл вызывает итератор.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-238">Each iteration of the `For Each` loop calls the iterator.</span></span> <span data-ttu-id="4a4cf-239">Когда `Yield` достижении оператора в итераторе, выражения возвращается и сохраняется текущее расположение в коде.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-239">When a `Yield` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="4a4cf-240">При следующем вызове итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-240">Execution is restarted from that location the next time that the iterator is called.</span></span>  
  
 <span data-ttu-id="4a4cf-241">Дополнительные сведения см. в разделе [итераторы (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).</span><span class="sxs-lookup"><span data-stu-id="4a4cf-241">For more information, see [Iterators (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).</span></span>  
  
 <span data-ttu-id="4a4cf-242">В приведенном ниже примере используется метод-итератор.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-242">The following example uses an iterator method.</span></span> <span data-ttu-id="4a4cf-243">Метод итератора имеет `Yield` оператор, находящийся внутри [для... Далее](../../../visual-basic/language-reference/statements/for-next-statement.md) цикла.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-243">The iterator method has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="4a4cf-244">В `ListEvenNumbers` метод, каждая итерация `For Each` тела оператора создает вызов метода итератора, который переходит к следующему `Yield` инструкции.</span><span class="sxs-lookup"><span data-stu-id="4a4cf-244">In the `ListEvenNumbers` method, each iteration of the `For Each` statement body creates a call to the iterator method, which proceeds to the next `Yield` statement.</span></span>  
  
```vb  
Public Sub ListEvenNumbers()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    Console.WriteLine()  
    ' Output: 6 8 10 12 14 16 18  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As IEnumerable(Of Integer)  
  
' Yield even numbers in the range.  
    For number = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a4cf-245">См. также</span><span class="sxs-lookup"><span data-stu-id="4a4cf-245">See Also</span></span>  
 <span data-ttu-id="4a4cf-246">[Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a4cf-246">[Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md) </span></span>  
<span data-ttu-id="4a4cf-247"> [Основные понятия программирования (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a4cf-247"> [Programming Concepts (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="4a4cf-248"> [Оператор Option Strict](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4a4cf-248"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="4a4cf-249"> [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span><span class="sxs-lookup"><span data-stu-id="4a4cf-249"> [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md) </span></span>  
<span data-ttu-id="4a4cf-250"> [Параллельный LINQ (PLINQ)](http://msdn.microsoft.com/library/3d4d0cd3-bde4-490b-99e7-f4e41be96455) </span><span class="sxs-lookup"><span data-stu-id="4a4cf-250"> [Parallel LINQ (PLINQ)](http://msdn.microsoft.com/library/3d4d0cd3-bde4-490b-99e7-f4e41be96455) </span></span>  
<span data-ttu-id="4a4cf-251"> [Коллекции и структуры данных](../../../standard/collections/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a4cf-251"> [Collections and Data Structures](../../../standard/collections/index.md) </span></span>  
<span data-ttu-id="4a4cf-252"> [Создание коллекций и управление ими](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069) </span><span class="sxs-lookup"><span data-stu-id="4a4cf-252"> [Creating and Manipulating Collections](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069) </span></span>  
<span data-ttu-id="4a4cf-253"> [Выбор класса коллекции](../../../standard/collections/selecting-a-collection-class.md) </span><span class="sxs-lookup"><span data-stu-id="4a4cf-253"> [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md) </span></span>  
<span data-ttu-id="4a4cf-254"> [Сравнение и сортировка в коллекциях](../../../standard/collections/comparisons-and-sorts-within-collections.md) </span><span class="sxs-lookup"><span data-stu-id="4a4cf-254"> [Comparisons and Sorts Within Collections](../../../standard/collections/comparisons-and-sorts-within-collections.md) </span></span>  
<span data-ttu-id="4a4cf-255"> [Когда следует использовать универсальные коллекции](../../../standard/collections/when-to-use-generic-collections.md)</span><span class="sxs-lookup"><span data-stu-id="4a4cf-255"> [When to Use Generic Collections](../../../standard/collections/when-to-use-generic-collections.md)</span></span>
