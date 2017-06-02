---
title: "Как использовать хранимые процедуры для возвращения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 725718f5-da29-4841-9f53-aafef64ba977
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как использовать хранимые процедуры для возвращения
В данном примере показано возвращение набора строк из базы данных и включение входного параметра в результаты фильтрации.  
  
 При выполнении хранимой процедуры, возвращающей набор строк, используется класс *результатов*, в котором хранятся возвращенные значения хранимой процедуры.  Для получения дополнительной информации см. [Анализ исходного кода LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/analyzing-linq-to-sql-source-code.md).  
  
## Пример  
 В следующем примере представлена хранимая процедура, которая возвращает строки клиентов и использует входной параметр для возврата только тех строк, в которых "Лондон" указан как город клиентов.  В примере предполагается использование перечислимого класса `CustomersByCityResult`.  
  
```  
CREATE PROCEDURE [dbo].[Customers By City]  
    (@param1 NVARCHAR(20))  
AS  
BEGIN  
    -- SET NOCOUNT ON added to prevent extra result sets from  
    -- interfering with SELECT statements.  
    SET NOCOUNT ON;  
    SELECT CustomerID, ContactName, CompanyName, City from Customers  
        as c where c.City=@param1  
END  
```  
  
 [!code-csharp[DLinqSprox#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#1)]
 [!code-vb[DLinqSprox#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#1)]  
  
## См. также  
 [Хранимые процедуры](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)   
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)