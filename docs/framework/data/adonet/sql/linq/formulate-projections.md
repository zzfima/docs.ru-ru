---
title: "Формулировка проекций"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 67c196b5c693e36e45d4cad4fa75e08145dd699d
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="formulate-projections"></a>Формулировка проекций
В следующем примере показано сочетание оператора `select` в C# и оператора `Select` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] с другими возможностями для создания проекций запросов.  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) для возвращения последовательности контактных имен для `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *анонимные типы* для возвращения последовательности контактных имен и телефонных номеров для `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *анонимные типы* для возвращения последовательности имен и телефонных номеров для сотрудников. `FirstName` И `LastName` поля объединяются в одно поле (`Name`) и `HomePhone` присваивается имя `Phone` в результирующей последовательности.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *анонимные типы* для возвращения последовательности всех `ProductID`и вычисляемого значения с именем `HalfPrice`. В качестве значения устанавливается `UnitPrice`, разделенная на 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *условного оператора* для возвращения последовательности названия продукта и доступности продуктов.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] `Select` предложение (`select` предложение в C#) и *известного типа* (имя) для возвращения последовательности имен сотрудников.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Select` и `Where` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` и `where` в C#) для возврата *отфильтрованной последовательности* контактных имен для клиентов из Лондона.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## <a name="example"></a>Пример  
 В следующем примере используется `Select` предложения в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] (`select` предложение в C#) и *анонимные типы* для возврата *сформированного подмножества* данных о клиентах.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## <a name="example"></a>Пример  
 В следующем примере вложенные запросы используется для возврата следующих результатов.  
  
-   Последовательность всех заказов и их соответствующие `OrderID`.  
  
-   Последовательность элементов, упорядоченных по наличию скидки.  
  
-   Количество сэкономленных средств при отсутствии расходов на доставку.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## <a name="see-also"></a>См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
