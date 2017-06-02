---
title: "Сопоставления типов данных ODBC | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 43c35d32-831d-480f-a150-78f7e869d17f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Сопоставления типов данных ODBC
В приведенной ниже таблице показаны выводимые типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для типов данных поставщика данных .NET Framework для ODBC \(<xref:System.Data.Odbc>\).  Приведены также типизированные методы доступа для <xref:System.Data.Odbc.OdbcDataReader>.  
  
|Тип ODBC|Тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|Типизированный метод доступа [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|  
|--------------|---------------------------------------------------------------------|----------------------------------------------------------------------------------------------|  
|SQL\_BIGINT|Int64|GetInt64\(\)|  
|SQL\_BINARY|Byte\[\]|GetBytes\(\)|  
|SQL\_BIT|Boolean|GetBoolean\(\)|  
|SQL\_CHAR|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_DECIMAL|Десятичное число|GetDecimal\(\)|  
|SQL\_DOUBLE|Double|GetDouble\(\)|  
|SQL\_GUID|Guid|GetGuid\(\)|  
|SQL\_INTEGER|Int32|GetInt32\(\)|  
|SQL\_LONG\_VARCHAR|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_LONGVARBINARY|Byte\[\]|GetBytes\(\)|  
|SQL\_NUMERIC|Десятичное число|GetDecimal\(\)|  
|SQL\_REAL|Single|GetFloat\(\)|  
|SQL\_SMALLINT|Int16|GetInt16\(\)|  
|SQL\_TINYINT|Byte|GetByte\(\)|  
|SQL\_TYPE\_TIMES|DateTime|GetDateTime\(\)|  
|SQL\_TYPE\_TIMESTAMP|DateTime|GetDateTime\(\)|  
|SQL\_VARBINARY|Byte\[\]|GetBytes\(\)|  
|SQL\_WCHAR|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_WLONGVARCHAR|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
|SQL\_WVARCHAR|Строковое<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|  
  
## См. также  
 [Получение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)