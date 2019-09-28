---
title: Практическое руководство. Как использовать хранимые процедуры, которые принимают параметры
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: c2b657f704d072b987578be5520a58d007ecac37
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353016"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a>Практическое руководство. Как использовать хранимые процедуры, которые принимают параметры
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет выходные параметры с параметрами, передаваемыми по ссылке, и для типов значений объявляет, что параметры могут принимать значение NULL.  
  
 Пример использования входного параметра в запросе, возвращающем набор строк, см. в разделе [How to: Возвращает наборы строк @ no__t-0.  
  
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

- [Хранимые процедуры](stored-procedures.md)
- [Загрузка примеров баз данных](downloading-sample-databases.md)
- [Использование типов значений, допускающих значения NULL](../../../../../csharp/programming-guide/nullable-types/using-nullable-types.md)
- [Типы значений, допускающие значение NULL](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
