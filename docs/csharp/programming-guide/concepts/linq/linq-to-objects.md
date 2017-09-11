---
title: LINQ to Objects (C#)
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
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
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
ms.openlocfilehash: 565b506a2b01c9d32fbd339d700e663527ee3b6e
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-objects-c"></a><span data-ttu-id="eb9a2-102">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="eb9a2-102">LINQ to Objects (C#)</span></span>
<span data-ttu-id="eb9a2-103">Термин "LINQ to Objects" означает использование запросов LINQ с любой коллекцией <xref:System.Collections.IEnumerable> или <xref:System.Collections.Generic.IEnumerable%601> напрямую, без привлечения промежуточного поставщика LINQ, API [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) или [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span><span class="sxs-lookup"><span data-stu-id="eb9a2-103">The term "LINQ to Objects" refers to the use of LINQ queries with any <xref:System.Collections.IEnumerable> or <xref:System.Collections.Generic.IEnumerable%601> collection directly, without the use of an intermediate LINQ provider or API such as [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) or [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span> <span data-ttu-id="eb9a2-104">Вы можете выполнить запрос LINQ к любой перечислимой коллекции, такой как <xref:System.Collections.Generic.List%601>, <xref:System.Array> или <xref:System.Collections.Generic.Dictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-104">You can use LINQ to query any enumerable collections such as <xref:System.Collections.Generic.List%601>, <xref:System.Array>, or <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="eb9a2-105">Коллекция может быть определена пользователем или возвращена API .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-105">The collection may be user-defined or may be returned by a .NET Framework API.</span></span>  
  
 <span data-ttu-id="eb9a2-106">В общем смысле LINQ to Objects представляет собой новый подход к коллекциям.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-106">In a basic sense, LINQ to Objects represents a new approach to collections.</span></span> <span data-ttu-id="eb9a2-107">Раньше нужно было написать сложные циклы `foreach`, определяющие порядок извлечения данных из коллекции.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-107">In the old way, you had to write complex `foreach` loops that specified how to retrieve data from a collection.</span></span> <span data-ttu-id="eb9a2-108">При использовании LINQ пишется декларативный код, описывающий, какие данные необходимо извлечь.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-108">In the LINQ approach, you write declarative code that describes what you want to retrieve.</span></span>  
  
 <span data-ttu-id="eb9a2-109">Кроме того, запросы LINQ предлагают три основных преимущества по сравнению с традиционными циклами `foreach`:</span><span class="sxs-lookup"><span data-stu-id="eb9a2-109">In addition, LINQ queries offer three main advantages over traditional `foreach` loops:</span></span>  
  
1.  <span data-ttu-id="eb9a2-110">Они более краткие и удобочитаемые, особенно при фильтрации нескольких условий.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-110">They are more concise and readable, especially when filtering multiple conditions.</span></span>  
  
2.  <span data-ttu-id="eb9a2-111">Они предоставляют широкие возможности фильтрации, упорядочивания и группировки с минимумом кода приложения.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-111">They provide powerful filtering, ordering, and grouping capabilities with a minimum of application code.</span></span>  
  
3.  <span data-ttu-id="eb9a2-112">Они могут переноситься в другие источники данных практически без изменений.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-112">They can be ported to other data sources with little or no modification.</span></span>  
  
 <span data-ttu-id="eb9a2-113">В общем, чем сложнее операция, которую нужно выполнить с данными, тем больше преимуществ вы получаете при использовании LINQ вместо традиционных способов итерации.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-113">In general, the more complex the operation you want to perform on the data, the more benefit you will realize by using LINQ instead of traditional iteration techniques.</span></span>  
  
 <span data-ttu-id="eb9a2-114">Целью этого раздела является демонстрация подхода LINQ с помощью нескольких примеров.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-114">The purpose of this section is to demonstrate the LINQ approach with some select examples.</span></span> <span data-ttu-id="eb9a2-115">Он не претендует на исчерпывающий характер.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-115">It is not intended to be exhaustive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eb9a2-116">Содержание</span><span class="sxs-lookup"><span data-stu-id="eb9a2-116">In This Section</span></span>  
 [<span data-ttu-id="eb9a2-117">LINQ и строки (C#)</span><span class="sxs-lookup"><span data-stu-id="eb9a2-117">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 <span data-ttu-id="eb9a2-118">Использование LINQ для запроса и преобразования строк и коллекций строк.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-118">Explains how LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="eb9a2-119">Ссылки на разделы, демонстрирующие эти принципы.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-119">Also includes links to topics that demonstrate these principles.</span></span>  
  
 [<span data-ttu-id="eb9a2-120">LINQ и отражение (C#)</span><span class="sxs-lookup"><span data-stu-id="eb9a2-120">LINQ and Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-reflection.md)  
 <span data-ttu-id="eb9a2-121">Ссылки на пример, демонстрирующий, как LINQ использует отражение.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-121">Links to a sample that demonstrates how LINQ uses reflection.</span></span>  
  
 [<span data-ttu-id="eb9a2-122">LINQ и каталоги файлов (C#)</span><span class="sxs-lookup"><span data-stu-id="eb9a2-122">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)  
 <span data-ttu-id="eb9a2-123">Использование LINQ для взаимодействия с файловыми системами.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-123">Explains how LINQ can be used to interact with file systems.</span></span> <span data-ttu-id="eb9a2-124">Ссылки на разделы, демонстрирующие эти понятия.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-124">Also includes links to topics that demonstrate these concepts.</span></span>  
  
 [<span data-ttu-id="eb9a2-125">Практическое руководство. Выполнение запроса к ArrayList с помощью LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="eb9a2-125">How to: Query an ArrayList with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 <span data-ttu-id="eb9a2-126">Выполнение запроса ArrayList в C#.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-126">Demonstrates how to query an ArrayList in C#.</span></span>  
  
 [<span data-ttu-id="eb9a2-127">Практическое руководство. Добавление настраиваемых методов для запросов LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="eb9a2-127">How to: Add Custom Methods for LINQ Queries (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 <span data-ttu-id="eb9a2-128">Расширение набора методов, которые можно использовать для запросов LINQ путем добавления методов расширения в интерфейс <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-128">Explains how to extend the set of methods that you can use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>  
  
 [<span data-ttu-id="eb9a2-129">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="eb9a2-129">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="eb9a2-130">Ссылки на разделы, рассказывающие LINQ и содержащие примеры кода выполнения запросов.</span><span class="sxs-lookup"><span data-stu-id="eb9a2-130">Provides links to topics that explain LINQ and provide examples of code that perform queries.</span></span>

