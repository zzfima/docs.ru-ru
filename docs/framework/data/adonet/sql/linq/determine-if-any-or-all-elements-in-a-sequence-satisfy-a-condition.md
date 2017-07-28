---
title: "Как определить, выполняется условие для одного или для всех элементов последовательности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 339ec145-826c-46d2-8cf2-3acd252cd072
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как определить, выполняется условие для одного или для всех элементов последовательности
Оператор <xref:System.Linq.Enumerable.All%2A> возвращает значение `true`, если все элементы в последовательности удовлетворяют указанному условию.  
  
 Оператор <xref:System.Linq.Queryable.Any%2A> возвращает значение `true`, если какой\-либо элемент в коллекции удовлетворяет указанному условию.  
  
## Пример  
 В следующем примере возвращается последовательность клиентов, сделавших хотя бы один заказ.  Если заданный `Customer` имеет `Order`, предложение `Where`\/`where` получает значение `true`.  
  
 [!code-csharp[DLinqQueryExamples#37](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#37)]
 [!code-vb[DLinqQueryExamples#37](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37)]  
  
## Пример  
 Следующий код Visual Basic определяет список клиентов, не оформивших заказы, и гарантирует наличие контактного имени для каждого клиента в этом списке.  
  
 [!code-vb[DLinqQueryExamples#37v](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#37v)]  
  
## Пример  
 В следующем примере C\# возвращается последовательность клиентов, `ShipCity` в заказах которых начинается с буквы "С".  Кроме того, в полученном результате будут указаны клиенты, не сделавшие ни одного заказа.  \(Для пустой последовательности оператор <xref:System.Linq.Queryable.All%2A> намеренно возвращает значение `true`.\) Клиенты, не имеющие заказов, удаляются из вывода на консоли с помощью оператора `Count`.  
  
 [!code-csharp[DLinqQueryExamples#38](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#38)]  
  
## См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)