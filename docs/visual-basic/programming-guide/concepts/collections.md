---
title: Коллекции
ms.date: 07/20/2015
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
ms.openlocfilehash: ba16d04e781bcf69356b1f603d92e104816a0860
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401415"
---
# <a name="collections-visual-basic"></a><span data-ttu-id="b800d-102">Коллекции (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b800d-102">Collections (Visual Basic)</span></span>

<span data-ttu-id="b800d-103">Во многих приложениях требуется создавать группы связанных объектов и управлять ими.</span><span class="sxs-lookup"><span data-stu-id="b800d-103">For many applications, you want to create and manage groups of related objects.</span></span> <span data-ttu-id="b800d-104">Существует два способа группировки объектов: создать массив объектов и создать коллекцию.</span><span class="sxs-lookup"><span data-stu-id="b800d-104">There are two ways to group objects: by creating arrays of objects, and by creating collections of objects.</span></span>

<span data-ttu-id="b800d-105">Массивы удобнее всего использовать для создания и работы с фиксированным числом строго типизированных объектов.</span><span class="sxs-lookup"><span data-stu-id="b800d-105">Arrays are most useful for creating and working with a fixed number of strongly-typed objects.</span></span> <span data-ttu-id="b800d-106">Информацию о массивах см. в разделе [Массивы](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="b800d-106">For information about arrays, see [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>

<span data-ttu-id="b800d-107">Коллекции предоставляют более гибкий способ работы с группами объектов.</span><span class="sxs-lookup"><span data-stu-id="b800d-107">Collections provide a more flexible way to work with groups of objects.</span></span> <span data-ttu-id="b800d-108">В отличие от массивов, коллекция, с которой вы работаете, может расти или уменьшаться динамически при необходимости.</span><span class="sxs-lookup"><span data-stu-id="b800d-108">Unlike arrays, the group of objects you work with can grow and shrink dynamically as the needs of the application change.</span></span> <span data-ttu-id="b800d-109">Некоторые коллекции допускают назначение ключа любому объекту, который добавляется в коллекцию, чтобы в дальнейшем можно было быстро извлечь связанный с ключом объект из коллекции.</span><span class="sxs-lookup"><span data-stu-id="b800d-109">For some collections, you can assign a key to any object that you put into the collection so that you can quickly retrieve the object by using the key.</span></span>

<span data-ttu-id="b800d-110">Коллекция является классом, поэтому необходимо объявить экземпляр класса перед добавлением в коллекцию элементов.</span><span class="sxs-lookup"><span data-stu-id="b800d-110">A collection is a class, so you must declare an instance of the class before you can add elements to that collection.</span></span>

<span data-ttu-id="b800d-111">Если коллекция содержит элементы только одного типа данных, можно использовать один из классов в пространстве имен <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b800d-111">If your collection contains elements of only one data type, you can use one of the classes in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="b800d-112">Универсальная коллекция обеспечивает строгую типизацию, так что в нее нельзя добавить другие типы данных.</span><span class="sxs-lookup"><span data-stu-id="b800d-112">A generic collection enforces type safety so that no other data type can be added to it.</span></span> <span data-ttu-id="b800d-113">При извлечении элемента из универсальной коллекции не нужно определять или преобразовывать его тип данных.</span><span class="sxs-lookup"><span data-stu-id="b800d-113">When you retrieve an element from a generic collection, you do not have to determine its data type or convert it.</span></span>

> [!NOTE]
> <span data-ttu-id="b800d-114">Для примеров в этой теме `System.Collections.Generic` включите заявления [об импорте](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) для областей имен. `System.Linq`</span><span class="sxs-lookup"><span data-stu-id="b800d-114">For the examples in this topic, include [Imports](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) statements for the `System.Collections.Generic` and `System.Linq` namespaces.</span></span>

<a name="BKMK_SimpleCollection"></a>

## <a name="using-a-simple-collection"></a><span data-ttu-id="b800d-115">Использование простой коллекции</span><span class="sxs-lookup"><span data-stu-id="b800d-115">Using a Simple Collection</span></span>

<span data-ttu-id="b800d-116">В примерах этого раздела используется универсальный класс <xref:System.Collections.Generic.List%601>, который позволяет работать со строго типизированными списками объектов.</span><span class="sxs-lookup"><span data-stu-id="b800d-116">The examples in this section use the generic <xref:System.Collections.Generic.List%601> class, which enables you to work with a strongly typed list of objects.</span></span>

<span data-ttu-id="b800d-117">Следующий пример создает список строк, а затем итерирует через строки с помощью [для каждого ... Следующее](../../../visual-basic/language-reference/statements/for-each-next-statement.md) заявление.</span><span class="sxs-lookup"><span data-stu-id="b800d-117">The following example creates a list of strings and then iterates through the strings by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span>

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

<span data-ttu-id="b800d-118">Если содержимое коллекции известно заранее, для ее инициализации можно использовать *инициализатор коллекции*.</span><span class="sxs-lookup"><span data-stu-id="b800d-118">If the contents of a collection are known in advance, you can use a *collection initializer* to initialize the collection.</span></span> <span data-ttu-id="b800d-119">Дополнительные сведения см. в разделе [Инициализаторы коллекций](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span><span class="sxs-lookup"><span data-stu-id="b800d-119">For more information, see [Collection Initializers](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).</span></span>

<span data-ttu-id="b800d-120">Следующий пример аналогичен предыдущему за исключением того, что для добавления элементов в коллекцию используется инициализатор коллекции.</span><span class="sxs-lookup"><span data-stu-id="b800d-120">The following example is the same as the previous example, except a collection initializer is used to add elements to the collection.</span></span>

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

<span data-ttu-id="b800d-121">Вы можете использовать [for... Следующее](../../../visual-basic/language-reference/statements/for-next-statement.md) заявление `For Each` вместо оператора для итерата через коллекцию.</span><span class="sxs-lookup"><span data-stu-id="b800d-121">You can use a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement instead of a `For Each` statement to iterate through a collection.</span></span> <span data-ttu-id="b800d-122">Для этого доступ к элементам коллекции осуществляется по позиции индекса.</span><span class="sxs-lookup"><span data-stu-id="b800d-122">You accomplish this by accessing the collection elements by the index position.</span></span> <span data-ttu-id="b800d-123">Индекс элементов начинается с 0 и заканчивается числом, равным количеству элементов минус 1.</span><span class="sxs-lookup"><span data-stu-id="b800d-123">The index of the elements starts at 0 and ends at the element count minus 1.</span></span>

<span data-ttu-id="b800d-124">В приведенном ниже примере выполняется перебор элементов коллекции с помощью оператора `For…Next` вместо `For Each`.</span><span class="sxs-lookup"><span data-stu-id="b800d-124">The following example iterates through the elements of a collection by using `For…Next` instead of `For Each`.</span></span>

```vb
Dim salmons As New List(Of String) From
    {"chinook", "coho", "pink", "sockeye"}

For index = 0 To salmons.Count - 1
    Console.Write(salmons(index) & " ")
Next
'Output: chinook coho pink sockeye
```

<span data-ttu-id="b800d-125">В приведенном ниже примере элемент удаляется из коллекции путем указания удаляемого объекта.</span><span class="sxs-lookup"><span data-stu-id="b800d-125">The following example removes an element from the collection by specifying the object to remove.</span></span>

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

<span data-ttu-id="b800d-126">В приведенном ниже примере удаляются элементы из универсального списка.</span><span class="sxs-lookup"><span data-stu-id="b800d-126">The following example removes elements from a generic list.</span></span> <span data-ttu-id="b800d-127">Вместо `For Each` заявления, [для ... Используется следующее](../../../visual-basic/language-reference/statements/for-next-statement.md) утверждение, итерирующее в порядке убывания.</span><span class="sxs-lookup"><span data-stu-id="b800d-127">Instead of a `For Each` statement, a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) statement that iterates in descending order is used.</span></span> <span data-ttu-id="b800d-128">Связано это с тем, что в результате работы метода <xref:System.Collections.Generic.List%601.RemoveAt%2A> элементы, следующие за удаленным элементом, получают меньшее значение индекса.</span><span class="sxs-lookup"><span data-stu-id="b800d-128">This is because the <xref:System.Collections.Generic.List%601.RemoveAt%2A> method causes elements after a removed element to have a lower index value.</span></span>

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

<span data-ttu-id="b800d-129">Для типа элементов в <xref:System.Collections.Generic.List%601> можно также определить собственный класс.</span><span class="sxs-lookup"><span data-stu-id="b800d-129">For the type of elements in the <xref:System.Collections.Generic.List%601>, you can also define your own class.</span></span> <span data-ttu-id="b800d-130">В приведенном ниже примере класс `Galaxy`, который используется объектом <xref:System.Collections.Generic.List%601>, определен в коде.</span><span class="sxs-lookup"><span data-stu-id="b800d-130">In the following example, the `Galaxy` class that is used by the <xref:System.Collections.Generic.List%601> is defined in the code.</span></span>

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

## <a name="kinds-of-collections"></a><span data-ttu-id="b800d-131">Виды коллекций</span><span class="sxs-lookup"><span data-stu-id="b800d-131">Kinds of Collections</span></span>

<span data-ttu-id="b800d-132">Многие типовые коллекции предоставляются платформой .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b800d-132">Many common collections are provided by the .NET Framework.</span></span> <span data-ttu-id="b800d-133">Каждый тип коллекции предназначен для определенной цели.</span><span class="sxs-lookup"><span data-stu-id="b800d-133">Each type of collection is designed for a specific purpose.</span></span>

<span data-ttu-id="b800d-134">В этом разделе описываются следующие часто используемые классы коллекций:</span><span class="sxs-lookup"><span data-stu-id="b800d-134">Some of the common collection classes are described in this section:</span></span>

- <span data-ttu-id="b800d-135">Классы <xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="b800d-135"><xref:System.Collections.Generic> classes</span></span>

- <span data-ttu-id="b800d-136">Классы <xref:System.Collections.Concurrent></span><span class="sxs-lookup"><span data-stu-id="b800d-136"><xref:System.Collections.Concurrent> classes</span></span>

- <span data-ttu-id="b800d-137">Классы <xref:System.Collections></span><span class="sxs-lookup"><span data-stu-id="b800d-137"><xref:System.Collections> classes</span></span>

- <span data-ttu-id="b800d-138">класс `Collection` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b800d-138">Visual Basic `Collection` class</span></span>

<a name="BKMK_Generic"></a>

### <a name="systemcollectionsgeneric-classes"></a><span data-ttu-id="b800d-139">Классы System.Collections.Generic</span><span class="sxs-lookup"><span data-stu-id="b800d-139">System.Collections.Generic Classes</span></span>

<span data-ttu-id="b800d-140">Универсальную коллекцию можно создать, используя один из классов в пространстве имен <xref:System.Collections.Generic>.</span><span class="sxs-lookup"><span data-stu-id="b800d-140">You can create a generic collection by using one of the classes in the <xref:System.Collections.Generic> namespace.</span></span> <span data-ttu-id="b800d-141">Универсальная коллекция применяется в том случае, если все элементы в коллекции имеют одинаковый тип данных.</span><span class="sxs-lookup"><span data-stu-id="b800d-141">A generic collection is useful when every item in the collection has the same data type.</span></span> <span data-ttu-id="b800d-142">Универсальная коллекция обеспечивает строгую типизацию, позволяя добавлять данные только необходимого типа.</span><span class="sxs-lookup"><span data-stu-id="b800d-142">A generic collection enforces strong typing by allowing only the desired data type to be added.</span></span>

<span data-ttu-id="b800d-143">В таблице ниже перечислены некоторые из часто используемых классов пространства имен <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b800d-143">The following table lists some of the frequently used classes of the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace:</span></span>

|<span data-ttu-id="b800d-144">Class</span><span class="sxs-lookup"><span data-stu-id="b800d-144">Class</span></span>|<span data-ttu-id="b800d-145">Описание</span><span class="sxs-lookup"><span data-stu-id="b800d-145">Description</span></span>|
|---|---|
|<xref:System.Collections.Generic.Dictionary%602>|<span data-ttu-id="b800d-146">Предоставляет коллекцию пар «ключ-значение», которые упорядочены по ключу.</span><span class="sxs-lookup"><span data-stu-id="b800d-146">Represents a collection of key/value pairs that are organized based on the key.</span></span>|
|<xref:System.Collections.Generic.List%601>|<span data-ttu-id="b800d-147">Представляет список объектов, доступных по индексу.</span><span class="sxs-lookup"><span data-stu-id="b800d-147">Represents a list of objects that can be accessed by index.</span></span> <span data-ttu-id="b800d-148">Предоставляет методы для поиска по списку, его сортировки и изменения.</span><span class="sxs-lookup"><span data-stu-id="b800d-148">Provides methods to search, sort, and modify lists.</span></span>|
|<xref:System.Collections.Generic.Queue%601>|<span data-ttu-id="b800d-149">Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).</span><span class="sxs-lookup"><span data-stu-id="b800d-149">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Generic.SortedList%602>|<span data-ttu-id="b800d-150">Представляет коллекцию пар "ключ-значение", упорядоченных по ключу на основе реализации <xref:System.Collections.Generic.IComparer%601>.</span><span class="sxs-lookup"><span data-stu-id="b800d-150">Represents a collection of key/value pairs that are sorted by key based on the associated <xref:System.Collections.Generic.IComparer%601> implementation.</span></span>|
|<xref:System.Collections.Generic.Stack%601>|<span data-ttu-id="b800d-151">Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).</span><span class="sxs-lookup"><span data-stu-id="b800d-151">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="b800d-152">Дополнительные сведения см. в разделе [Часто используемые типы коллекций](../../../standard/collections/commonly-used-collection-types.md), [Выбор класса коллекции](../../../standard/collections/selecting-a-collection-class.md) и <xref:System.Collections.Generic?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b800d-152">For additional information, see [Commonly Used Collection Types](../../../standard/collections/commonly-used-collection-types.md), [Selecting a Collection Class](../../../standard/collections/selecting-a-collection-class.md), and <xref:System.Collections.Generic?displayProperty=nameWithType>.</span></span>

