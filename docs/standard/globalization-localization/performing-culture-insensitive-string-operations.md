---
title: "Выполнение строковых операций, не зависящих от языка и региональных параметров"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e703e9adc531b7d1695d3e9bbed61a2c0f62ad31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="performing-culture-insensitive-string-operations"></a><span data-ttu-id="d74dd-102">Выполнение строковых операций, не зависящих от языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="d74dd-102">Performing Culture-Insensitive String Operations</span></span>
<span data-ttu-id="d74dd-103">Большинство методов .NET Framework, выполняющих строковые операции с учетом языка и региональных параметров по умолчанию предоставляют перегрузки метода, которые позволяют явным образом указать язык и региональные параметры путем передачи <xref:System.Globalization.CultureInfo> параметра.</span><span class="sxs-lookup"><span data-stu-id="d74dd-103">Most .NET Framework methods that perform culture-sensitive string operations by default provide method overloads that allow you to explicitly specify the culture to use by passing a <xref:System.Globalization.CultureInfo> parameter.</span></span> <span data-ttu-id="d74dd-104">Эти перегрузки позволяют устранить различия в сопоставлении регистров и правилах сортировки, вызванные различием языка и региональных параметров, и получить результаты, которые не зависят от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d74dd-104">These overloads allow you to eliminate cultural variations in case mappings and sorting rules and guarantee culture-insensitive results.</span></span>  
  
 <span data-ttu-id="d74dd-105">В этом разделе содержатся следующие подразделы, которые показывают, как выполнять операции со строками без учета языка и региональных параметров с помощью методов платформы .NET Framework, которые по умолчанию учитывают язык и региональные параметры.</span><span class="sxs-lookup"><span data-stu-id="d74dd-105">This section provides the following topics to demonstrate how to perform culture-insensitive string operations using .NET Framework methods that are culture-sensitive by default.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d74dd-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="d74dd-106">In This Section</span></span>  
 [<span data-ttu-id="d74dd-107">Сравнение строк без учета языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="d74dd-107">Performing Culture-Insensitive String Comparisons</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 <span data-ttu-id="d74dd-108">Описывает использование <xref:System.String.Compare%2A?displayProperty=nameWithType> и <xref:System.String.CompareTo%2A?displayProperty=nameWithType> методы для выполнения сравнения строк без учета языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d74dd-108">Describes how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> and <xref:System.String.CompareTo%2A?displayProperty=nameWithType> methods to perform culture-insensitive string comparisons.</span></span>  
  
 [<span data-ttu-id="d74dd-109">Изменение регистра без учета языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="d74dd-109">Performing Culture-Insensitive Case Changes</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 <span data-ttu-id="d74dd-110">Описывает использование <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, и <xref:System.Char.ToLower%2A?displayProperty=nameWithType> методы для выполнения смены регистра независимо от языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d74dd-110">Describes how to use the <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods to perform culture-insensitive case changes.</span></span>  
  
 [<span data-ttu-id="d74dd-111">Выполнение строковых операций без учета языка и региональных параметров в коллекциях</span><span class="sxs-lookup"><span data-stu-id="d74dd-111">Performing Culture-Insensitive String Operations in Collections</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 <span data-ttu-id="d74dd-112">Описывает использование <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> класса <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> и <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> для выполнения операций без учета языка и региональных параметров в коллекции.</span><span class="sxs-lookup"><span data-stu-id="d74dd-112">Describes how to use the <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> class, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> and <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> to perform culture-insensitive operations in collections.</span></span>  
  
 [<span data-ttu-id="d74dd-113">Выполнение строковых операций без учета языка и региональных параметров в массивах</span><span class="sxs-lookup"><span data-stu-id="d74dd-113">Performing Culture-Insensitive String Operations in Arrays</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 <span data-ttu-id="d74dd-114">Описывает использование <xref:System.Array.Sort%2A?displayProperty=nameWithType> и <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> методы для выполнения операций без учета языка и региональных параметров в массивах.</span><span class="sxs-lookup"><span data-stu-id="d74dd-114">Describes how to use the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods to perform culture-insensitive operations in arrays.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d74dd-115">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="d74dd-115">Related Sections</span></span>  
 [<span data-ttu-id="d74dd-116">Операции со строками без учета языка и региональных параметров</span><span class="sxs-lookup"><span data-stu-id="d74dd-116">Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 <span data-ttu-id="d74dd-117">Описывает, почему следует иметь в виду язык и региональные параметры при выполнении операций над строками, и содержит указания о том, когда следует выполнять операции с учетом и без учета языка и региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="d74dd-117">Describes why you should be aware of culture when performing operations on strings and provides guidelines for when to perform culture-sensitive operations and when to perform culture-insensitive operations.</span></span>
