---
title: "Как использовать хранимые процедуры, принимающие параметры | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как использовать хранимые процедуры, принимающие параметры
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сопоставляет выходные параметры с параметрами, передаваемыми по ссылке, и для типов значений объявляет, что параметры могут принимать значение NULL.  
  
 Пример использования выходного параметра в запросе, который возвращает набор строк, см. в разделе [Как использовать хранимые процедуры для возвращения](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).  
  
## Пример  
 В следующем примере передается один входной параметр \(код клиента\) и возвращается один выходной параметр \(общий объем продаж по этому клиенту\).  
  
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
  
## Пример  
 Эту хранимую процедуру можно вызвать следующим образом:  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## См. также  
 [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)   
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Использование допускающих значение NULL типов](../Topic/Using%20Nullable%20Types%20\(C%23%20Programming%20Guide\).md)   
 [Типы значения, допускающие Null](../Topic/Nullable%20Value%20Types%20\(Visual%20Basic\).md)