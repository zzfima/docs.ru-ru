---
title: Практическое руководство. Как применять определяемые пользователем возвращающие табличное значение функции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: eedc2e9b997e91ed9fe0038f260aa475d23a0627
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033596"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a><span data-ttu-id="00ee9-102">Практическое руководство. Как применять определяемые пользователем возвращающие табличное значение функции</span><span class="sxs-lookup"><span data-stu-id="00ee9-102">How to: Use Table-Valued User-Defined Functions</span></span>
<span data-ttu-id="00ee9-103">Табличная функция возвращает один набор строк (в отличие от хранимых процедур, которые могут возвращать несколько результирующих форм).</span><span class="sxs-lookup"><span data-stu-id="00ee9-103">A table-valued function returns a single rowset (unlike stored procedures, which can return multiple result shapes).</span></span> <span data-ttu-id="00ee9-104">Поскольку типом возвращаемого значения табличной функции является `Table`, эту функцию можно использовать в SQL там, где будет выполняться работа с таблицей.</span><span class="sxs-lookup"><span data-stu-id="00ee9-104">Because the return type of a table-valued function is `Table`, you can use a table-valued function anywhere in SQL that you can use a table.</span></span> <span data-ttu-id="00ee9-105">Кроме того, табличную функцию можно считать аналогом таблицы.</span><span class="sxs-lookup"><span data-stu-id="00ee9-105">You can also treat the table-valued function just as you would a table.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00ee9-106">Пример</span><span class="sxs-lookup"><span data-stu-id="00ee9-106">Example</span></span>  
 <span data-ttu-id="00ee9-107">Следующая функция SQL явно указывает возвращаемое значение: `TABLE`.</span><span class="sxs-lookup"><span data-stu-id="00ee9-107">The following SQL function explicitly states that it returns a `TABLE`.</span></span> <span data-ttu-id="00ee9-108">Поэтому структура возвращаемого набора строк является неявно определенной.</span><span class="sxs-lookup"><span data-stu-id="00ee9-108">Therefore, the returned rowset structure is implicitly defined.</span></span>  
  
```  
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="00ee9-109">сопоставляет функцию следующим образом.</span><span class="sxs-lookup"><span data-stu-id="00ee9-109">maps the function as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="00ee9-110">Пример</span><span class="sxs-lookup"><span data-stu-id="00ee9-110">Example</span></span>  
 <span data-ttu-id="00ee9-111">В следующем коде SQL показана возможность соединения с таблицей, возвращаемой функцией, и, в противном случае, обработать ее как любую другую таблицу.</span><span class="sxs-lookup"><span data-stu-id="00ee9-111">The following SQL code shows that you can join to the table that the function returns and otherwise treat it as you would any other table:</span></span>  
  
```  
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 <span data-ttu-id="00ee9-112">В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запрос должен быть преобразован следующим образом.</span><span class="sxs-lookup"><span data-stu-id="00ee9-112">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the query would be rendered as follows:</span></span>  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="00ee9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="00ee9-113">See also</span></span>

- [<span data-ttu-id="00ee9-114">Определяемые пользователем функции</span><span class="sxs-lookup"><span data-stu-id="00ee9-114">User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/user-defined-functions.md)