<a name="BKMK_Concurrent"></a>

### <a name="systemcollectionsconcurrent-classes"></a><span data-ttu-id="b800d-153">Классы System.Collections.Concurrent</span><span class="sxs-lookup"><span data-stu-id="b800d-153">System.Collections.Concurrent Classes</span></span>

<span data-ttu-id="b800d-154">В .NET Framework 4 или более поздней версии коллекции пространства имен <xref:System.Collections.Concurrent> предоставляют эффективные потокобезопасные операции для доступа к элементам коллекции из нескольких потоков.</span><span class="sxs-lookup"><span data-stu-id="b800d-154">In the .NET Framework 4 or newer, the collections in the <xref:System.Collections.Concurrent> namespace provide efficient thread-safe operations for accessing collection items from multiple threads.</span></span>

<span data-ttu-id="b800d-155">Классы пространства имен <xref:System.Collections.Concurrent> следует использовать вместо соответствующих типов пространств имен <xref:System.Collections.Generic?displayProperty=nameWithType> и <xref:System.Collections?displayProperty=nameWithType>, если несколько потоков параллельно обращаются к такой коллекции.</span><span class="sxs-lookup"><span data-stu-id="b800d-155">The classes in the <xref:System.Collections.Concurrent> namespace should be used instead of the corresponding types in the <xref:System.Collections.Generic?displayProperty=nameWithType> and <xref:System.Collections?displayProperty=nameWithType> namespaces whenever multiple threads are accessing the collection concurrently.</span></span> <span data-ttu-id="b800d-156">Дополнительные сведения см. в статьях [Потокобезопасные коллекции](../../../standard/collections/thread-safe/index.md) и <xref:System.Collections.Concurrent>.</span><span class="sxs-lookup"><span data-stu-id="b800d-156">For more information, see [Thread-Safe Collections](../../../standard/collections/thread-safe/index.md) and <xref:System.Collections.Concurrent>.</span></span>

