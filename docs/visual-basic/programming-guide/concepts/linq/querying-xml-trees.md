---
title: "Выполнение запросов деревьям XML (Visual Basic) | Документы Microsoft"
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
ms.assetid: 2e35c1ab-08c8-4378-9ca8-8ff344756eda
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9b2aa1e4852657590449be3e297302bf41ba3e5d
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017


---
# <a name="querying-xml-trees-visual-basic"></a><span data-ttu-id="e9869-102">Выполнение запросов к деревьям XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9869-102">Querying XML Trees (Visual Basic)</span></span>
<span data-ttu-id="e9869-103">В этом разделе приведены примеры запросов [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9869-103">This section provides examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] queries.</span></span>  
  
 <span data-ttu-id="e9869-104">Дополнительные сведения о записи [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросах см [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span><span class="sxs-lookup"><span data-stu-id="e9869-104">For more information about writing [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries, see [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).</span></span>  
  
 <span data-ttu-id="e9869-105">После создания экземпляра XML-дерева наиболее эффективным способом извлечения данных из дерева становится запись запросов.</span><span class="sxs-lookup"><span data-stu-id="e9869-105">After you have instantiated an XML tree, writing queries is the most effective way to extract data from the tree.</span></span> <span data-ttu-id="e9869-106">Кроме того, применение запросов в сочетании с функциональным построением позволяет создать новый XML-документ, имеющий другую форму по сравнению с исходным документом.</span><span class="sxs-lookup"><span data-stu-id="e9869-106">Also, querying combined with functional construction enables you to generate a new XML document that has a different shape from the original document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9869-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="e9869-107">In This Section</span></span>  
  
|<span data-ttu-id="e9869-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="e9869-108">Topic</span></span>|<span data-ttu-id="e9869-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e9869-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e9869-110">Базовые запросы (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9869-110">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)|<span data-ttu-id="e9869-111">Содержит общие примеры запросов к XML-деревьям.</span><span class="sxs-lookup"><span data-stu-id="e9869-111">Provides common examples of querying XML trees.</span></span>|  
|[<span data-ttu-id="e9869-112">Проекции и преобразования (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9869-112">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)|<span data-ttu-id="e9869-113">Содержит общие примеры получения проекции и преобразования XML-деревьев.</span><span class="sxs-lookup"><span data-stu-id="e9869-113">Provides common examples of projecting from and transforming XML trees.</span></span>|  
|[<span data-ttu-id="e9869-114">Дополнительные способы создания запросов (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9869-114">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)|<span data-ttu-id="e9869-115">Показывает способы выполнения запросов, применимые в более сложных сценариях.</span><span class="sxs-lookup"><span data-stu-id="e9869-115">Provides query techniques that are useful in more advanced scenarios.</span></span>|  
|[<span data-ttu-id="e9869-116">LINQ to XML для пользователей XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9869-116">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)|<span data-ttu-id="e9869-117">Представляет число выражений XPath и их [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] эквиваленты.</span><span class="sxs-lookup"><span data-stu-id="e9869-117">Presents a number of XPath expressions and their [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] equivalents.</span></span>|  
|[<span data-ttu-id="e9869-118">Чисто функциональные преобразования XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e9869-118">Pure Functional Transformations of XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)|<span data-ttu-id="e9869-119">Представляет небольшой учебник по написанию запросов в стиле функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="e9869-119">Presents a small tutorial on writing queries in the style of functional programming.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e9869-120">См. также</span><span class="sxs-lookup"><span data-stu-id="e9869-120">See Also</span></span>  
 <span data-ttu-id="e9869-121">[Руководство по программированию (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span><span class="sxs-lookup"><span data-stu-id="e9869-121">[Programming Guide (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md) </span></span>  
<span data-ttu-id="e9869-122"> [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)</span><span class="sxs-lookup"><span data-stu-id="e9869-122"> [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)</span></span>
