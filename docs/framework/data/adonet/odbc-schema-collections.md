---
title: "Коллекции схем ODBC | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Коллекции схем ODBC
В данном разделе рассматривается поддержка коллекций схем для драйверов ODBC для Microsoft SQL Server, Oracle и Microsoft Jet.  
  
## Драйвер ODBC для Microsoft SQL Server  
 Драйвер ODBC для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
-   Таблицы  
  
-   Indexes  
  
-   Столбцы  
  
-   Процедуры  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Представления  
  
### Tables и Views  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CAT|Строковое|  
|TABLE\_SCHEM|Строковое|  
|TABLE\_NAME|Строковое|  
|TABLE\_TYPE|Строковое|  
|REMARKS|Строковое|  
  
### Indexes  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CAT|Строковое|  
|TABLE\_SCHEM|Строковое|  
|TABLE\_NAME|Строковое|  
|NON\_UNIQUE|Int16|  
|INDEX\_QUALIFIER|Строковое|  
|INDEX\_NAME|Строковое|  
|TYPE|Int16|  
|ORDINAL\_POSITION|Int16|  
|COLUMN\_NAME|Строковое|  
|ASC\_OR\_DESC|Строковое|  
|CARDINATLITY|Int32|  
|PAGES|Int32|  
|FILTER\_CONDITION|Строковое|  
|SS\_TYPE\_SCHEMA|Строковое|  
|SS\_DATA\_TYPE|Byte|  
  
### Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CAT|Строковое|  
|TABLE\_SCHEM|Строковое|  
|TABLE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Строковое|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Строковое|  
|COLUMN\_DEF|Строковое|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|Строковое|  
|SS\_TYPE\_CATALOG|Строковое|  
|SS\_TYPE\_SCHEMA|Строковое|  
|SS\_DATA\_TYPE|Byte|  
  
### Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_CAT|Строковое|  
|PROCEDURE\_SCHEM|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|NUM\_INPUT\_PARAMS|Int32|  
|NUM\_OUTPUT\_PARAMS|Int32|  
|NUM\_RESULT\_SETS|Int32|  
|REMARKS|Строковое|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_CAT|Строковое|  
|PROCEDURE\_SCHEM|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Строковое|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Строковое|  
|COLUMN\_DEF|Строковое|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|Строковое|  
|SS\_TYPE\_CATALOG|Строковое|  
|SS\_TYPE\_SCHEMA|Строковое|  
|SS\_DATA\_TYPE|Byte|  
  
### ProcedureParameters  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_CAT|Строковое|  
|PROCEDURE\_SCHEM|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Строковое|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Строковое|  
|COLUMN\_DEF|Строковое|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|Строковое|  
|SS\_TYPE\_CATALOG|Строковое|  
|SS\_TYPE\_SCHEMA|Строковое|  
|SS\_DATA\_TYPE|Byte|  
  
## Драйвер ODBC для Oracle \(Майкрософт\)  
 Драйвер Microsoft SQL Server ODBC для Oracle поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
-   Таблицы  
  
-   Столбцы  
  
-   Процедуры  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Представления  
  
-   Indexes  
  
### Tables и Views  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_QUALIFIER|Строковое|  
|TABLE\_OWNER|Строковое|  
|TABLE\_NAME|Строковое|  
|TABLE\_TYPE|Строковое|  
|REMARKS|Строковое|  
  
### Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_QUALIFIER|Строковое|  
|TABLE\_OWNER|Строковое|  
|TABLE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Строковое|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Строковое|  
|ORDINAL\_POSITION|Int32|  
  
### Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_QUALIFIER|Строковое|  
|PROCEDURE\_OWNER|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|NUM\_INPUT\_PARAMS|Int16|  
|NUM\_OUTPUT\_PARAMS|Int16|  
|NUM\_RESULT\_SETS|Int16|  
|REMARKS|Строковое|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_QUALIFIER|Строковое|  
|PROCEDURE\_OWNER|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Строковое|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Строковое|  
|OVERLOAD|Int32|  
|ORDINAL\_POSITION|Int32|  
  
## Драйвер ODBC для Jet \(Майкрософт\)  
 Драйвер ODBC для Jet \(Майкрософт\) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
-   Таблицы  
  
-   Indexes  
  
-   Столбцы  
  
-   Процедуры  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Представления  
  
### Tables и Views  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_QUALIFIER|Строковое|  
|TABLE\_OWNER|Строковое|  
|TABLE\_NAME|Строковое|  
|TABLE\_TYPE|Строковое|  
|REMARKS|Строковое|  
  
### Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_QUALIFIER|Строковое|  
|TABLE\_OWNER|Строковое|  
|TABLE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Строковое|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Строковое|  
|ORDINAL\_POSITION|Int32|  
  
### Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_QUALIFIER|Строковое|  
|PROCEDURE\_OWNER|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|NUM\_INPUT\_PARAMS|Int16|  
|NUM\_OUTPUT\_PARAMS|Int16|  
|NUM\_RESULT\_SETS|Int16|  
|REMARKS|Строковое|  
|PROCEDURE\_TYPE|Int16|  
  
### ProcedureColumns  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_QUALIFIER|Строковое|  
|PROCEDURE\_OWNER|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Строковое|  
|PRECISION|Int32|  
|LENGTH|Int32|  
|SCALE|Int16|  
|RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Строковое|  
|OVERLOAD|Int32|  
|ORDINAL\_POSITION|Int32|  
  
### ProcedureParameters  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_CAT|Строковое|  
|PROCEDURE\_SCHEM|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_TYPE|Int16|  
|DATA\_TYPE|Int16|  
|TYPE\_NAME|Строковое|  
|COLUMN\_SIZE|Int32|  
|BUFFER\_LENGTH|Int32|  
|DECIMAL\_DIGITS|Int16|  
|NUM\_PREC\_RADIX|Int16|  
|NULLABLE|Int16|  
|REMARKS|Строковое|  
|COLUMN\_DEF|Строковое|  
|SQL\_DATA\_TYPE|Int16|  
|SQL\_DATETIME\_SUB|Int16|  
|CHAR\_OCTET\_LENGTH|Int32|  
|ORDINAL\_POSITION|Int32|  
|IS\_NULLABLE|Строковое|  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)