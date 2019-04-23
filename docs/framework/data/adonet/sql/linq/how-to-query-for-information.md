---
title: Практическое руководство. Как обращаться с запросами о сведениях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: aedf89f1e570b34d31050fabb91842cefe351488
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162846"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="55491-102">Практическое руководство. Как обращаться с запросами о сведениях</span><span class="sxs-lookup"><span data-stu-id="55491-102">How to: Query for Information</span></span>
<span data-ttu-id="55491-103">Для запросов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] используется тот же синтаксис, что и для запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55491-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="55491-104">Единственное отличие заключается в том, что ссылки на объекты в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запросы, сопоставляются с элементами базы данных.</span><span class="sxs-lookup"><span data-stu-id="55491-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="55491-105">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="55491-105">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="55491-106">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки.</span><span class="sxs-lookup"><span data-stu-id="55491-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="55491-107">Некоторым запросам [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], возможно, требуется уделить особое внимание в приложениях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="55491-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="55491-108">Дополнительные сведения см. в разделе [основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="55491-108">For more information, see [Query Concepts](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="55491-109">Пример</span><span class="sxs-lookup"><span data-stu-id="55491-109">Example</span></span>  
 <span data-ttu-id="55491-110">Следующий запрос возвращает список клиентов из Лондона.</span><span class="sxs-lookup"><span data-stu-id="55491-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="55491-111">В этом примере используется таблица `Customers` из учебной базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="55491-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="55491-112">См. также</span><span class="sxs-lookup"><span data-stu-id="55491-112">See also</span></span>

- [<span data-ttu-id="55491-113">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="55491-113">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [<span data-ttu-id="55491-114">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="55491-114">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="55491-115">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="55491-115">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
