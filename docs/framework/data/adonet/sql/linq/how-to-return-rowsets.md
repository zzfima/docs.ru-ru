---
title: Практическое руководство. Как возвращать наборы строк
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: 599ad6f722251003ab56547ce050cbd0e8da831d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168718"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="b6953-102">Практическое руководство. Как возвращать наборы строк</span><span class="sxs-lookup"><span data-stu-id="b6953-102">How to: Return Rowsets</span></span>
<span data-ttu-id="b6953-103">В данном примере показано возвращение набора строк из базы данных и включение входного параметра в результаты фильтрации.</span><span class="sxs-lookup"><span data-stu-id="b6953-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="b6953-104">При выполнении хранимой процедуры, возвращающей набор строк, используйте *результат* класс, который хранит возвращенные хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="b6953-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="b6953-105">Дополнительные сведения см. в разделе [анализ кода LINQ to SQL источника](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="b6953-105">For more information, see [Analyzing LINQ to SQL Source Code](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6953-106">Пример</span><span class="sxs-lookup"><span data-stu-id="b6953-106">Example</span></span>  
 <span data-ttu-id="b6953-107">В следующем примере представлена хранимая процедура, которая возвращает строки клиентов и использует входной параметр для возврата только тех строк, в которых "Лондон" указан как город клиентов.</span><span class="sxs-lookup"><span data-stu-id="b6953-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="b6953-108">В примере предполагается использование перечислимого класса `CustomersByCityResult`.</span><span class="sxs-lookup"><span data-stu-id="b6953-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b6953-109">См. также</span><span class="sxs-lookup"><span data-stu-id="b6953-109">See also</span></span>

- [<span data-ttu-id="b6953-110">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="b6953-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [<span data-ttu-id="b6953-111">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="b6953-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
