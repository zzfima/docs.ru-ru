---
title: Практическое руководство. Запрос информации
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 3380b486da33a5dc083ed51f6705e666978df197
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634655"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="4eb4c-102">Практическое руководство. Запрос информации</span><span class="sxs-lookup"><span data-stu-id="4eb4c-102">How to: Query for Information</span></span>
<span data-ttu-id="4eb4c-103">Запросы в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] используют тот же синтаксис, что и запросы в LINQ.</span><span class="sxs-lookup"><span data-stu-id="4eb4c-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="4eb4c-104">Единственное отличие заключается в том, что объекты, упоминаемые в запросах [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], сопоставляются с элементами в базе данных.</span><span class="sxs-lookup"><span data-stu-id="4eb4c-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="4eb4c-105">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4eb4c-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="4eb4c-106">Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует написанные пользователем запросы в эквивалентные запросы SQL и отправляет их на сервер для обработки.</span><span class="sxs-lookup"><span data-stu-id="4eb4c-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="4eb4c-107">Некоторые функции запросов LINQ могут потребовать особого внимания в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] приложениях.</span><span class="sxs-lookup"><span data-stu-id="4eb4c-107">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="4eb4c-108">Дополнительные сведения см. в разделе [Основные понятия запросов](query-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="4eb4c-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4eb4c-109">Пример</span><span class="sxs-lookup"><span data-stu-id="4eb4c-109">Example</span></span>  
 <span data-ttu-id="4eb4c-110">Следующий запрос возвращает список клиентов из Лондона.</span><span class="sxs-lookup"><span data-stu-id="4eb4c-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="4eb4c-111">В этом примере используется таблица `Customers` из учебной базы данных "Northwind".</span><span class="sxs-lookup"><span data-stu-id="4eb4c-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4eb4c-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="4eb4c-112">See also</span></span>

- [<span data-ttu-id="4eb4c-113">Создание модели объектов</span><span class="sxs-lookup"><span data-stu-id="4eb4c-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="4eb4c-114">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="4eb4c-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="4eb4c-115">Запрос к базе данных</span><span class="sxs-lookup"><span data-stu-id="4eb4c-115">Querying the Database</span></span>](querying-the-database.md)
