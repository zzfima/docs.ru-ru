---
title: Практическое руководство. Использование хранимых процедур, принимающих параметры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: d1c9337f59b8cf218b9d2ab8fe4cf21afd2da689
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a>Практическое руководство. Использование хранимых процедур, принимающих параметры
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет выходные параметры с параметрами, передаваемыми по ссылке, и для типов значений объявляет, что параметры могут принимать значение NULL.  
  
 Пример демонстрирует использование входного параметра в запросе, который возвращает набор строк, см. в разделе [как: возвращают наборы строк](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).  
  
## <a name="example"></a>Пример  
 В следующем примере передается один входной параметр (код клиента) и возвращается один выходной параметр (общий объем продаж по этому клиенту).  
  
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
  
## <a name="example"></a>Пример  
 Эту хранимую процедуру можно вызвать следующим образом:  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>См. также  
 [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)  
 [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [Использование допускающих значение NULL типов](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)  
 [Типы значений, допускающие значение NULL](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
