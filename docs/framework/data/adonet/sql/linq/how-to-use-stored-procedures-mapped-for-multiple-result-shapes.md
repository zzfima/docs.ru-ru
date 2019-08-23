---
title: Практическое руководство. Как использовать хранимые процедуры, сопоставленные с несколькими результирующими формами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 22614be8e53d975c4efdf7004f41906c58639c61
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938694"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a>Практическое руководство. Как использовать хранимые процедуры, сопоставленные с несколькими результирующими формами
Если хранимая процедура возвращает несколько результирующих форм, тип возвращаемых данных не может быть строго типизированным в соответствии с отдельной формой проекции. Хотя [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] может формировать все возможные типы проекций, он не может понять порядок, в котором они будут возвращены.  
  
 Этот сценарий противоположен сценарию использования хранимых процедур, которые последовательно возвращают несколько результирующих форм. Дополнительные сведения см. в разделе [Практическое руководство. Используйте хранимые процедуры, сопоставленные](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)с последовательной фигурой результата.  
  
 Чтобы указать набор типов, которые могут возвращать хранимые процедуры, возвращающие несколько типов результатов, к этим процедурам применяется атрибут <xref:System.Data.Linq.Mapping.ResultTypeAttribute>.  
  
## <a name="example"></a>Пример  
 В следующем примере SQL-кода результирующая форма зависит от входных данных (`shape =1` или `shape = 2`). Какая проекция будет возвращена первой, неизвестно.  
  
```  
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a>Пример  
 Для выполнения этой хранимой процедуры следует использовать код, который выглядит следующим образом:  
  
> [!NOTE]
> Необходимо использовать шаблон <xref:System.Data.Linq.IMultipleResults.GetResult%2A> для получения перечислителя правильного типа на основе сведений о хранимой процедуре.  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>См. также

- [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
