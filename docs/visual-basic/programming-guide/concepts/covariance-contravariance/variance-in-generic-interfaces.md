---
title: "Вариативность в универсальных интерфейсах (Visual Basic) | Документы Microsoft"
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
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
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
ms.openlocfilehash: c53c27bdb085213046553fc4b08f11336880a7c2
ms.contentlocale: ru-ru
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-visual-basic"></a><span data-ttu-id="4ee46-102">Вариативность в универсальных интерфейсах (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ee46-102">Variance in Generic Interfaces (Visual Basic)</span></span>
<span data-ttu-id="4ee46-103">Платформа .NET framework 4 появилась поддержка вариативности для нескольких существующих универсальных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="4ee46-103">.NET Framework 4 introduced variance support for several existing generic interfaces.</span></span> <span data-ttu-id="4ee46-104">Поддержка вариативности позволяет выполнять неявное преобразование классов, реализующих эти интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="4ee46-104">Variance support enables implicit conversion of classes that implement these interfaces.</span></span> <span data-ttu-id="4ee46-105">Вариант теперь являются следующие интерфейсы:</span><span class="sxs-lookup"><span data-stu-id="4ee46-105">The following interfaces are now variant:</span></span>  
  
-   <span data-ttu-id="4ee46-106"><xref:System.Collections.Generic.IEnumerable%601>(T является ковариантным)</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="4ee46-106"><xref:System.Collections.Generic.IEnumerable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="4ee46-107"><xref:System.Collections.Generic.IEnumerator%601>(T является ковариантным)</xref:System.Collections.Generic.IEnumerator%601></span><span class="sxs-lookup"><span data-stu-id="4ee46-107"><xref:System.Collections.Generic.IEnumerator%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="4ee46-108"><xref:System.Linq.IQueryable%601>(T является ковариантным)</xref:System.Linq.IQueryable%601></span><span class="sxs-lookup"><span data-stu-id="4ee46-108"><xref:System.Linq.IQueryable%601> (T is covariant)</span></span>  
  
-   <span data-ttu-id="4ee46-109"><xref:System.Linq.IGrouping%602>(`TKey` и `TElement` ковариантных)</xref:System.Linq.IGrouping%602></span><span class="sxs-lookup"><span data-stu-id="4ee46-109"><xref:System.Linq.IGrouping%602> (`TKey` and `TElement` are covariant)</span></span>  
  
-   <span data-ttu-id="4ee46-110"><xref:System.Collections.Generic.IComparer%601>(T является контравариантным)</xref:System.Collections.Generic.IComparer%601></span><span class="sxs-lookup"><span data-stu-id="4ee46-110"><xref:System.Collections.Generic.IComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="4ee46-111"><xref:System.Collections.Generic.IEqualityComparer%601>(T является контравариантным)</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="4ee46-111"><xref:System.Collections.Generic.IEqualityComparer%601> (T is contravariant)</span></span>  
  
-   <span data-ttu-id="4ee46-112"><xref:System.IComparable%601>(T является контравариантным)</xref:System.IComparable%601></span><span class="sxs-lookup"><span data-stu-id="4ee46-112"><xref:System.IComparable%601> (T is contravariant)</span></span>  
  
 <span data-ttu-id="4ee46-113">Ковариация позволяет методу иметь более производный тип возвращаемого значения, определенного параметром универсального типа интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4ee46-113">Covariance permits a method to have a more derived return type than that defined by the generic type parameter of the interface.</span></span> <span data-ttu-id="4ee46-114">Чтобы продемонстрировать функцию ковариации, рассмотрим следующие универсальные интерфейсы: `IEnumerable(Of Object)` и `IEnumerable(Of String)`.</span><span class="sxs-lookup"><span data-stu-id="4ee46-114">To illustrate the covariance feature, consider these generic interfaces: `IEnumerable(Of Object)` and `IEnumerable(Of String)`.</span></span> <span data-ttu-id="4ee46-115">`IEnumerable(Of String)` Не наследует интерфейс `IEnumerable(Of Object)` интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4ee46-115">The `IEnumerable(Of String)` interface does not inherit the `IEnumerable(Of Object)` interface.</span></span> <span data-ttu-id="4ee46-116">Тем не менее `String` тип наследовать `Object` типа, а в некоторых случаях может потребоваться назначение объектов этих интерфейсов друг с другом.</span><span class="sxs-lookup"><span data-stu-id="4ee46-116">However, the `String` type does inherit the `Object` type, and in some cases you may want to assign objects of these interfaces to each other.</span></span> <span data-ttu-id="4ee46-117">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="4ee46-117">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="4ee46-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4ee46-118"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4ee46-119">В более ранних версиях платформы .NET Framework, этот код вызовет ошибку компиляции в Visual Basic с `Option Strict On`.</span><span class="sxs-lookup"><span data-stu-id="4ee46-119">In earlier versions of the .NET Framework, this code causes a compilation error in Visual Basic with `Option Strict On`.</span></span> <span data-ttu-id="4ee46-120">Но теперь вы можете использовать `strings` вместо `objects`, как показано в предыдущем примере, поскольку <xref:System.Collections.Generic.IEnumerable%601>интерфейс является ковариантным.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="4ee46-120">But now you can use `strings` instead of `objects`, as shown in the previous example, because the <xref:System.Collections.Generic.IEnumerable%601> interface is covariant.</span></span>  
  
 <span data-ttu-id="4ee46-121">Контрвариантность позволяет методу иметь типы аргументов, для которых меньше, чем указано параметром универсального интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4ee46-121">Contravariance permits a method to have argument types that are less derived than that specified by the generic parameter of the interface.</span></span> <span data-ttu-id="4ee46-122">Чтобы продемонстрировать функцию контравариации, предположим, что вы создали `BaseComparer` класса для сравнения экземпляров `BaseClass` класса.</span><span class="sxs-lookup"><span data-stu-id="4ee46-122">To illustrate contravariance, assume that you have created a `BaseComparer` class to compare instances of the `BaseClass` class.</span></span> <span data-ttu-id="4ee46-123">Класс `BaseComparer` реализует интерфейс `IEqualityComparer(Of BaseClass)`.</span><span class="sxs-lookup"><span data-stu-id="4ee46-123">The `BaseComparer` class implements the `IEqualityComparer(Of BaseClass)` interface.</span></span> <span data-ttu-id="4ee46-124">Поскольку <xref:System.Collections.Generic.IEqualityComparer%601>интерфейса теперь является контравариантным, можно использовать `BaseComparer` для сравнения экземпляров классов, наследующих `BaseClass` класса</xref:System.Collections.Generic.IEqualityComparer%601></span><span class="sxs-lookup"><span data-stu-id="4ee46-124">Because the <xref:System.Collections.Generic.IEqualityComparer%601> interface is now contravariant, you can use `BaseComparer` to compare instances of classes that inherit the `BaseClass` class.</span></span> <span data-ttu-id="4ee46-125">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="4ee46-125">This is shown in the following code example.</span></span>  
  