<span data-ttu-id="b800d-157">Некоторые из классов, входящих в пространство имен <xref:System.Collections.Concurrent>, — это <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601> и <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span><span class="sxs-lookup"><span data-stu-id="b800d-157">Some classes included in the <xref:System.Collections.Concurrent> namespace are <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, and <xref:System.Collections.Concurrent.ConcurrentStack%601>.</span></span>

<a name="BKMK_Collections"></a>

### <a name="systemcollections-classes"></a><span data-ttu-id="b800d-158">Классы System.Collections</span><span class="sxs-lookup"><span data-stu-id="b800d-158">System.Collections Classes</span></span>

<span data-ttu-id="b800d-159">Классы в пространстве имен <xref:System.Collections?displayProperty=nameWithType> хранят элементы не в виде конкретно типизированных объектов, а как объекты типа `Object`.</span><span class="sxs-lookup"><span data-stu-id="b800d-159">The classes in the <xref:System.Collections?displayProperty=nameWithType> namespace do not store elements as specifically typed objects, but as objects of type `Object`.</span></span>

<span data-ttu-id="b800d-160">Везде, где это возможно, следует использовать универсальные коллекции пространства имен <xref:System.Collections.Generic?displayProperty=nameWithType> или пространства имен <xref:System.Collections.Concurrent> вместо устаревших типов пространства имен `System.Collections`.</span><span class="sxs-lookup"><span data-stu-id="b800d-160">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace or the <xref:System.Collections.Concurrent> namespace instead of the legacy types in the `System.Collections` namespace.</span></span>

