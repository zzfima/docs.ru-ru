---
title: "Применимость функциональных преобразований (C#)"
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
ms.assetid: c78107bd-b006-4574-a3d4-bbf808388ff3
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b008bdef820b979e2aabd480e08a3bfa5ee5afa2
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="applicability-of-functional-transformation-c"></a><span data-ttu-id="d6427-102">Применимость функциональных преобразований (C#)</span><span class="sxs-lookup"><span data-stu-id="d6427-102">Applicability of Functional Transformation (C#)</span></span>
<span data-ttu-id="d6427-103">Чисто функциональные преобразования применяются в самых разнообразных ситуациях.</span><span class="sxs-lookup"><span data-stu-id="d6427-103">Pure functional transformations are applicable in a wide variety of situations.</span></span>  
  
 <span data-ttu-id="d6427-104">Подход с использованием функциональных преобразований идеально подходит для запросов и управления структурированными данными, поэтому вполне соответствует технологиям LINQ.</span><span class="sxs-lookup"><span data-stu-id="d6427-104">The functional transformation approach is ideally suited for querying and manipulating structured data; therefore it fits well with LINQ technologies.</span></span> <span data-ttu-id="d6427-105">Но функциональные преобразования могут применяться гораздо шире, чем только в LINQ.</span><span class="sxs-lookup"><span data-stu-id="d6427-105">However, functional transformation has a much wider applicability than use with LINQ.</span></span> <span data-ttu-id="d6427-106">Любой процесс, основной задачей которого является преобразование данных из одной формы в другую, может считаться применимым для функционального преобразования.</span><span class="sxs-lookup"><span data-stu-id="d6427-106">Any process where the main focus is on transforming data from one form to another should probably be considered as a candidate for functional transformation.</span></span>  
  
 <span data-ttu-id="d6427-107">Этот подход можно использовать при решении многих задач, даже если на первый взгляд кажется, что он неприменим.</span><span class="sxs-lookup"><span data-stu-id="d6427-107">This approach is applicable to many problems that might not appear at first glance to be a candidate.</span></span> <span data-ttu-id="d6427-108">Применение функциональных преобразований в сочетании с технологиями LINQ или без них должно рассматриваться при работе со следующими объектами.</span><span class="sxs-lookup"><span data-stu-id="d6427-108">Used in conjunction with or separately from LINQ, functional transformation should be considered for the following areas:</span></span>  
  
-   <span data-ttu-id="d6427-109">Документы на основе XML.</span><span class="sxs-lookup"><span data-stu-id="d6427-109">XML-based documents.</span></span> <span data-ttu-id="d6427-110">Имеющие правильный формат данные на любом диалекте языка XML могут быть легко подвергнуты функциональным преобразованиям.</span><span class="sxs-lookup"><span data-stu-id="d6427-110">Well-formed data of any XML dialect can be easily manipulated through functional transformation.</span></span> <span data-ttu-id="d6427-111">Дополнительные сведения см. в разделе [Функциональное преобразование XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d6427-111">For more information, see [Functional Transformation of XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md).</span></span>  
  
-   <span data-ttu-id="d6427-112">Другие структурированные форматы файлов.</span><span class="sxs-lookup"><span data-stu-id="d6427-112">Other structured file formats.</span></span> <span data-ttu-id="d6427-113">Большинство файлов, от Windows.ini до обычных текстовых документов, имеют определенную структуру, которую можно анализировать и преобразовывать.</span><span class="sxs-lookup"><span data-stu-id="d6427-113">From Windows.ini files to plain text documents, most files have some structure that lends itself to analysis and transformation.</span></span>  
  
-   <span data-ttu-id="d6427-114">Протоколы потоковых данных.</span><span class="sxs-lookup"><span data-stu-id="d6427-114">Data streaming protocols.</span></span> <span data-ttu-id="d6427-115">Кодирование и декодирование данных в коммуникационных протоколах часто можно представить в виде простого функционального преобразования.</span><span class="sxs-lookup"><span data-stu-id="d6427-115">Encoding data into and decoding data from communication protocols can often be represented by a simple functional transform.</span></span>  
  
-   <span data-ttu-id="d6427-116">Данные RDBMS и OODBMS.</span><span class="sxs-lookup"><span data-stu-id="d6427-116">RDBMS and OODBMS data.</span></span> <span data-ttu-id="d6427-117">Реляционные и объектно-ориентированные базы данных, как и XML, являются широко используемыми структурированными источниками данных.</span><span class="sxs-lookup"><span data-stu-id="d6427-117">Relational and object-oriented databases, just like XML, are widely-used structured data sources.</span></span>  
  
-   <span data-ttu-id="d6427-118">Математические, статистические и научные решения.</span><span class="sxs-lookup"><span data-stu-id="d6427-118">Mathematic, statistic, and science solutions.</span></span> <span data-ttu-id="d6427-119">В этих областях происходит обработка больших наборов данных, чтобы пользователь мог представлять визуально, оценивать или действительно решить нетривиальные задачи.</span><span class="sxs-lookup"><span data-stu-id="d6427-119">These fields tend to manipulate large data sets to assist the user in visualizing, estimating, or actually solving non-trivial problems.</span></span>  
  
 <span data-ttu-id="d6427-120">Как описано в разделе [Рефакторинг в чистые функции (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md), использование чистых функций является примером функционального программирования.</span><span class="sxs-lookup"><span data-stu-id="d6427-120">As described in [Refactoring Into Pure Functions (C#)](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md), using pure functions is an example of functional programming.</span></span> <span data-ttu-id="d6427-121">Кроме очевидных преимуществ чистых функций, их применение позволяет получить ценный опыт решения проблем с точки зрения применения функциональных преобразований.</span><span class="sxs-lookup"><span data-stu-id="d6427-121">In additional to their immediate benefits, using pure functions provides valuable experience in thinking about problems from a functional transformation perspective.</span></span> <span data-ttu-id="d6427-122">Такой подход может серьезно повлиять на стиль программирования и конструирования классов.</span><span class="sxs-lookup"><span data-stu-id="d6427-122">This approach can also have major impact on program and class design.</span></span> <span data-ttu-id="d6427-123">Это особенно важно, если задача легко решается путем преобразования данных, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="d6427-123">This is especially true when a problem lends itself to a data transformation solution as described above.</span></span>  
  
 <span data-ttu-id="d6427-124">Безусловно, это не относится к теме данного учебника, но следует отметить, что проекты, разработанные с учетом возможностей функциональных преобразований, чаще всего бывают сосредоточены на применении в качестве действующих факторов процессов, а не объектов, а полученное в результате решение чаще всего бывает реализовано как ряд крупномасштабных преобразований, а не как изменения состояний отдельных объектов.</span><span class="sxs-lookup"><span data-stu-id="d6427-124">Although they are beyond the scope of this tutorial, designs that are influenced by the functional transformation perspective tend to center on processes more than on objects as actors, and the resulting solution tends to be implemented as series of large-scale transformations, rather than individual object state changes.</span></span>  
  
 <span data-ttu-id="d6427-125">Следует также помнить, что C# поддерживает как императивный, так и функциональный подход, поэтому в приложении целесообразнее всего сочетать элементы обоих стилей программирования.</span><span class="sxs-lookup"><span data-stu-id="d6427-125">Again, remember that C# supports both imperative and functional approaches, so the best design for your application might incorporate elements of both.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6427-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d6427-126">See Also</span></span>  
 <span data-ttu-id="d6427-127">[Введение в чистые функциональные преобразования (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="d6427-127">[Introduction to Pure Functional Transformations (C#)](../../../../csharp/programming-guide/concepts/linq/introduction-to-pure-functional-transformations.md) </span></span>  
 <span data-ttu-id="d6427-128">[Функциональное преобразование XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md) </span><span class="sxs-lookup"><span data-stu-id="d6427-128">[Functional Transformation of XML (C#)](../../../../csharp/programming-guide/concepts/linq/functional-transformation-of-xml.md) </span></span>  
 [<span data-ttu-id="d6427-129">Рефакторинг в чистые функции (C#)</span><span class="sxs-lookup"><span data-stu-id="d6427-129">Refactoring Into Pure Functions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/refactoring-into-pure-functions.md)