<span data-ttu-id="4ee46-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4ee46-126"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4ee46-127">Дополнительные примеры см. в разделе [Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span><span class="sxs-lookup"><span data-stu-id="4ee46-127">For more examples, see [Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).</span></span>  
  
 <span data-ttu-id="4ee46-128">Вариативность в универсальных интерфейсах поддерживается только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="4ee46-128">Variance in generic interfaces is supported for reference types only.</span></span> <span data-ttu-id="4ee46-129">Типы значений не поддерживают вариативность.</span><span class="sxs-lookup"><span data-stu-id="4ee46-129">Value types do not support variance.</span></span> <span data-ttu-id="4ee46-130">Например `IEnumerable(Of Integer)` не может быть неявно преобразован в `IEnumerable(Of Object)`, так как целочисленные типы представлены по типу значения.</span><span class="sxs-lookup"><span data-stu-id="4ee46-130">For example, `IEnumerable(Of Integer)` cannot be implicitly converted to `IEnumerable(Of Object)`, because integers are represented by a value type.</span></span>  
  
<span data-ttu-id="4ee46-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="4ee46-131"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
 <span data-ttu-id="4ee46-132">Также важно помнить, что классов, реализующих вариантные интерфейсы являются инвариантными.</span><span class="sxs-lookup"><span data-stu-id="4ee46-132">It is also important to remember that classes that implement variant interfaces are still invariant.</span></span> <span data-ttu-id="4ee46-133">Например несмотря на то что <xref:System.Collections.Generic.List%601>реализует ковариантный интерфейс <xref:System.Collections.Generic.IEnumerable%601>, нельзя неявно преобразовать `List(Of Object)` для `List(Of String)`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="4ee46-133">For example, although <xref:System.Collections.Generic.List%601> implements the covariant interface <xref:System.Collections.Generic.IEnumerable%601>, you cannot implicitly convert `List(Of Object)` to `List(Of String)`.</span></span> <span data-ttu-id="4ee46-134">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="4ee46-134">This is illustrated in the following code example.</span></span>  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ee46-135">См. также</span><span class="sxs-lookup"><span data-stu-id="4ee46-135">See Also</span></span>  
 <span data-ttu-id="4ee46-136">[Использование вариативности в интерфейсах для универсальных коллекций (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span><span class="sxs-lookup"><span data-stu-id="4ee46-136">[Using Variance in Interfaces for Generic Collections (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md) </span></span>  
<span data-ttu-id="4ee46-137"> [Создание вариативных универсальных интерфейсов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span><span class="sxs-lookup"><span data-stu-id="4ee46-137"> [Creating Variant Generic Interfaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) </span></span>  
<span data-ttu-id="4ee46-138"> [Универсальные интерфейсы](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span><span class="sxs-lookup"><span data-stu-id="4ee46-138"> [Generic Interfaces](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf) </span></span>  
<span data-ttu-id="4ee46-139"> [Вариативность в делегатах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span><span class="sxs-lookup"><span data-stu-id="4ee46-139"> [Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)</span></span>
