---
title: "Учебник. Объединение запросов в цепочки (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 44f54444-c4c5-4c23-9d19-986b957b8eda
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 08196f4780e566cc05e36b6cfe78caad3e9c96a1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="tutorial-chaining-queries-together-c"></a><span data-ttu-id="19754-102">Учебник. Объединение запросов в цепочки (C#)</span><span class="sxs-lookup"><span data-stu-id="19754-102">Tutorial: Chaining Queries Together (C#)</span></span>
<span data-ttu-id="19754-103">В этом учебнике приводится модель обработки, при которой запросы объединяются в цепочку.</span><span class="sxs-lookup"><span data-stu-id="19754-103">This tutorial illustrates the processing model when you chain queries together.</span></span> <span data-ttu-id="19754-104">Объединение запросов в цепочку - ключевая часть написания функциональных преобразований.</span><span class="sxs-lookup"><span data-stu-id="19754-104">Chaining queries together is a key part of writing functional transformations.</span></span> <span data-ttu-id="19754-105">Необходимо полностью понимать принцип работы запросов, объединенных в цепочку.</span><span class="sxs-lookup"><span data-stu-id="19754-105">It is important to understand exactly how chained queries work.</span></span>  
  
 <span data-ttu-id="19754-106">Запросы, с помощью которых обрабатываются XML-документы Office Open, широко используют этот способ.</span><span class="sxs-lookup"><span data-stu-id="19754-106">The queries that process Office Open XML documents use this technique extensively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="19754-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="19754-107">In This Section</span></span>  
  
|<span data-ttu-id="19754-108">Раздел</span><span class="sxs-lookup"><span data-stu-id="19754-108">Topic</span></span>|<span data-ttu-id="19754-109">Описание</span><span class="sxs-lookup"><span data-stu-id="19754-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="19754-110">Отложенное выполнение и отложенное вычисление в LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="19754-110">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)|<span data-ttu-id="19754-111">Описываются основные понятия отложенного выполнения и неспешного вычисления.</span><span class="sxs-lookup"><span data-stu-id="19754-111">Describes the concepts of deferred execution and lazy evaluation.</span></span>|  
|[<span data-ttu-id="19754-112">Пример отложенного выполнения (C#)</span><span class="sxs-lookup"><span data-stu-id="19754-112">Deferred Execution Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)|<span data-ttu-id="19754-113">Также приводится пример отложенного выполнения.</span><span class="sxs-lookup"><span data-stu-id="19754-113">Provides an example of deferred execution.</span></span>|  
|[<span data-ttu-id="19754-114">Пример связывания запросов (C#)</span><span class="sxs-lookup"><span data-stu-id="19754-114">Chaining Queries Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)|<span data-ttu-id="19754-115">Показывается принцип работы отложенного исполнения при объединении запросов.</span><span class="sxs-lookup"><span data-stu-id="19754-115">Shows how deferred execution works when chaining queries together.</span></span>|  
|[<span data-ttu-id="19754-116">Промежуточная материализация (C#)</span><span class="sxs-lookup"><span data-stu-id="19754-116">Intermediate Materialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)|<span data-ttu-id="19754-117">Определяются и разъясняются семантические принципы промежуточной материализации.</span><span class="sxs-lookup"><span data-stu-id="19754-117">Identifies and illustrates the semantics of intermediate materialization.</span></span>|  
|[<span data-ttu-id="19754-118">Связывание стандартных операторов запросов (C#)</span><span class="sxs-lookup"><span data-stu-id="19754-118">Chaining Standard Query Operators Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)|<span data-ttu-id="19754-119">Описывается семантика отложенного вычисления стандартных операторов запроса.</span><span class="sxs-lookup"><span data-stu-id="19754-119">Describes the lazy semantics of the standard query operators.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19754-120">См. также</span><span class="sxs-lookup"><span data-stu-id="19754-120">See Also</span></span>  
 [<span data-ttu-id="19754-121">Чистые функциональные преобразования XML (C#)</span><span class="sxs-lookup"><span data-stu-id="19754-121">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
