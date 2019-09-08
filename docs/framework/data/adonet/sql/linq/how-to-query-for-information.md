---
title: Практическое руководство. Как обращаться с запросами о сведениях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: ed32bbe7d27357cbed7d77dd235b698a65c0e29e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793535"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="982b8-102">Практическое руководство. Как обращаться с запросами о сведениях</span><span class="sxs-lookup"><span data-stu-id="982b8-102">How to: Query for Information</span></span>
<span data-ttu-id="982b8-103">Для запросов в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] используется тот же синтаксис, что и для запросов [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="982b8-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="982b8-104">Единственное отличие заключается в том, что объекты, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] на которые имеются ссылки в запросах, сопоставляются с элементами в базе данных.</span><span class="sxs-lookup"><span data-stu-id="982b8-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="982b8-105">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="982b8-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="982b8-106">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки.</span><span class="sxs-lookup"><span data-stu-id="982b8-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="982b8-107">Некоторым запросам [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)], возможно, требуется уделить особое внимание в приложениях [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="982b8-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="982b8-108">Дополнительные сведения см. в разделе [Основные понятия запросов](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="982b8-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="982b8-109">Пример</span><span class="sxs-lookup"><span data-stu-id="982b8-109">Example</span></span>  
 <span data-ttu-id="982b8-110">Следующий запрос возвращает список клиентов из Лондона.</span><span class="sxs-lookup"><span data-stu-id="982b8-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="982b8-111">В этом примере используется таблица `Customers` из учебной базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="982b8-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="982b8-112">См. также</span><span class="sxs-lookup"><span data-stu-id="982b8-112">See also</span></span>

- [<span data-ttu-id="982b8-113">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="982b8-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="982b8-114">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="982b8-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="982b8-115">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="982b8-115">Querying the Database</span></span>](querying-the-database.md)
