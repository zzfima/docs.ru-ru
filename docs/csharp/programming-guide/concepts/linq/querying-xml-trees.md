---
title: Выполнение запросов к деревьям XML (C#)
ms.date: 07/20/2015
ms.assetid: 0913d81b-541a-4fd4-9cbf-7ec89fd817ea
ms.openlocfilehash: 5d2e40da26f30a0ece570acf2fd25684d1cba40f
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925589"
---
# <a name="querying-xml-trees-c"></a><span data-ttu-id="c2695-102">Выполнение запросов к деревьям XML (C#)</span><span class="sxs-lookup"><span data-stu-id="c2695-102">Querying XML Trees (C#)</span></span>
<span data-ttu-id="c2695-103">В этом разделе приведены примеры запросов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2695-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>  
  
 <span data-ttu-id="c2695-104">Дополнительные сведения о запросах [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] см. в разделе [Приступая к работе с LINQ в C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="c2695-104">For more information about writing [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries, see [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="c2695-105">После создания экземпляра XML-дерева наиболее эффективным способом извлечения данных из дерева становится запись запросов.</span><span class="sxs-lookup"><span data-stu-id="c2695-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="c2695-106">Кроме того, применение запросов в сочетании с функциональным построением позволяет создать новый XML-документ, имеющий другую форму по сравнению с исходным документом.</span><span class="sxs-lookup"><span data-stu-id="c2695-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c2695-107">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="c2695-107">In This Section</span></span>  
  
|<span data-ttu-id="c2695-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="c2695-108">Topic</span></span>|<span data-ttu-id="c2695-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="c2695-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c2695-110">Базовые запросы (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c2695-110">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="c2695-111">Содержит общие примеры запросов к XML-деревьям.</span><span class="sxs-lookup"><span data-stu-id="c2695-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="c2695-112">Проекции и преобразования (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c2695-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="c2695-113">Содержит общие примеры получения проекции и преобразования XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="c2695-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="c2695-114">Дополнительные способы создания запросов (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c2695-114">Advanced Query Techniques (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="c2695-115">Показывает способы выполнения запросов, применимые в более сложных сценариях.</span><span class="sxs-lookup"><span data-stu-id="c2695-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="c2695-116">LINQ to XML для пользователей XPath (C#)</span><span class="sxs-lookup"><span data-stu-id="c2695-116">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="c2695-117">Представляет число выражений XPath и их эквивалентов [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c2695-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="c2695-118">Чистые функциональные преобразования XML (C#)</span><span class="sxs-lookup"><span data-stu-id="c2695-118">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="c2695-119">Представляет небольшой учебник по написанию запросов в стиле функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="c2695-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c2695-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c2695-120">See Also</span></span>  
 [<span data-ttu-id="c2695-121">Руководство по программированию (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c2695-121">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)  
 [<span data-ttu-id="c2695-122">Приступая к работе с LINQ в C#</span><span class="sxs-lookup"><span data-stu-id="c2695-122">Getting Started with LINQ in C#</span></span>](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)
