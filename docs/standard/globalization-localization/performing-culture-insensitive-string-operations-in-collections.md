---
title: "Выполнение в коллекциях строковых операций, не зависящих от языка и региональных параметров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CaseInsensitiveComparer class, using
- CollectionsUtil.CreateCaseInsensitiveHashtable method
- culture-insensitive string operations, collections
- collections [.NET Framework], culture-insensitive string operations
- CaseInsensitiveHashCodeProvider class, using
- ArrayList.Sort method
- SortedList class, culture-insensitive string operations
- culture parameter
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b84f25aa2470104be98b9f3858091c44f40ba6a7
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="performing-culture-insensitive-string-operations-in-collections"></a><span data-ttu-id="e7367-102">Выполнение в коллекциях строковых операций, не зависящих от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="e7367-102">Performing Culture-Insensitive String Operations in Collections</span></span>
<span data-ttu-id="e7367-103">В пространстве имен <xref:System.Collections> существуют классы и члены, поведение которых по умолчанию зависит от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="e7367-103">There are classes and members in the <xref:System.Collections> namespace that provide culture-sensitive behavior by default.</span></span> <span data-ttu-id="e7367-104">Конструкторы по умолчанию для классов <xref:System.Collections.CaseInsensitiveComparer> и <xref:System.Collections.CaseInsensitiveHashCodeProvider> инициализируют новый экземпляра с помощью свойства <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7367-104">The default constructors for the <xref:System.Collections.CaseInsensitiveComparer> and <xref:System.Collections.CaseInsensitiveHashCodeProvider> classes initialize a new instance using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="e7367-105">Все перегрузки метода <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> создают новый экземпляр класса <xref:System.Collections.Hashtable>, по умолчанию используя свойство `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-105">All overloads of the <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> method create a new instance of the <xref:System.Collections.Hashtable> class using the `Thread.CurrentCulture` property by default.</span></span> <span data-ttu-id="e7367-106">Перегруженные версии метода <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> по умолчанию выполняют сортировку с учетом языка и региональных параметров, используя свойства `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-106">Overloads of the <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> method perform culture-sensitive sorts by default using `Thread.CurrentCulture`.</span></span> <span data-ttu-id="e7367-107">Если в качестве ключей используются строки, на сортировку и поиск по <xref:System.Collections.SortedList> влияет значение `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-107">Sorting and lookup in a <xref:System.Collections.SortedList> can be affected by `Thread.CurrentCulture` when strings are used as the keys.</span></span> <span data-ttu-id="e7367-108">Для получения результатов, не зависящих от языка и региональных параметров, для этих классов и методов в пространстве имен `Collections` следуйте рекомендациям, приведенным в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e7367-108">Follow the usage recommendations provided in this section to obtain culture-insensitive results from these classes and methods in the `Collections` namespace.</span></span>  
  
 <span data-ttu-id="e7367-109">**Примечание**. Если передать в метод сравнения <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>, сравнение выполняется без учета языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="e7367-109">**Note** Passing <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="e7367-110">Однако при этом не выполняется нелингвистическое сравнение, например для путей к файлам, разделов реестра и переменных среды.</span><span class="sxs-lookup"><span data-stu-id="e7367-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="e7367-111">Также не поддерживается принятие решений по безопасности на основе результата сравнения.</span><span class="sxs-lookup"><span data-stu-id="e7367-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="e7367-112">Для нелингвистического сравнения и (или) поддержки принятия решений по безопасности в приложении следует использовать метод сравнения, который принимает значение <xref:System.StringComparison>.</span><span class="sxs-lookup"><span data-stu-id="e7367-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="e7367-113">Приложение должно передавать <xref:System.StringComparison>.</span><span class="sxs-lookup"><span data-stu-id="e7367-113">The application should then pass <xref:System.StringComparison>.</span></span>  
  
## <a name="using-the-caseinsensitivecomparer-and-caseinsensitivehashcodeprovider-classes"></a><span data-ttu-id="e7367-114">Использование классов CaseInsensitiveComparer и CaseInsensitiveHashCodeProvider</span><span class="sxs-lookup"><span data-stu-id="e7367-114">Using the CaseInsensitiveComparer and CaseInsensitiveHashCodeProvider Classes</span></span>  
 <span data-ttu-id="e7367-115">В конструкторах по умолчанию для `CaseInsensitiveHashCodeProvider` и `CaseInsensitiveComparer` инициализируется новый экземпляр класса с использованием `Thread.CurrentCulture`. Это приводит к тому, что язык и региональные параметры учитываются при сравнении.</span><span class="sxs-lookup"><span data-stu-id="e7367-115">The default constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer` initialize a new instance of the class using the `Thread.CurrentCulture`, resulting in culture-sensitive behavior.</span></span> <span data-ttu-id="e7367-116">В следующем примере кода показан конструктор для `Hashtable`, который учитывает язык и региональные параметры, так как он использует конструкторы по умолчанию для `CaseInsensitiveHashCodeProvider` и `CaseInsensitiveComparer`.</span><span class="sxs-lookup"><span data-stu-id="e7367-116">The following code example demonstrates the constructor for a `Hashtable` that is culture-sensitive because it uses the default constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer`.</span></span>  
  
