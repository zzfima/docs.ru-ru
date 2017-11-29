---
title: "Сравнение удаленного и локальное выполнение"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 2b04ba6dde572aa0a8edddc8a2a30a8e11a3e79c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="remote-vs-local-execution"></a><span data-ttu-id="d8781-102">Сравнение удаленного и локальное выполнение</span><span class="sxs-lookup"><span data-stu-id="d8781-102">Remote vs. Local Execution</span></span>
<span data-ttu-id="d8781-103">Запросы можно выполнять либо удаленно (то есть ядро базы данных выполняет запрос в базе данных) или локально ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполняет запрос в локальном кэше).</span><span class="sxs-lookup"><span data-stu-id="d8781-103">You can decide to execute your queries either remotely (that is, the database engine executes the query against the database) or locally ([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] executes the query against a local cache).</span></span>  
  
## <a name="remote-execution"></a><span data-ttu-id="d8781-104">Удаленное выполнение</span><span class="sxs-lookup"><span data-stu-id="d8781-104">Remote Execution</span></span>  
 <span data-ttu-id="d8781-105">Рассмотрим следующий запрос:</span><span class="sxs-lookup"><span data-stu-id="d8781-105">Consider the following query:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 <span data-ttu-id="d8781-106">Если база данных содержит тысячи строк заказов, для обработки небольшого подмножества совсем не обязательно извлекать все строки.</span><span class="sxs-lookup"><span data-stu-id="d8781-106">If your database has thousands of rows of orders, you do not want to retrieve them all to process a small subset.</span></span> <span data-ttu-id="d8781-107">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] класс <xref:System.Data.Linq.EntitySet%601> реализует интерфейс <xref:System.Linq.IQueryable>.</span><span class="sxs-lookup"><span data-stu-id="d8781-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Data.Linq.EntitySet%601> class implements the <xref:System.Linq.IQueryable> interface.</span></span> <span data-ttu-id="d8781-108">Этот метод гарантирует удаленное выполнение подобных запросов.</span><span class="sxs-lookup"><span data-stu-id="d8781-108">This approach makes sure that such queries can be executed remotely.</span></span> <span data-ttu-id="d8781-109">Благодаря этому методу пользователь получает два существенных преимущества.</span><span class="sxs-lookup"><span data-stu-id="d8781-109">Two major benefits flow from this technique:</span></span>  
  
-   <span data-ttu-id="d8781-110">Извлекаются только необходимые данные.</span><span class="sxs-lookup"><span data-stu-id="d8781-110">Unnecessary data is not retrieved.</span></span>  
  
-   <span data-ttu-id="d8781-111">Запросы, выполняемые ядром базы данных зачастую более эффективны благодаря индексам базы данных.</span><span class="sxs-lookup"><span data-stu-id="d8781-111">A query executed by the database engine is often more efficient because of the database indexes.</span></span>  
  
## <a name="local-execution"></a><span data-ttu-id="d8781-112">локальное выполнение</span><span class="sxs-lookup"><span data-stu-id="d8781-112">Local Execution</span></span>  
 <span data-ttu-id="d8781-113">В других случаях бывает необходимо иметь полный набор связанных записей в локальном кэше.</span><span class="sxs-lookup"><span data-stu-id="d8781-113">In other situations, you might want to have the complete set of related entities in the local cache.</span></span> <span data-ttu-id="d8781-114">Для этой цели класс <xref:System.Data.Linq.EntitySet%601> предоставляет метод <xref:System.Data.Linq.EntitySet%601.Load%2A> для явной загрузки всех членов класса <xref:System.Data.Linq.EntitySet%601>.</span><span class="sxs-lookup"><span data-stu-id="d8781-114">For this purpose, <xref:System.Data.Linq.EntitySet%601> provides the <xref:System.Data.Linq.EntitySet%601.Load%2A> method to explicitly load all the members of the <xref:System.Data.Linq.EntitySet%601>.</span></span>  
  
 <span data-ttu-id="d8781-115">Если класс <xref:System.Data.Linq.EntitySet%601> уже загружен, последующие запросы выполняются локально.</span><span class="sxs-lookup"><span data-stu-id="d8781-115">If an <xref:System.Data.Linq.EntitySet%601> is already loaded, subsequent queries are executed locally.</span></span> <span data-ttu-id="d8781-116">Этот метод полезен с двух точек зрения.</span><span class="sxs-lookup"><span data-stu-id="d8781-116">This approach helps in two ways:</span></span>  
  
