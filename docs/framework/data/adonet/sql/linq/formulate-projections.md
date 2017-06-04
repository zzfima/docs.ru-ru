---
title: "Формирование проекций | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 745742df-0eda-479b-83f8-29bd8a80db96
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Формирование проекций
В следующем примере показано сочетание оператора `select` в C\# и оператора `Select` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] с другими возможностями для создания проекций запросов.  
  
## Пример  
 В следующем примере предложение `Select` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложение `select` в C\#\) используется для возвращения последовательности контактных имен для `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#57](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#57)]
 [!code-vb[DLinqQueryExamples#57](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#57)]  
  
## Пример  
 В следующем примере предложение `Select` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложение `select` в C\#\) и *анонимные типы* используются для возвращения последовательности контактных имен и телефонных номеров для `Customers`.  
  
 [!code-csharp[DLinqQueryExamples#58](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#58)]
 [!code-vb[DLinqQueryExamples#58](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#58)]  
  
## Пример  
 В следующем примере предложение `Select` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложение `select` в C\#\) и *анонимные типы* используются для возвращения последовательности контактных имен и телефонных номеров для сотрудников.  В результирующей последовательности поля `FirstName` и `LastName` объединены в одно поле \(`Name`\), а поле `HomePhone` переименовано в `Phone`.  
  
 [!code-csharp[DLinqQueryExamples#59](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#59)]
 [!code-vb[DLinqQueryExamples#59](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#59)]  
  
## Пример  
 В следующем примере предложение `Select` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложение `select` в C\#\) и *анонимные типы* используются для возвращения последовательности всех `ProductID` и вычисляемого значения с именем `HalfPrice`.  В качестве значения устанавливается `UnitPrice`, разделенная на 2.  
  
 [!code-csharp[DLinqQueryExamples#60](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#60)]
 [!code-vb[DLinqQueryExamples#60](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#60)]  
  
## Пример  
 В следующем примере предложение `Select` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложение `select` в C\#\) и *условный оператор* используются для возвращения последовательности названия продукта и его доступности.  
  
 [!code-csharp[DLinqQueryExamples#61](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#61)]
 [!code-vb[DLinqQueryExamples#61](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#61)]  
  
## Пример  
 В следующем примере предложение `Select` [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложение `select` в C\#\) и *известный тип* \("Имя"\) используются для возвращения последовательности имен сотрудников.  
  
 [!code-csharp[DLinqQueryExamples#62](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#62)]
 [!code-vb[DLinqQueryExamples#62](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#62)]  
  
## Пример  
 В следующем примере предложения `Select` и `Where` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложения `select` и `where` в C\#\) используются для возвращения *отфильтрованной последовательности* контактных имен для клиентов в Лондоне.  
  
 [!code-csharp[DLinqQueryExamples#63](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#63)]
 [!code-vb[DLinqQueryExamples#63](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#63)]  
  
## Пример  
 В следующем примере предложение `Select` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] \(предложение `select` в C\#\) и *анонимные типы* используются для возвращения *сформированного подмножества* данных о клиентах.  
  
 [!code-csharp[DLinqQueryExamples#64](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#64)]
 [!code-vb[DLinqQueryExamples#64](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#64)]  
  
## Пример  
 В следующем примере вложенные запросы используется для возврата следующих результатов.  
  
-   Последовательность всех заказов и их соответствующие `OrderID`.  
  
-   Последовательность элементов, упорядоченных по наличию скидки.  
  
-   Количество сэкономленных средств при отсутствии расходов на доставку.  
  
 [!code-csharp[DLinqQueryExamples#65](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#65)]
 [!code-vb[DLinqQueryExamples#65](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#65)]  
  
## См. также  
 [Примеры запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)