<span data-ttu-id="b800d-161">В следующей таблице перечислены некоторые из часто используемых классов пространства имен `System.Collections`:</span><span class="sxs-lookup"><span data-stu-id="b800d-161">The following table lists some of the frequently used classes in the `System.Collections` namespace:</span></span>

|<span data-ttu-id="b800d-162">Class</span><span class="sxs-lookup"><span data-stu-id="b800d-162">Class</span></span>|<span data-ttu-id="b800d-163">Описание</span><span class="sxs-lookup"><span data-stu-id="b800d-163">Description</span></span>|
|---|---|
|<xref:System.Collections.ArrayList>|<span data-ttu-id="b800d-164">Представляет массив объектов, размер которого динамически увеличивается по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b800d-164">Represents an array of objects whose size is dynamically increased as required.</span></span>|
|<xref:System.Collections.Hashtable>|<span data-ttu-id="b800d-165">Представляет коллекцию пар «ключ-значение», которые упорядочены по хэш-коду ключа.</span><span class="sxs-lookup"><span data-stu-id="b800d-165">Represents a collection of key/value pairs that are organized based on the hash code of the key.</span></span>|
|<xref:System.Collections.Queue>|<span data-ttu-id="b800d-166">Представляет коллекцию объектов, которая обслуживается в порядке поступления (FIFO).</span><span class="sxs-lookup"><span data-stu-id="b800d-166">Represents a first in, first out (FIFO) collection of objects.</span></span>|
|<xref:System.Collections.Stack>|<span data-ttu-id="b800d-167">Представляет коллекцию объектов, которая обслуживается в обратном порядке (LIFO).</span><span class="sxs-lookup"><span data-stu-id="b800d-167">Represents a last in, first out (LIFO) collection of objects.</span></span>|

