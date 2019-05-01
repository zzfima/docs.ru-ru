---
title: Практическое руководство. Как использовать хранимые процедуры, которые принимают параметры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: 8dd463c895efcddfe288fe1dc8571981872d9d80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033617"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a>Практическое руководство. Как использовать хранимые процедуры, которые принимают параметры
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет выходные параметры с параметрами, передаваемыми по ссылке, и для типов значений объявляет, что параметры могут принимать значение NULL.  
  
 Пример демонстрирует использование входного параметра в запросе, который возвращает набор строк, см. в разделе [как: Возврат наборов строк](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).  
  
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

- [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [Загрузка примеров баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Использование допускающих значение NULL типов](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)
- [Типы значений, допускающие значение NULL](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
