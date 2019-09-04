---
title: Примеры синтаксиса запросов на основе методов. Операторы элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 9a057cd80b3dc110626d1a9a850ee7c9704b33b4
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250260"
---
# <a name="method-based-query-syntax-examples-element-operators"></a>Примеры синтаксиса запросов на основе методов. Операторы элементов
В примерах этого раздела показано, как использовать <xref:System.Linq.Enumerable.First%2A> метод для запроса [модели AdventureWorks Sales](https://archive.codeplex.com/?p=msftdbprodsamples) с помощью синтаксиса запросов на основе методов. Модель AdventureWorks Sales, которая используется в этих примерах, состоит из таблиц Contact, Address, Product, SalesOrderHeader и SalesOrderDetail образца базы данных AdventureWorks.  
  
 В примере в этом разделе используются следующие `using` / `Imports` инструкции:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a>Первая  
  
### <a name="example"></a>Пример  
 В следующем примере <xref:System.Linq.Enumerable.First%2A> метод используется для поиска первого адреса электронной почты, который начинается с "Кэролайн".  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a>См. также

- [Запросы в LINQ to Entities](queries-in-linq-to-entities.md)