<span data-ttu-id="b800d-168">Пространство имен <xref:System.Collections.Specialized> предоставляет специализированные и строго типизированные классы коллекций, такие как коллекции строк, связанные списки и гибридные словари.</span><span class="sxs-lookup"><span data-stu-id="b800d-168">The <xref:System.Collections.Specialized> namespace provides specialized and strongly typed collection classes, such as string-only collections and linked-list and hybrid dictionaries.</span></span>

<a name="BKMK_VisualBasic"></a>

### <a name="visual-basic-collection-class"></a><span data-ttu-id="b800d-169">Класс Collection в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b800d-169">Visual Basic Collection Class</span></span>

<span data-ttu-id="b800d-170">Класс <xref:Microsoft.VisualBasic.Collection> в Visual Basic можно использовать для доступа к элементу коллекции по числовому индексу или ключу `String`.</span><span class="sxs-lookup"><span data-stu-id="b800d-170">You can use the Visual Basic <xref:Microsoft.VisualBasic.Collection> class to access a collection item by using either a numeric index or a `String` key.</span></span> <span data-ttu-id="b800d-171">Элементы можно добавлять в объект коллекции с указанием или без указания ключа.</span><span class="sxs-lookup"><span data-stu-id="b800d-171">You can add items to a collection object either with or without specifying a key.</span></span> <span data-ttu-id="b800d-172">Если добавить объект без ключа, необходимо использовать его числовой индекс для доступа к нему.</span><span class="sxs-lookup"><span data-stu-id="b800d-172">If you add an item without a key, you must use its numeric index to access it.</span></span>

<span data-ttu-id="b800d-173">Класс `Collection` в Visual Basic хранит все свои элементы как тип `Object`, поэтому можно добавить элемент любого типа данных.</span><span class="sxs-lookup"><span data-stu-id="b800d-173">The Visual Basic `Collection` class stores all its elements as type `Object`, so you can add an item of any data type.</span></span> <span data-ttu-id="b800d-174">Нет никакой защиты от добавления неподходящих типов данных.</span><span class="sxs-lookup"><span data-stu-id="b800d-174">There is no safeguard against inappropriate data types being added.</span></span>

<span data-ttu-id="b800d-175">При использовании класса `Collection` в Visual Basic первый элемент в коллекции имеет индекс 1.</span><span class="sxs-lookup"><span data-stu-id="b800d-175">When you use the Visual Basic `Collection` class, the first item in a collection has an index of 1.</span></span> <span data-ttu-id="b800d-176">Этим он отличается от классов коллекций платформы .NET Framework, для которых начальный индекс равен 0.</span><span class="sxs-lookup"><span data-stu-id="b800d-176">This differs from the .NET Framework collection classes, for which the starting index is 0.</span></span>

<span data-ttu-id="b800d-177">Везде, где это возможно, следует использовать универсальные коллекции в пространстве имен <xref:System.Collections.Generic?displayProperty=nameWithType> или пространстве имен <xref:System.Collections.Concurrent> вместо класса `Collection` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b800d-177">Whenever possible, you should use the generic collections in the <xref:System.Collections.Generic?displayProperty=nameWithType> namespace or the <xref:System.Collections.Concurrent> namespace instead of the Visual Basic `Collection` class.</span></span>

<span data-ttu-id="b800d-178">Дополнительные сведения см. в разделе <xref:Microsoft.VisualBasic.Collection>.</span><span class="sxs-lookup"><span data-stu-id="b800d-178">For more information, see <xref:Microsoft.VisualBasic.Collection>.</span></span>

<a name="BKMK_KeyValuePairs"></a>

## <a name="implementing-a-collection-of-keyvalue-pairs"></a><span data-ttu-id="b800d-179">Реализация коллекции пар «ключ-значение»</span><span class="sxs-lookup"><span data-stu-id="b800d-179">Implementing a Collection of Key/Value Pairs</span></span>

<span data-ttu-id="b800d-180">Универсальная коллекция <xref:System.Collections.Generic.Dictionary%602> позволяет получить доступ к элементам коллекции с помощью ключа каждого элемента.</span><span class="sxs-lookup"><span data-stu-id="b800d-180">The <xref:System.Collections.Generic.Dictionary%602> generic collection enables you to access to elements in a collection by using the key of each element.</span></span> <span data-ttu-id="b800d-181">Каждый элемент, добавляемый в словарь, состоит из значения и связанного с ним ключа.</span><span class="sxs-lookup"><span data-stu-id="b800d-181">Each addition to the dictionary consists of a value and its associated key.</span></span> <span data-ttu-id="b800d-182">Извлечение значения по его ключу происходит быстро, так как класс `Dictionary` реализован как хэш-таблица.</span><span class="sxs-lookup"><span data-stu-id="b800d-182">Retrieving a value by using its key is fast because the `Dictionary` class is implemented as a hash table.</span></span>

