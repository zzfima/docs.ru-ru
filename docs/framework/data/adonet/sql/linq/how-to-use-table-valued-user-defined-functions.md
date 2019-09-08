---
title: Практическое руководство. Как применять определяемые пользователем возвращающие табличное значение функции
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a4ae2b4-3290-4aa1-bc95-fc70c51b54cf
ms.openlocfilehash: 31797ae7d0fe23227cc4af733fbceac5d474f779
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781447"
---
# <a name="how-to-use-table-valued-user-defined-functions"></a>Практическое руководство. Как применять определяемые пользователем возвращающие табличное значение функции
Табличная функция возвращает один набор строк (в отличие от хранимых процедур, которые могут возвращать несколько результирующих форм). Поскольку типом возвращаемого значения табличной функции является `Table`, эту функцию можно использовать в SQL там, где будет выполняться работа с таблицей. Кроме того, табличную функцию можно считать аналогом таблицы.  
  
## <a name="example"></a>Пример  
 Следующая функция SQL явно указывает возвращаемое значение: `TABLE`. Поэтому структура возвращаемого набора строк является неявно определенной.  
  
```  
CREATE FUNCTION ProductsCostingMoreThan(@cost money)  
RETURNS TABLE  
AS  
RETURN  
    SELECT ProductID, UnitPrice  
    FROM Products  
    WHERE UnitPrice > @cost  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет функцию следующим образом.  
  
 [!code-csharp[DLinqUDFS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/northwind-tfunc.cs#1)]
 [!code-vb[DLinqUDFS#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/northwind-tfunc.vb#1)]  
  
## <a name="example"></a>Пример  
 В следующем коде SQL показана возможность соединения с таблицей, возвращаемой функцией, и, в противном случае, обработать ее как любую другую таблицу.  
  
```  
SELECT p2.ProductName, p1.UnitPrice  
FROM dbo.ProductsCostingMoreThan(80.50)  
AS p1 INNER JOIN Products AS p2 ON p1.ProductID = p2.ProductID  
```  
  
 В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] запрос должен быть преобразован следующим образом.  
  
 [!code-csharp[DLinqUDFS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#2)]
 [!code-vb[DLinqUDFS#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Определяемые пользователем функции](user-defined-functions.md)
