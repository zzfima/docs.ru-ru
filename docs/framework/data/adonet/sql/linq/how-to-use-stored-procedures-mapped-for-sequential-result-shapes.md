---
title: Как выполнить использовать хранимые процедуры, сопоставленные с последовательными результирующими формами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: 296870029d2329640466b3a540e9057738173aa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495660"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a>Как выполнить использовать хранимые процедуры, сопоставленные с последовательными результирующими формами
Этот тип хранимых процедур может создавать несколько результирующих форм, но всегда известно, в каком порядке возвращаются результаты. Этот сценарий противоположен сценарию, в котором порядок возвращения результатов не известен. Дополнительные сведения см. в разделе [Как Использовать хранимые процедуры, сопоставленные с несколькими результирующими формами](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).  
  
## <a name="example"></a>Пример  
 Ниже представлен код T-SQL для хранимой процедуры, которая последовательно возвращает несколько результирующих наборов.  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a>Пример  
 Для выполнения этой хранимой процедуры следует использовать код, который выглядит следующим образом:  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a>См. также
- [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
