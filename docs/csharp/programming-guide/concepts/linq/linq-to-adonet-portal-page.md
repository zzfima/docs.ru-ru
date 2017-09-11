---
title: "LINQ to ADO.NET (Страница портала)"
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
ms.assetid: 6bd269b4-3509-4688-b672-836008704182
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
ms.openlocfilehash: d768d5796e5eb7ff4fed071d906c672b83b42d2b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-adonet-portal-page"></a><span data-ttu-id="1230e-102">LINQ to ADO.NET (Страница портала)</span><span class="sxs-lookup"><span data-stu-id="1230e-102">LINQ to ADO.NET (Portal Page)</span></span>
[!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)]<span data-ttu-id="1230e-103"> позволяет запрашивать любой перечисляемый объект [!INCLUDE[vstecado](~/includes/vstecado-md.md)] с помощью модели программирования [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1230e-103"> enables you to query over any enumerable object in [!INCLUDE[vstecado](~/includes/vstecado-md.md)] by using the [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] programming model.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1230e-104">Документация по [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] находится в разделе ADO.NET пакета SDK для .NET Framework: [LINQ и ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).</span><span class="sxs-lookup"><span data-stu-id="1230e-104">The [!INCLUDE[linq_adonet](~/includes/linq-adonet-md.md)] documentation is located in the ADO.NET section of the .NET Framework SDK: [LINQ and ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec).</span></span>  
  
 <span data-ttu-id="1230e-105">Существуют три отдельные технологии ADO.NET [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] и [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1230e-105">There are three separate ADO.NET [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] technologies: [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)], [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], and [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span></span> <span data-ttu-id="1230e-106">Технология [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] обеспечивает расширенные и оптимизированные запросы к <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] позволяет запрашивать непосредственно схемы базы данных [!INCLUDE[ssNoVersion](~/includes/ssnoversion-md.md)], а [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] — выполнять запросы к [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1230e-106">[!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)] provides richer, optimized querying over the <xref:System.Data.DataSet>, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] enables you to directly query [!INCLUDE[ssNoVersion](~/includes/ssnoversion-md.md)] database schemas, and [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)] allows you to query an [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)].</span></span>  
  
## <a name="linq-to-dataset"></a><span data-ttu-id="1230e-107">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="1230e-107">LINQ to DataSet</span></span>  
 <span data-ttu-id="1230e-108"><xref:System.Data.DataSet> является одним из наиболее широко используемых компонентов в [!INCLUDE[vstecado](~/includes/vstecado-md.md)] и представляет собой ключевой элемент в модели отсоединенного программирования, на которой построен [!INCLUDE[vstecado](~/includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1230e-108">The <xref:System.Data.DataSet> is one of the most widely used components in [!INCLUDE[vstecado](~/includes/vstecado-md.md)], and is a key element of the disconnected programming model that [!INCLUDE[vstecado](~/includes/vstecado-md.md)] is built on.</span></span> <span data-ttu-id="1230e-109">Несмотря на все это, объект <xref:System.Data.DataSet> имеет ограниченные возможности запросов.</span><span class="sxs-lookup"><span data-stu-id="1230e-109">Despite this prominence, however, the <xref:System.Data.DataSet> has limited query capabilities.</span></span>  
  
 [!INCLUDE[linq_dataset](~/includes/linq-dataset-md.md)]<span data-ttu-id="1230e-110"> позволяет использовать расширенные возможности запросов в <xref:System.Data.DataSet> с применением той же функциональности, которая доступна для многих других источников данных.</span><span class="sxs-lookup"><span data-stu-id="1230e-110"> enables you to build richer query capabilities into <xref:System.Data.DataSet> by using the same query functionality that is available for many other data sources.</span></span>  
  
 <span data-ttu-id="1230e-111">Дополнительные сведения см. в разделе [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="1230e-111">For more information, see [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).</span></span>  
  
## <a name="linq-to-sql"></a><span data-ttu-id="1230e-112">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1230e-112">LINQ to SQL</span></span>  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]<span data-ttu-id="1230e-113"> предоставляет инфраструктуру времени выполнения для управления реляционными данными в виде объектов.</span><span class="sxs-lookup"><span data-stu-id="1230e-113"> provides a run-time infrastructure for managing relational data as objects.</span></span> <span data-ttu-id="1230e-114">В [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] модель данных реляционной базы данных сопоставляется объектной модели, выраженной в языке программирования разработчика.</span><span class="sxs-lookup"><span data-stu-id="1230e-114">In [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="1230e-115">При выполнении приложения [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] преобразует интегрированные в язык запросы из объектной модели в SQL и отправляет их в базу данных для выполнения.</span><span class="sxs-lookup"><span data-stu-id="1230e-115">When you execute the application, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates language-integrated queries in the object model into SQL and sends them to the database for execution.</span></span> <span data-ttu-id="1230e-116">Когда база данных возвращает результаты, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] переводит их обратно в объекты, которыми можно управлять.</span><span class="sxs-lookup"><span data-stu-id="1230e-116">When the database returns the results, [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] translates them back into objects that you can manipulate.</span></span>  
  
 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]<span data-ttu-id="1230e-117"> включает поддержку хранимых процедур, определяемых пользователем функций в базе данных и наследования в объектной модели.</span><span class="sxs-lookup"><span data-stu-id="1230e-117"> includes support for stored procedures and user-defined functions in the database, and for inheritance in the object model.</span></span>  
  
 <span data-ttu-id="1230e-118">Дополнительные сведения см. в разделе [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).</span><span class="sxs-lookup"><span data-stu-id="1230e-118">For more information, see [LINQ to SQL](https://msdn.microsoft.com/library/bb386976).</span></span>  
  
## <a name="linq-to-entities"></a><span data-ttu-id="1230e-119">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="1230e-119">LINQ to Entities</span></span>  
 <span data-ttu-id="1230e-120">В модели [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)] реляционные данные представлены в виде объектов в среде .NET.</span><span class="sxs-lookup"><span data-stu-id="1230e-120">Through the [!INCLUDE[adonet_edm](~/includes/adonet-edm-md.md)], relational data is exposed as objects in the .NET environment.</span></span> <span data-ttu-id="1230e-121">Благодаря этому поддержка [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] эффективно реализуется на уровне объектов, что позволяет составлять запросы баз данных на языке, используемом для сборки бизнес-логики.</span><span class="sxs-lookup"><span data-stu-id="1230e-121">This makes the object layer an ideal target for [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] support, allowing developers to formulate queries against the database from the language used to build the business logic.</span></span> <span data-ttu-id="1230e-122">Эта функция называется [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1230e-122">This capability is known as [!INCLUDE[linq_entities](~/includes/linq-entities-md.md)].</span></span> <span data-ttu-id="1230e-123">Дополнительные сведения см. в разделе [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md).</span><span class="sxs-lookup"><span data-stu-id="1230e-123">See [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md) for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1230e-124">См. также</span><span class="sxs-lookup"><span data-stu-id="1230e-124">See Also</span></span>  
 <span data-ttu-id="1230e-125">[LINQ и ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec) </span><span class="sxs-lookup"><span data-stu-id="1230e-125">[LINQ and ADO.NET](http://msdn.microsoft.com/library/bf0c8f93-3ff7-49f3-8aed-f2b7ac938dec) </span></span>  
 [<span data-ttu-id="1230e-126">LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="1230e-126">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)