-   <span data-ttu-id="d8781-117">Если полный набор необходимо использовать локально или несколько раз, можно избежать удаленных запросов и связанных с ними задержек.</span><span class="sxs-lookup"><span data-stu-id="d8781-117">If the complete set must be used locally or multiple times, you can avoid remote queries and associated latencies.</span></span>  
  
-   <span data-ttu-id="d8781-118">Сущность можно сериализовать как полную сущность.</span><span class="sxs-lookup"><span data-stu-id="d8781-118">The entity can be serialized as a complete entity.</span></span>  
  
 <span data-ttu-id="d8781-119">В следующем фрагменте кода показывается, как добиться локального выполнения.</span><span class="sxs-lookup"><span data-stu-id="d8781-119">The following code fragment illustrates how local execution can be obtained:</span></span>  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## <a name="comparison"></a><span data-ttu-id="d8781-120">Сравнение</span><span class="sxs-lookup"><span data-stu-id="d8781-120">Comparison</span></span>  
 <span data-ttu-id="d8781-121">Эти две возможности предоставляют мощное сочетание параметров: удаленное выполнение для больших коллекций и локальное выполнение для малых коллекций или в тех случаях, когда требуется вся коллекция.</span><span class="sxs-lookup"><span data-stu-id="d8781-121">These two capabilities provide a powerful combination of options: remote execution for large collections and local execution for small collections or where the complete collection is needed.</span></span> <span data-ttu-id="d8781-122">Удаленное выполнение реализуется с помощью интерфейса <xref:System.Linq.IQueryable>, а локальное выполнение - посредством хранящейся в памяти коллекции <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="d8781-122">You implement remote execution through <xref:System.Linq.IQueryable>, and local execution against an in-memory <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="d8781-123">Для принудительного выполнения локального (т. е <xref:System.Collections.Generic.IEnumerable%601>), в разделе [преобразование типа в универсальный интерфейс IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).</span><span class="sxs-lookup"><span data-stu-id="d8781-123">To force local execution (that is, <xref:System.Collections.Generic.IEnumerable%601>), see [Convert a Type to a Generic IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).</span></span>  
  
### <a name="queries-against-unordered-sets"></a><span data-ttu-id="d8781-124">Запросы к неупорядоченным наборам</span><span class="sxs-lookup"><span data-stu-id="d8781-124">Queries Against Unordered Sets</span></span>  
 <span data-ttu-id="d8781-125">Обратите внимание на важное отличие между локальной коллекцией, которая реализует <xref:System.Collections.Generic.List%601> и коллекцией, предоставляющей удаленное выполнение запросов к *неупорядоченных наборов* в реляционной базе данных.</span><span class="sxs-lookup"><span data-stu-id="d8781-125">Note the important difference between a local collection that implements <xref:System.Collections.Generic.List%601> and a collection that provides remote queries executed against *unordered sets* in a relational database.</span></span> <span data-ttu-id="d8781-126">Для методов <xref:System.Collections.Generic.List%601>, например при использовании значений индексов, требуется семантика списка, которая, как правило, не реализуется посредством удаленного запроса к неупорядоченному набору.</span><span class="sxs-lookup"><span data-stu-id="d8781-126"><xref:System.Collections.Generic.List%601> methods such as those that use index values require list semantics, which typically cannot be obtained through a remote query against an unordered set.</span></span> <span data-ttu-id="d8781-127">По этой причине подобные методы неявно загружают класс <xref:System.Data.Linq.EntitySet%601>, чтобы получить возможность локального выполнения.</span><span class="sxs-lookup"><span data-stu-id="d8781-127">For this reason, such methods implicitly load the <xref:System.Data.Linq.EntitySet%601> to allow local execution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8781-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d8781-128">See Also</span></span>  
 [<span data-ttu-id="d8781-129">Основные принципы запросов</span><span class="sxs-lookup"><span data-stu-id="d8781-129">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
