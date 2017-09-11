---
title: "Выполнение запросов к деревьям XML (C#)"
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
ms.assetid: 0913d81b-541a-4fd4-9cbf-7ec89fd817ea
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4bad11434ed2610492854d5ec4a7a84bceb189f3
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="querying-xml-trees-c"></a><span data-ttu-id="365bb-102">Выполнение запросов к деревьям XML (C#)</span><span class="sxs-lookup"><span data-stu-id="365bb-102">Querying XML Trees (C#)</span></span>
<span data-ttu-id="365bb-103">В этом разделе приведены примеры запросов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="365bb-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="365bb-104">Дополнительные сведения о запросах [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] см. в разделе [Приступая к работе с LINQ в C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="365bb-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="365bb-105">После создания экземпляра XML-дерева наиболее эффективным способом извлечения данных из дерева становится запись запросов.</span><span class="sxs-lookup"><span data-stu-id="365bb-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="365bb-106">Кроме того, применение запросов в сочетании с функциональным построением позволяет создать новый XML-документ, имеющий другую форму по сравнению с исходным документом.</span><span class="sxs-lookup"><span data-stu-id="365bb-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="365bb-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="365bb-107">In This Section</span></span>  
  
|<span data-ttu-id="365bb-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="365bb-108">Topic</span></span>|<span data-ttu-id="365bb-109">Описание</span><span class="sxs-lookup"><span data-stu-id="365bb-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="365bb-110">Базовые запросы (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="365bb-110">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="365bb-111">Содержит общие примеры запросов к XML-деревьям.</span><span class="sxs-lookup"><span data-stu-id="365bb-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="365bb-112">Проекции и преобразования (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="365bb-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="365bb-113">Содержит общие примеры получения проекции и преобразования XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="365bb-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="365bb-114">Дополнительные способы создания запросов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="365bb-114">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="365bb-115">Показывает способы выполнения запросов, применимые в более сложных сценариях.</span><span class="sxs-lookup"><span data-stu-id="365bb-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="365bb-116">LINQ to XML для пользователей XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="365bb-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="365bb-117">Представляет число выражений XPath и их эквивалентов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="365bb-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="365bb-118">Чистые функциональные преобразования XML (C#)</span><span class="sxs-lookup"><span data-stu-id="365bb-118">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="365bb-119">Представляет небольшой учебник по написанию запросов в стиле функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="365bb-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="365bb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="365bb-120">See Also</span></span>  
 <span data-ttu-id="365bb-121">[Руководство по программированию (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="365bb-121">[Programming Guide (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span></span>  
 [<span data-ttu-id="365bb-122">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="365bb-122">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)