<span data-ttu-id="b800d-183">В приведенном ниже примере создается коллекция `Dictionary` и выполняется перебор словаря с помощью оператора `For Each`.</span><span class="sxs-lookup"><span data-stu-id="b800d-183">The following example creates a `Dictionary` collection and iterates through the dictionary by using a `For Each` statement.</span></span>

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

<span data-ttu-id="b800d-184">Чтобы вместо этого использовать инициализатор коллекции для создания коллекции `Dictionary`, можно заменить методы `BuildDictionary` и `AddToDictionary` приведенным ниже методом.</span><span class="sxs-lookup"><span data-stu-id="b800d-184">To instead use a collection initializer to build the `Dictionary` collection, you can replace the `BuildDictionary` and `AddToDictionary` methods with the following method.</span></span>

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

<span data-ttu-id="b800d-185">В приведенном ниже примере используется метод <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> и свойство <xref:System.Collections.Generic.Dictionary%602.Item%2A>`Dictionary` для быстрого поиска элемента по ключу.</span><span class="sxs-lookup"><span data-stu-id="b800d-185">The following example uses the <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> method and the <xref:System.Collections.Generic.Dictionary%602.Item%2A> property of `Dictionary` to quickly find an item by key.</span></span> <span data-ttu-id="b800d-186">Свойство `Item` позволяет получить доступ к `elements` элементу `elements(symbol)` в коллекции, используя код в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b800d-186">The `Item` property enables you to access an item in the `elements` collection by using the `elements(symbol)` code in Visual Basic.</span></span>

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

<span data-ttu-id="b800d-187">В приведенном ниже примере вместо этого используется метод <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> для быстрого поиска элемента по ключу.</span><span class="sxs-lookup"><span data-stu-id="b800d-187">The following example instead uses the <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> method quickly find an item by key.</span></span>

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

## <a name="using-linq-to-access-a-collection"></a><span data-ttu-id="b800d-188">Использование LINQ для доступа к коллекции</span><span class="sxs-lookup"><span data-stu-id="b800d-188">Using LINQ to Access a Collection</span></span>

