---
title: Практическое руководство. Как вызывать встроенные определяемые пользователем функции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: 01ba9ab4359cbd124b2207c87d5dae904641911a
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002987"
---
# <a name="how-to-call-user-defined-functions-inline"></a><span data-ttu-id="a60a2-102">Практическое руководство. Как вызывать встроенные определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="a60a2-102">How to: Call User-Defined Functions Inline</span></span>
<span data-ttu-id="a60a2-103">Пользовательские функции можно вызывать из строки кода, однако функции, включенные в запрос, выполнение которого отложено, выполняются только одновременно с запросом.</span><span class="sxs-lookup"><span data-stu-id="a60a2-103">Although you can call user-defined functions inline, functions that are included in a query whose execution is deferred are not executed until the query is executed.</span></span> <span data-ttu-id="a60a2-104">Дополнительные сведения см. в разделе [Введение в запросы LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a60a2-104">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="a60a2-105">Если та же функция вызывается за пределами запроса, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает простой запрос из выражения вызова метода.</span><span class="sxs-lookup"><span data-stu-id="a60a2-105">When you call the same function outside a query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates a simple query from the method call expression.</span></span> <span data-ttu-id="a60a2-106">Ниже показан синтаксис SQL (параметр `@p0` привязан к передаваемой константе).</span><span class="sxs-lookup"><span data-stu-id="a60a2-106">The following is the SQL syntax (the parameter `@p0` is bound to the constant passed in):</span></span>  
  
```sql  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a60a2-107">создает следующий код:</span><span class="sxs-lookup"><span data-stu-id="a60a2-107">creates the following:</span></span>  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="a60a2-108">Пример</span><span class="sxs-lookup"><span data-stu-id="a60a2-108">Example</span></span>  
 <span data-ttu-id="a60a2-109">В следующем [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запросе можно увидеть встроенный вызов созданного определяемого пользователем метода функции `ReverseCustName`.</span><span class="sxs-lookup"><span data-stu-id="a60a2-109">In the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query, you can see an inline call to the generated user-defined function method `ReverseCustName`.</span></span> <span data-ttu-id="a60a2-110">Функция не выполняется немедленно, поскольку выполнение запроса отложено.</span><span class="sxs-lookup"><span data-stu-id="a60a2-110">The function is not executed immediately because query execution is deferred.</span></span> <span data-ttu-id="a60a2-111">Код SQL, созданный для этого запроса, преобразуется в вызов пользовательской функции в базе данных (см. код SQL, расположенный после запроса).</span><span class="sxs-lookup"><span data-stu-id="a60a2-111">The SQL built for this query translates to a call to the user-defined function in the database (see the SQL code following the query).</span></span>  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```sql  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a><span data-ttu-id="a60a2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a60a2-112">See also</span></span>

- [<span data-ttu-id="a60a2-113">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="a60a2-113">User-Defined Functions</span></span>](user-defined-functions.md)
