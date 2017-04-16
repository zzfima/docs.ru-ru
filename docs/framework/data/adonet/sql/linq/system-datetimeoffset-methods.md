---
title: "Методы System.DateTimeOffset | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Методы System.DateTimeOffset
После их сопоставления в модели объектов или внешнем файле сопоставления LINQ to SQL позволяет использовать большинство методов, операторов и свойств <xref:System.DateTimeOffset?displayProperty=fullName> внутри запросов LINQ to SQL.  
  
 Не поддерживаются только те методы, которые унаследованы от <xref:System.Object?displayProperty=fullName> и не имеют смысла в контексте запросов LINQ to SQL, например `Finalize`, `GetHashCode`, `GetType` и `MemberwiseClone`.  Эти методы не поддерживаются, поскольку LINQ to SQL не может перевести их для выполнения в SQL Server.  
  
> [!NOTE]
>  Для структуры среды CLR <xref:System.DateTimeOffset?displayProperty=fullName> и для обеспечения возможности ее сопоставления столбцу SQL `DATETIMEOFFSET` с помощью LINQ to SQL необходима платформа .NET Framework 3.5 с пакетом обновления 1 \(SP1\) или выше.  Столбец SQL типа `DATETIMEOFFSET` доступен только в версиях Microsoft SQL Server 2008 и выше.  
  
## Методы даты и времени класса SQLMethods  
 Помимо методов, содержащихся в структуре <xref:System.DateTimeOffset>, LINQ to SQL поддерживает методы для работы с датой и временем из класса <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=fullName>, перечисленные в следующей таблице.  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## См. также  
 [Основные понятия о запросах](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)   
 [Создание модели объектов](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)   
 [Сопоставление типов SQL и CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)