<span data-ttu-id="b800d-189">Для доступа к коллекции можно использовать язык LINQ.</span><span class="sxs-lookup"><span data-stu-id="b800d-189">LINQ (Language-Integrated Query) can be used to access collections.</span></span> <span data-ttu-id="b800d-190">Запросы LINQ обеспечивают возможности фильтрации, упорядочения и группировки.</span><span class="sxs-lookup"><span data-stu-id="b800d-190">LINQ queries provide filtering, ordering, and grouping capabilities.</span></span> <span data-ttu-id="b800d-191">Для получения дополнительной информации, [см. Начало работы с LIN's в Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="b800d-191">For more information, see [Getting Started with LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>

<span data-ttu-id="b800d-192">В приведенном ниже примере выполняется запрос LINQ применительно к универсальной коллекции `List`.</span><span class="sxs-lookup"><span data-stu-id="b800d-192">The following example runs a LINQ query against a generic `List`.</span></span> <span data-ttu-id="b800d-193">Запрос LINQ возвращает другую коллекцию, содержащую результаты.</span><span class="sxs-lookup"><span data-stu-id="b800d-193">The LINQ query returns a different collection that contains the results.</span></span>

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

## <a name="sorting-a-collection"></a><span data-ttu-id="b800d-194">Сортировка коллекции</span><span class="sxs-lookup"><span data-stu-id="b800d-194">Sorting a Collection</span></span>

<span data-ttu-id="b800d-195">Приведенный ниже пример демонстрирует процедуру сортировки коллекции.</span><span class="sxs-lookup"><span data-stu-id="b800d-195">The following example illustrates a procedure for sorting a collection.</span></span> <span data-ttu-id="b800d-196">В примере сортируются экземпляры класса `Car`, которые хранятся в <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="b800d-196">The example sorts instances of the `Car` class that are stored in a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="b800d-197">Класс `Car` реализует интерфейс <xref:System.IComparable%601>, который требует реализации метода <xref:System.IComparable%601.CompareTo%2A>.</span><span class="sxs-lookup"><span data-stu-id="b800d-197">The `Car` class implements the <xref:System.IComparable%601> interface, which requires that the <xref:System.IComparable%601.CompareTo%2A> method be implemented.</span></span>

<span data-ttu-id="b800d-198">Каждый вызов метода <xref:System.IComparable%601.CompareTo%2A> выполняет одно сравнение, используемое для сортировки.</span><span class="sxs-lookup"><span data-stu-id="b800d-198">Each call to the <xref:System.IComparable%601.CompareTo%2A> method makes a single comparison that is used for sorting.</span></span> <span data-ttu-id="b800d-199">Написанный пользователем код в методе `CompareTo` возвращает значение для каждого сравнения текущего объекта с другим объектом.</span><span class="sxs-lookup"><span data-stu-id="b800d-199">User-written code in the `CompareTo` method returns a value for each comparison of the current object with another object.</span></span> <span data-ttu-id="b800d-200">Возвращаемое значение меньше нуля, если текущий объект меньше другого объекта, больше нуля, если текущий объект больше другого объекта, и равняется нулю, если объекты равны.</span><span class="sxs-lookup"><span data-stu-id="b800d-200">The value returned is less than zero if the current object is less than the other object, greater than zero if the current object is greater than the other object, and zero if they are equal.</span></span> <span data-ttu-id="b800d-201">Это позволяет определить в коде условия для отношения «больше», «меньше» и «равно».</span><span class="sxs-lookup"><span data-stu-id="b800d-201">This enables you to define in code the criteria for greater than, less than, and equal.</span></span>

<span data-ttu-id="b800d-202">В методе `ListCars` оператор `cars.Sort()` сортирует список.</span><span class="sxs-lookup"><span data-stu-id="b800d-202">In the `ListCars` method, the `cars.Sort()` statement sorts the list.</span></span> <span data-ttu-id="b800d-203">Этот вызов метода <xref:System.Collections.Generic.List%601.Sort%2A><xref:System.Collections.Generic.List%601> приводит к тому, что метод `CompareTo` вызывается автоматически для объектов `Car` в `List`.</span><span class="sxs-lookup"><span data-stu-id="b800d-203">This call to the <xref:System.Collections.Generic.List%601.Sort%2A> method of the <xref:System.Collections.Generic.List%601> causes the `CompareTo` method to be called automatically for the `Car` objects in the `List`.</span></span>

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

## <a name="defining-a-custom-collection"></a><span data-ttu-id="b800d-204">Определение настраиваемой коллекции</span><span class="sxs-lookup"><span data-stu-id="b800d-204">Defining a Custom Collection</span></span>

<span data-ttu-id="b800d-205">Вы можете определить коллекцию, реализовав интерфейс <xref:System.Collections.Generic.IEnumerable%601> или <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="b800d-205">You can define a collection by implementing the <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="b800d-206">Для получения дополнительной информации [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hwyysy67(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b800d-206">For additional information, see [Enumerating a Collection](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/hwyysy67(v=vs.100)).</span></span>

<span data-ttu-id="b800d-207">Хотя можно определить настраиваемую коллекцию, обычно лучше использовать коллекции, входящие в .NET Framework, которые описаны в подразделе [Виды коллекций](#kinds-of-collections) ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b800d-207">Although you can define a custom collection, it is usually better to instead use the collections that are included in the .NET Framework, which are described in [Kinds of Collections](#kinds-of-collections) earlier in this topic.</span></span>

<span data-ttu-id="b800d-208">В приведенном ниже примере определяется настраиваемый класс коллекции с именем `AllColors`.</span><span class="sxs-lookup"><span data-stu-id="b800d-208">The following example defines a custom collection class named `AllColors`.</span></span> <span data-ttu-id="b800d-209">Этот класс реализует интерфейс <xref:System.Collections.IEnumerable>, который требует реализации метода <xref:System.Collections.IEnumerable.GetEnumerator%2A>.</span><span class="sxs-lookup"><span data-stu-id="b800d-209">This class implements the <xref:System.Collections.IEnumerable> interface, which requires that the <xref:System.Collections.IEnumerable.GetEnumerator%2A> method be implemented.</span></span>

<span data-ttu-id="b800d-210">Метод `GetEnumerator` возвращает экземпляр класса `ColorEnumerator`.</span><span class="sxs-lookup"><span data-stu-id="b800d-210">The `GetEnumerator` method returns an instance of the `ColorEnumerator` class.</span></span> <span data-ttu-id="b800d-211">Класс `ColorEnumerator` реализует интерфейс <xref:System.Collections.IEnumerator>, который требует реализации свойства <xref:System.Collections.IEnumerator.Current%2A>, метода <xref:System.Collections.IEnumerator.MoveNext%2A> и метода <xref:System.Collections.IEnumerator.Reset%2A>.</span><span class="sxs-lookup"><span data-stu-id="b800d-211">`ColorEnumerator` implements the <xref:System.Collections.IEnumerator> interface, which requires that the <xref:System.Collections.IEnumerator.Current%2A> property, <xref:System.Collections.IEnumerator.MoveNext%2A> method, and <xref:System.Collections.IEnumerator.Reset%2A> method be implemented.</span></span>

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

## <a name="iterators"></a><span data-ttu-id="b800d-212">Iterators</span><span class="sxs-lookup"><span data-stu-id="b800d-212">Iterators</span></span>

<span data-ttu-id="b800d-213">*Итератор* используется для выполнения настраиваемого перебора коллекции.</span><span class="sxs-lookup"><span data-stu-id="b800d-213">An *iterator* is used to perform a custom iteration over a collection.</span></span> <span data-ttu-id="b800d-214">Итератор может быть методом или методом доступа `get`.</span><span class="sxs-lookup"><span data-stu-id="b800d-214">An iterator can be a method or a `get` accessor.</span></span> <span data-ttu-id="b800d-215">Итератор использует выписку [о доходности,](../../../visual-basic/language-reference/statements/yield-statement.md) чтобы вернуть каждый элемент коллекции по одному.</span><span class="sxs-lookup"><span data-stu-id="b800d-215">An iterator uses a [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element of the collection one at a time.</span></span>

<span data-ttu-id="b800d-216">Вы называете итератор с помощью [для каждого ... Следующее](../../../visual-basic/language-reference/statements/for-each-next-statement.md) заявление.</span><span class="sxs-lookup"><span data-stu-id="b800d-216">You call an iterator by using a [For Each…Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement.</span></span> <span data-ttu-id="b800d-217">Каждая итерация цикла `For Each` вызывает итератор.</span><span class="sxs-lookup"><span data-stu-id="b800d-217">Each iteration of the `For Each` loop calls the iterator.</span></span> <span data-ttu-id="b800d-218">При достижении оператора `Yield` в итераторе возвращается выражение, и текущее расположение в коде сохраняется.</span><span class="sxs-lookup"><span data-stu-id="b800d-218">When a `Yield` statement is reached in the iterator, an expression is returned, and the current location in code is retained.</span></span> <span data-ttu-id="b800d-219">При следующем вызове итератора выполнение возобновляется с этого места.</span><span class="sxs-lookup"><span data-stu-id="b800d-219">Execution is restarted from that location the next time that the iterator is called.</span></span>

<span data-ttu-id="b800d-220">Для получения дополнительной информации [см.](../../../visual-basic/programming-guide/concepts/iterators.md)</span><span class="sxs-lookup"><span data-stu-id="b800d-220">For more information, see [Iterators (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).</span></span>

<span data-ttu-id="b800d-221">В приведенном ниже примере используется метод-итератор.</span><span class="sxs-lookup"><span data-stu-id="b800d-221">The following example uses an iterator method.</span></span> <span data-ttu-id="b800d-222">Метод итератора имеет `Yield` заявление, которое находится внутри [For... Следующий](../../../visual-basic/language-reference/statements/for-next-statement.md) цикл.</span><span class="sxs-lookup"><span data-stu-id="b800d-222">The iterator method has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop.</span></span> <span data-ttu-id="b800d-223">В методе `ListEvenNumbers` каждая итерация тела оператора `For Each` создает вызов метода-итератора, который переходит к следующему оператору `Yield`.</span><span class="sxs-lookup"><span data-stu-id="b800d-223">In the `ListEvenNumbers` method, each iteration of the `For Each` statement body creates a call to the iterator method, which proceeds to the next `Yield` statement.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="b800d-224">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b800d-224">See also</span></span>

- [<span data-ttu-id="b800d-225">Коллекция Инициалов</span><span class="sxs-lookup"><span data-stu-id="b800d-225">Collection Initializers</span></span>](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [<span data-ttu-id="b800d-226">Основные понятия программирования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b800d-226">Programming Concepts (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="b800d-227">Option Strict Statement</span><span class="sxs-lookup"><span data-stu-id="b800d-227">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="b800d-228">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b800d-228">LINQ to Objects (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="b800d-229">Parallel LINQ (PLINQ)</span><span class="sxs-lookup"><span data-stu-id="b800d-229">Parallel LINQ (PLINQ)</span></span>](../../../standard/parallel-programming/parallel-linq-plinq.md)
- [<span data-ttu-id="b800d-230">Коллекции и структуры данных</span><span class="sxs-lookup"><span data-stu-id="b800d-230">Collections and Data Structures</span></span>](../../../standard/collections/index.md)
- [<span data-ttu-id="b800d-231">Выбор класса коллекции</span><span class="sxs-lookup"><span data-stu-id="b800d-231">Selecting a Collection Class</span></span>](../../../standard/collections/selecting-a-collection-class.md)
- [<span data-ttu-id="b800d-232">Сравнение и сортировка в коллекциях</span><span class="sxs-lookup"><span data-stu-id="b800d-232">Comparisons and Sorts Within Collections</span></span>](../../../standard/collections/comparisons-and-sorts-within-collections.md)
- [<span data-ttu-id="b800d-233">Когда использовать общие коллекции</span><span class="sxs-lookup"><span data-stu-id="b800d-233">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)