```vb  
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)  
```  
  
```csharp  
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);  
```  
  
 <span data-ttu-id="e7367-117">Если вы хотите создать `Hashtable`, не учитывающий язык и региональные параметры, с помощью классов `CaseInsensitiveComparer` и `CaseInsensitiveHashCodeProvider`, инициализируйте новые экземпляры этих классов с помощью конструкторов, которые принимают параметр `culture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-117">If you want to create a culture-insensitive `Hashtable` using the `CaseInsensitiveComparer` and `CaseInsensitiveHashCodeProvider` classes, initialize new instances of these classes using the constructors that accept a `culture` parameter.</span></span> <span data-ttu-id="e7367-118">В качестве параметра `culture` укажите <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e7367-118">For the `culture` parameter, specify <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="e7367-119">В следующем примере кода показан конструктор для `Hashtable`, который не учитывает язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="e7367-119">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>  
  
```vb  
internalHashtable = New Hashtable(New  
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),  
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))  
```  
  
```csharp  
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider  
    (CultureInfo.InvariantCulture),   
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));  
```  
  
## <a name="using-the-collectionsutilcreatecaseinsensitivehashtable-method"></a><span data-ttu-id="e7367-120">Использование метода CollectionsUtil.CreateCaseInsensitiveHashTable</span><span class="sxs-lookup"><span data-stu-id="e7367-120">Using the CollectionsUtil.CreateCaseInsensitiveHashTable Method</span></span>  
 <span data-ttu-id="e7367-121">Для создания нового экземпляра класса `Hashtable`, который не учитывает регистр строк, удобно использовать метод `CollectionsUtil.CreateCaseInsensitiveHashTable`.</span><span class="sxs-lookup"><span data-stu-id="e7367-121">The `CollectionsUtil.CreateCaseInsensitiveHashTable` method is a useful shortcut for creating a new instance of the `Hashtable` class that ignores the case of strings.</span></span> <span data-ttu-id="e7367-122">Однако все перегруженные версии метода `CollectionsUtil.CreateCaseInsensitiveHashTable` учитывают язык и региональные параметры, так как они используют свойство `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-122">However, all overloads of the `CollectionsUtil.CreateCaseInsensitiveHashTable` method are culture-sensitive because they use the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="e7367-123">С помощью этого метода нельзя создать `Hashtable`, который не учитывает язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="e7367-123">You cannot create a culture-insensitive `Hashtable` using this method.</span></span> <span data-ttu-id="e7367-124">Чтобы создать `Hashtable`, который не учитывает язык и региональные параметры, используйте конструктор `Hashtable`, который принимает параметр `culture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-124">To create a culture-insensitive `Hashtable`, use the `Hashtable` constructor that accepts a `culture` parameter.</span></span> <span data-ttu-id="e7367-125">В качестве параметра `culture` укажите `CultureInfo.InvariantCulture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-125">For the `culture` parameter, specify `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="e7367-126">В следующем примере кода показан конструктор для `Hashtable`, который не учитывает язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="e7367-126">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>  
  
```vb  
internalHashtable = New Hashtable(New  
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),  
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))  
```  
  
```csharp  
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider  
    (CultureInfo.InvariantCulture),   
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));  
```  
  
<a name="cpconperformingculture-insensitivestringoperationsincollectionsanchor1"></a>   
## <a name="using-the-sortedlist-class"></a><span data-ttu-id="e7367-127">Использование класса SortedList</span><span class="sxs-lookup"><span data-stu-id="e7367-127">Using the SortedList Class</span></span>  
 <span data-ttu-id="e7367-128">`SortedList` представляет коллекцию пар "ключ — значение", упорядоченных по ключу. Обращаться к парам можно по ключу и индексу.</span><span class="sxs-lookup"><span data-stu-id="e7367-128">A `SortedList` represents a collection of key-and-value pairs that are sorted by the keys and are accessible by key and by index.</span></span> <span data-ttu-id="e7367-129">Если используется `SortedList` и в качестве ключей используются строки, на поиск и сортировку может повлиять свойство `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-129">When you use a `SortedList` where strings are the keys, the sorting and lookup can be affected by the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="e7367-130">Чтобы `SortedList` не учитывал язык и региональные параметры, создайте `SortedList` с помощью одного из конструкторов, принимающих параметр `comparer`.</span><span class="sxs-lookup"><span data-stu-id="e7367-130">To obtain culture-insensitive behavior from a `SortedList`, create a `SortedList` using one of the constructors that accepts a `comparer` parameter.</span></span> <span data-ttu-id="e7367-131">Параметр `comparer` указывает реализацию <xref:System.Collections.IComparer>, которую нужно использовать при сравнении ключей.</span><span class="sxs-lookup"><span data-stu-id="e7367-131">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing keys.</span></span> <span data-ttu-id="e7367-132">Для сравнения ключей в качестве параметра укажите пользовательский класс сравнения, который использует `CultureInfo.InvariantCulture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-132">For the parameter, specify a custom comparer class that uses `CultureInfo.InvariantCulture` to compare keys.</span></span> <span data-ttu-id="e7367-133">В следующем примере показан пользовательский класс сравнения, не учитывающий язык и региональные параметры. Для этого в конструктор `SortedList` передается параметр `comparer`.</span><span class="sxs-lookup"><span data-stu-id="e7367-133">The following example illustrates a custom culture-insensitive comparer class that you can specify as the `comparer` parameter to a `SortedList` constructor.</span></span>  
  
