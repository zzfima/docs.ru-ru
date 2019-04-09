---
title: Практическое руководство. Как использовать хранимые процедуры, которые принимают параметры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: 8dd463c895efcddfe288fe1dc8571981872d9d80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181770"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="718ed-102">Практическое руководство. Как использовать хранимые процедуры, которые принимают параметры</span><span class="sxs-lookup"><span data-stu-id="718ed-102">How to: Use Stored Procedures that Take Parameters</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="718ed-103">сопоставляет выходные параметры, чтобы ссылаться на параметры, а для типов значений объявляет, что параметры как допускающие значение NULL.</span><span class="sxs-lookup"><span data-stu-id="718ed-103">maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="718ed-104">Пример демонстрирует использование входного параметра в запросе, который возвращает набор строк, см. в разделе [как: Возврат наборов строк](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="718ed-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="718ed-105">Пример</span><span class="sxs-lookup"><span data-stu-id="718ed-105">Example</span></span>  
 <span data-ttu-id="718ed-106">В следующем примере передается один входной параметр (код клиента) и возвращается один выходной параметр (общий объем продаж по этому клиенту).</span><span class="sxs-lookup"><span data-stu-id="718ed-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```  
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="718ed-107">Пример</span><span class="sxs-lookup"><span data-stu-id="718ed-107">Example</span></span>  
 <span data-ttu-id="718ed-108">Эту хранимую процедуру можно вызвать следующим образом:</span><span class="sxs-lookup"><span data-stu-id="718ed-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="718ed-109">См. также</span><span class="sxs-lookup"><span data-stu-id="718ed-109">See also</span></span>

- [<span data-ttu-id="718ed-110">Хранимые процедуры</span><span class="sxs-lookup"><span data-stu-id="718ed-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [<span data-ttu-id="718ed-111">Загрузка примеров баз данных</span><span class="sxs-lookup"><span data-stu-id="718ed-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="718ed-112">Использование допускающих значение NULL типов</span><span class="sxs-lookup"><span data-stu-id="718ed-112">Using Nullable Types</span></span>](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="718ed-113">Типы значения, допускающие Null</span><span class="sxs-lookup"><span data-stu-id="718ed-113">Nullable Value Types</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
