---
title: "LINQ и универсальные типы (C#)"
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
helpviewer_keywords:
- LINQ [C#], generic types
- generic types [LINQ]
- generics [LINQ]
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 177db64491d58b31ca50cef0bb2eda8c2cb65078
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="linq-and-generic-types-c"></a><span data-ttu-id="58fa1-102">LINQ и универсальные типы (C#)</span><span class="sxs-lookup"><span data-stu-id="58fa1-102">LINQ and Generic Types (C#)</span></span>
<span data-ttu-id="58fa1-103">Запросы [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] основаны на универсальных типах, которые впервые появились в версии [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 2.0.</span><span class="sxs-lookup"><span data-stu-id="58fa1-103">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries are based on generic types, which were introduced in version 2.0 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="58fa1-104">Для того чтобы приступить к написанию запросов, не требуется глубокое знание универсальных типов.</span><span class="sxs-lookup"><span data-stu-id="58fa1-104">You do not need an in-depth knowledge of generics before you can start writing queries.</span></span> <span data-ttu-id="58fa1-105">Тем не менее необходимо понимание двух основных принципов.</span><span class="sxs-lookup"><span data-stu-id="58fa1-105">However, you may want to understand two basic concepts:</span></span>  
  
1.  <span data-ttu-id="58fa1-106">При создании экземпляра универсального класса коллекции, такого как <xref:System.Collections.Generic.List%601>, замените "T" типом объектов, которые будут храниться в списке.</span><span class="sxs-lookup"><span data-stu-id="58fa1-106">When you create an instance of a generic collection class such as <xref:System.Collections.Generic.List%601>, you replace the "T" with the type of objects that the list will hold.</span></span> <span data-ttu-id="58fa1-107">Например, список строк выражается как `List<string>`, а список объектов `Customer` — как `List<Customer>`.</span><span class="sxs-lookup"><span data-stu-id="58fa1-107">For example, a list of strings is expressed as `List<string>`, and a list of `Customer` objects is expressed as `List<Customer>`.</span></span> <span data-ttu-id="58fa1-108">Универсальный список является строго типизированным и предоставляет ряд преимуществ по сравнению с коллекциями, которые хранят свои элементы как <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="58fa1-108">A generic list is strongly typed and provides many benefits over collections that store their elements as <xref:System.Object>.</span></span> <span data-ttu-id="58fa1-109">При попытке добавить `Customer` в `List<string>` будет выдана ошибка во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="58fa1-109">If you try to add a `Customer` to a `List<string>`, you will get an error at compile time.</span></span> <span data-ttu-id="58fa1-110">Универсальные коллекции просты в использовании, поскольку нет необходимости выполнять приведение типов во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="58fa1-110">It is easy to use generic collections because you do not have to perform run-time type-casting.</span></span>  
  
2.  <span data-ttu-id="58fa1-111"><xref:System.Collections.Generic.IEnumerable%601> — это интерфейс, поддерживающий перечисление универсальных классов коллекций с помощью оператора `foreach`.</span><span class="sxs-lookup"><span data-stu-id="58fa1-111"><xref:System.Collections.Generic.IEnumerable%601> is the interface that enables generic collection classes to be enumerated by using the `foreach` statement.</span></span> <span data-ttu-id="58fa1-112">Универсальные классы коллекций поддерживают <xref:System.Collections.Generic.IEnumerable%601> так же, как неуниверсальные классы коллекций (например <xref:System.Collections.ArrayList>) поддерживают <xref:System.Collections.IEnumerable>.</span><span class="sxs-lookup"><span data-stu-id="58fa1-112">Generic collection classes support <xref:System.Collections.Generic.IEnumerable%601> just as non-generic collection classes such as <xref:System.Collections.ArrayList> support <xref:System.Collections.IEnumerable>.</span></span>  
  
 <span data-ttu-id="58fa1-113">Дополнительные сведения об универсальных классах см. в разделе [Универсальные шаблоны](../../../../csharp/programming-guide/generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="58fa1-113">For more information about generics, see [Generics](../../../../csharp/programming-guide/generics/index.md).</span></span>  
  
## <a name="ienumerablet-variables-in-linq-queries"></a><span data-ttu-id="58fa1-114">Переменные IEnumerable<T\> в запросах LINQ</span><span class="sxs-lookup"><span data-stu-id="58fa1-114">IEnumerable<T\> variables in LINQ Queries</span></span>  
 <span data-ttu-id="58fa1-115">Переменные запроса [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] типизированы как <xref:System.Collections.Generic.IEnumerable%601> или производный тип, например <xref:System.Linq.IQueryable%601>.</span><span class="sxs-lookup"><span data-stu-id="58fa1-115">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query variables are typed as <xref:System.Collections.Generic.IEnumerable%601> or a derived type such as <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="58fa1-116">Если появляется переменная запроса, которая типизируется как `IEnumerable<Customer>`, это просто означает, что запрос при выполнении выведет последовательность из нуля или более объектов `Customer`.</span><span class="sxs-lookup"><span data-stu-id="58fa1-116">When you see a query variable that is typed as `IEnumerable<Customer>`, it just means that the query, when it is executed, will produce a sequence of zero or more `Customer` objects.</span></span>  
  
 <span data-ttu-id="58fa1-117">[!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="58fa1-117">[!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]</span></span>  
  
 <span data-ttu-id="58fa1-118">Дополнительные сведения см. в разделе [Связи типов в операциях запроса LINQ](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="58fa1-118">For more information, see [Type Relationships in LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="letting-the-compiler-handle-generic-type-declarations"></a><span data-ttu-id="58fa1-119">Передача обработки объявлений универсальных типов компилятору</span><span class="sxs-lookup"><span data-stu-id="58fa1-119">Letting the Compiler Handle Generic Type Declarations</span></span>  
 <span data-ttu-id="58fa1-120">При желании можно отказаться от обычного синтаксиса универсальных типов, используя ключевое слово [var](../../../../csharp/language-reference/keywords/var.md).</span><span class="sxs-lookup"><span data-stu-id="58fa1-120">If you prefer, you can avoid generic syntax by using the [var](../../../../csharp/language-reference/keywords/var.md) keyword.</span></span> <span data-ttu-id="58fa1-121">Ключевое слово `var` дает компилятору указание вывести тип переменной запроса путем поиска в источнике данных, указанном в предложении `from`.</span><span class="sxs-lookup"><span data-stu-id="58fa1-121">The `var` keyword instructs the compiler to infer the type of a query variable by looking at the data source specified in the `from` clause.</span></span> <span data-ttu-id="58fa1-122">В следующем примере создается тот же скомпилированный код, что и в предыдущем примере:</span><span class="sxs-lookup"><span data-stu-id="58fa1-122">The following example produces the same compiled code as the previous example:</span></span>  
  
 <span data-ttu-id="58fa1-123">[!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="58fa1-123">[!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]</span></span>  
  
 <span data-ttu-id="58fa1-124">Ключевое слово `var` удобно, если тип переменной является очевидным, или если не требуется явно указывать вложенные универсальные типы, например создаваемые групповыми запросами.</span><span class="sxs-lookup"><span data-stu-id="58fa1-124">The `var` keyword is useful when the type of the variable is obvious or when it is not that important to explicitly specify nested generic types such as those that are produced by group queries.</span></span> <span data-ttu-id="58fa1-125">Как правило, рекомендуется помнить о том, что использование `var` делает код более сложным для чтения.</span><span class="sxs-lookup"><span data-stu-id="58fa1-125">In general, we recommend that if you use `var`, realize that it can make your code more difficult for others to read.</span></span> <span data-ttu-id="58fa1-126">Дополнительные сведения см. в разделе [Неявно типизированные локальные переменные](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span><span class="sxs-lookup"><span data-stu-id="58fa1-126">For more information, see [Implicitly Typed Local Variables](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58fa1-127">См. также</span><span class="sxs-lookup"><span data-stu-id="58fa1-127">See Also</span></span>  
 <span data-ttu-id="58fa1-128">[Приступая к работе с LINQ в C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span><span class="sxs-lookup"><span data-stu-id="58fa1-128">[Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) </span></span>  
 [<span data-ttu-id="58fa1-129">Универсальные шаблоны</span><span class="sxs-lookup"><span data-stu-id="58fa1-129">Generics</span></span>](../../../../csharp/programming-guide/generics/index.md)