```vb  
Imports System  
Imports System.Collections  
Imports System.Globalization  
  
Friend Class InvariantComparer  
    Implements IComparer   
    Private m_compareInfo As CompareInfo  
    Friend Shared [Default] As New InvariantComparer()  
  
    Friend Sub New()  
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo  
    End Sub     
  
    Public Function Compare(a As Object, b As Object) As Integer _  
            Implements IComparer.Compare  
        Dim sa As String = CType(a, String)  
        Dim sb As String = CType(b, String)  
        If Not (sa Is Nothing) And Not (sb Is Nothing) Then  
            Return m_compareInfo.Compare(sa, sb)  
        Else  
            Return Comparer.Default.Compare(a, b)  
        End If  
    End Function  
End Class  
```  
  
```csharp  
using System;  
using System.Collections;  
using System.Globalization;  
  
internal class InvariantComparer : IComparer   
{  
    private CompareInfo m_compareInfo;  
    internal static readonly InvariantComparer Default = new  
        InvariantComparer();  
  
    internal InvariantComparer()   
    {  
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo;  
    }  
  
    public int Compare(Object a, Object b)  
    {  
        String sa = a as String;  
        String sb = b as String;  
        if (sa != null && sb != null)  
            return m_compareInfo.Compare(sa, sb);  
        else  
            return Comparer.Default.Compare(a,b);  
    }  
}  
```  
  
 <span data-ttu-id="e7367-134">В общем случае при использовании `SortedList` для строк без указания пользовательского инвариантного класса сравнения изменение `Thread.CurrentCulture` после заполнения списка может сделать список недействительным.</span><span class="sxs-lookup"><span data-stu-id="e7367-134">In general, if you use a `SortedList` on strings without specifying a custom invariant comparer, a change to `Thread.CurrentCulture` after the list has been populated can invalidate the list.</span></span>  
  
## <a name="using-the-arraylistsort-method"></a><span data-ttu-id="e7367-135">Использование метода ArrayList.Sort</span><span class="sxs-lookup"><span data-stu-id="e7367-135">Using the ArrayList.Sort Method</span></span>  
 <span data-ttu-id="e7367-136">Перегруженные версии метода по умолчанию `ArrayList.Sort` выполняют сортировку с учетом языка и региональных параметров благодаря использованию свойства `Thread.CurrentCulture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-136">Overloads of the `ArrayList.Sort` method perform culture-sensitive sorts by default using the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="e7367-137">Результаты могут различаться из-за различного порядка сортировки в разных языках и региональных параметрах.</span><span class="sxs-lookup"><span data-stu-id="e7367-137">Results can vary by culture due to different sort orders.</span></span> <span data-ttu-id="e7367-138">Чтобы результат не зависел от языка и региональных параметров, используйте перегрузки этого метода, которые принимают реализацию `IComparer`.</span><span class="sxs-lookup"><span data-stu-id="e7367-138">To eliminate culture-sensitive behavior, use the overloads of this method that accept an `IComparer` implementation.</span></span> <span data-ttu-id="e7367-139">В качестве параметра `comparer` укажите пользовательский инвариантный класс сравнения, который использует `CultureInfo.InvariantCulture`.</span><span class="sxs-lookup"><span data-stu-id="e7367-139">For the `comparer` parameter, specify a custom invariant comparer class that uses `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="e7367-140">Пример пользовательского инвариантного класса сравнения приведен в разделе [Использование класса SortedList](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1).</span><span class="sxs-lookup"><span data-stu-id="e7367-140">An example of a custom invariant comparer class is provided in the [Using the SortedList Class](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7367-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e7367-141">See Also</span></span>  
 <xref:System.Collections.CaseInsensitiveComparer>  
 <xref:System.Collections.CaseInsensitiveHashCodeProvider>  
 <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Collections.SortedList>  
 <xref:System.Collections.Hashtable>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="e7367-142">Выполнение строковых операций, не зависящих от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="e7367-142">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)  
 <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>
