---
title: Практическое руководство. Как возвращать наборы строк
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
ms.openlocfilehash: b853a6f2175009cbcbc01c14a6732b98e37e1a7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "72003059"
---
# <a name="how-to-return-rowsets"></a><span data-ttu-id="7dd8f-102">Практическое руководство. Как возвращать наборы строк</span><span class="sxs-lookup"><span data-stu-id="7dd8f-102">How to: Return Rowsets</span></span>
<span data-ttu-id="7dd8f-103">В данном примере показано возвращение набора строк из базы данных и включение входного параметра в результаты фильтрации.</span><span class="sxs-lookup"><span data-stu-id="7dd8f-103">This example returns a rowset from the database, and includes an input parameter to filter the result.</span></span>  
  
 <span data-ttu-id="7dd8f-104">При выполнении хранимой процедуры, возвращающей набор строк, используется *результирующий* класс, хранящий возвращаемые результаты из хранимой процедуры.</span><span class="sxs-lookup"><span data-stu-id="7dd8f-104">When you execute a stored procedure that returns a rowset, you use a *result* class that stores the returns from the stored procedure.</span></span> <span data-ttu-id="7dd8f-105">Дополнительные сведения см. в разделе [анализ исходного кода LINQ to SQL](analyzing-linq-to-sql-source-code.md).</span><span class="sxs-lookup"><span data-stu-id="7dd8f-105">For more information, see [Analyzing LINQ to SQL Source Code](analyzing-linq-to-sql-source-code.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dd8f-106">Пример</span><span class="sxs-lookup"><span data-stu-id="7dd8f-106">Example</span></span>  
 <span data-ttu-id="7dd8f-107">В следующем примере представлена хранимая процедура, которая возвращает строки клиентов и использует входной параметр для возврата только тех строк, в которых "Лондон" указан как город клиентов.</span><span class="sxs-lookup"><span data-stu-id="7dd8f-107">The following example represents a stored procedure that returns rows of customers and uses an input parameter to return only those rows that list "London" as the customer city.</span></span> <span data-ttu-id="7dd8f-108">В примере предполагается использование перечислимого класса `CustomersByCityResult`.</span><span class="sxs-lookup"><span data-stu-id="7dd8f-108">The example assumes an enumerable `CustomersByCityResult` class.</span></span>  
  
```sql  
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
  
## <a name="see-also"></a><span data-ttu-id="7dd8f-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7dd8f-109">See also</span></span>

- [<span data-ttu-id="7dd8f-110">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="7dd8f-110">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="7dd8f-111">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="7dd8f-111">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
