---
title: "Операции с элементами (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: da747e884960c89fabc45d3761da92f913d66362
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="element-operations-c"></a><span data-ttu-id="8fa52-102">Операции с элементами (C#)</span><span class="sxs-lookup"><span data-stu-id="8fa52-102">Element Operations (C#)</span></span>
<span data-ttu-id="8fa52-103">Операции с элементами возвращают один определенный элемент из последовательности.</span><span class="sxs-lookup"><span data-stu-id="8fa52-103">Element operations return a single, specific element from a sequence.</span></span>  
  
 <span data-ttu-id="8fa52-104">В следующем разделе перечислены методы стандартных операторов запросов, которые выполняют операции с элементами.</span><span class="sxs-lookup"><span data-stu-id="8fa52-104">The standard query operator methods that perform element operations are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8fa52-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8fa52-105">Methods</span></span>  
  
|<span data-ttu-id="8fa52-106">Имя метода</span><span class="sxs-lookup"><span data-stu-id="8fa52-106">Method Name</span></span>|<span data-ttu-id="8fa52-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8fa52-107">Description</span></span>|<span data-ttu-id="8fa52-108">Синтаксис выражения запроса C#</span><span class="sxs-lookup"><span data-stu-id="8fa52-108">C# Query Expression Syntax</span></span>|<span data-ttu-id="8fa52-109">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="8fa52-109">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="8fa52-110">ElementAt</span><span class="sxs-lookup"><span data-stu-id="8fa52-110">ElementAt</span></span>|<span data-ttu-id="8fa52-111">Возвращает элемент коллекции с указанным индексом.</span><span class="sxs-lookup"><span data-stu-id="8fa52-111">Returns the element at a specified index in a collection.</span></span>|<span data-ttu-id="8fa52-112">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8fa52-112">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=fullName>|  
|<span data-ttu-id="8fa52-113">ElementAtOrDefault</span><span class="sxs-lookup"><span data-stu-id="8fa52-113">ElementAtOrDefault</span></span>|<span data-ttu-id="8fa52-114">Возвращает элемент коллекции с указанным индексом или значение по умолчанию, если индекс выходит за пределы допустимого диапазона.</span><span class="sxs-lookup"><span data-stu-id="8fa52-114">Returns the element at a specified index in a collection or a default value if the index is out of range.</span></span>|<span data-ttu-id="8fa52-115">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8fa52-115">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="8fa52-116">First</span><span class="sxs-lookup"><span data-stu-id="8fa52-116">First</span></span>|<span data-ttu-id="8fa52-117">Возвращает первый элемент коллекции или первый элемент, удовлетворяющий условию.</span><span class="sxs-lookup"><span data-stu-id="8fa52-117">Returns the first element of a collection, or the first element that satisfies a condition.</span></span>|<span data-ttu-id="8fa52-118">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8fa52-118">Not applicable.</span></span>|<xref:System.Linq.Enumerable.First%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=fullName>|  
|<span data-ttu-id="8fa52-119">FirstOrDefault</span><span class="sxs-lookup"><span data-stu-id="8fa52-119">FirstOrDefault</span></span>|<span data-ttu-id="8fa52-120">Возвращает первый элемент коллекции или первый элемент, удовлетворяющий условию.</span><span class="sxs-lookup"><span data-stu-id="8fa52-120">Returns the first element of a collection, or the first element that satisfies a condition.</span></span> <span data-ttu-id="8fa52-121">Если такой элемент не существует, возвращает значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8fa52-121">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="8fa52-122">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8fa52-122">Not applicable.</span></span>|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=fullName>|  
|<span data-ttu-id="8fa52-123">Последняя</span><span class="sxs-lookup"><span data-stu-id="8fa52-123">Last</span></span>|<span data-ttu-id="8fa52-124">Возвращает последний элемент коллекции или последний элемент, удовлетворяющий условию.</span><span class="sxs-lookup"><span data-stu-id="8fa52-124">Returns the last element of a collection, or the last element that satisfies a condition.</span></span>|<span data-ttu-id="8fa52-125">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8fa52-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Last%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=fullName>|  
|<span data-ttu-id="8fa52-126">LastOrDefault</span><span class="sxs-lookup"><span data-stu-id="8fa52-126">LastOrDefault</span></span>|<span data-ttu-id="8fa52-127">Возвращает последний элемент коллекции или последний элемент, удовлетворяющий условию.</span><span class="sxs-lookup"><span data-stu-id="8fa52-127">Returns the last element of a collection, or the last element that satisfies a condition.</span></span> <span data-ttu-id="8fa52-128">Если такой элемент не существует, возвращает значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8fa52-128">Returns a default value if no such element exists.</span></span>|<span data-ttu-id="8fa52-129">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8fa52-129">Not applicable.</span></span>|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=fullName>|  
|<span data-ttu-id="8fa52-130">Single</span><span class="sxs-lookup"><span data-stu-id="8fa52-130">Single</span></span>|<span data-ttu-id="8fa52-131">Возвращает единственный элемент коллекции или единственный элемент, удовлетворяющий условию.</span><span class="sxs-lookup"><span data-stu-id="8fa52-131">Returns the only element of a collection, or the only element that satisfies a condition.</span></span>|<span data-ttu-id="8fa52-132">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8fa52-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Single%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=fullName>|  
|<span data-ttu-id="8fa52-133">SingleOrDefault</span><span class="sxs-lookup"><span data-stu-id="8fa52-133">SingleOrDefault</span></span>|<span data-ttu-id="8fa52-134">Возвращает единственный элемент коллекции или единственный элемент, удовлетворяющий условию.</span><span class="sxs-lookup"><span data-stu-id="8fa52-134">Returns the only element of a collection, or the only element that satisfies a condition.</span></span> <span data-ttu-id="8fa52-135">Если такой элемент отсутствует или коллекция содержит не один такой элемент, возвращает значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8fa52-135">Returns a default value if no such element exists or the collection does not contain exactly one element.</span></span>|<span data-ttu-id="8fa52-136">Неприменимо.</span><span class="sxs-lookup"><span data-stu-id="8fa52-136">Not applicable.</span></span>|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a><span data-ttu-id="8fa52-137">См. также</span><span class="sxs-lookup"><span data-stu-id="8fa52-137">See Also</span></span>  
 <span data-ttu-id="8fa52-138"><xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="8fa52-138"><xref:System.Linq></span></span>   
 <span data-ttu-id="8fa52-139">[Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="8fa52-139">[Standard Query Operators Overview (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
 [<span data-ttu-id="8fa52-140">Практическое руководство. Запрос самого большого файла или файлов в дереве папок (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="8fa52-140">How to: Query for the Largest File or Files in a Directory Tree (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)

