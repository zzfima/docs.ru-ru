---
title: "Неподдерживаемые функции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e480cfb5-697e-42c8-bed5-9264c945c4f9
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Неподдерживаемые функции
В LINQ to SQL следующие функции SQL недоступны путем преобразования существующих конструкций среды CLR и .NET Framework.  
  
-   `STDDEV`  
  
-   `LIKE`  
  
     Хотя функция `LIKE` не поддерживается прямым преобразованием, аналогичная функция существует в классе <xref:System.Data.Linq.SqlClient.SqlMethods>.  Для получения дополнительной информации см. [M:System.Data.Linq.SqlClient.SqlMethods.Like\(System.String,System.String](assetId:///M:System.Data.Linq.SqlClient.SqlMethods.Like(System.String,System.String?qualifyHint=True&autoUpgrade=True).  
  
-   `DATEDIFF`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `DATEDIFF`.  Аналогичная функция существует в классе [SqlMethods](assetId:///T:System.Data.Linq.SqlClient.SqlMethods?qualifyHint=False&autoUpgrade=True).  
  
-   `ROUND`  
  
     В LINQ to SQL реализована ограниченная поддержка функции `ROUND`.  Для получения дополнительной информации см. [Методы System.Math](../Topic/System.Math%20Methods.md).  
  
## См. также  
 [Типы данных и функции](../Topic/Data%20Types%20and%20Functions.md)