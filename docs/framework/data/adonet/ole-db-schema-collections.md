---
title: "Коллекции схем OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Коллекции схем OLE DB
В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.  
  
## Поставщик OLE DB для Microsoft SQL Server  
 Драйвер OLE DB для Microsoft SQL Server поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
-   Таблицы  
  
-   Столбцы  
  
-   Процедуры  
  
-   ProcedureParameters  
  
-   Catalog  
  
-   Indexes  
  
### Таблицы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|TABLE\_TYPE|Строковое|  
|TABLE\_GUID|Guid|  
|DESCRIPTION|Строковое|  
|TABLE\_PROPID|Int64|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_HASDEFAULT|Boolean|  
|COLUMN\_DEFAULT|Строковое|  
|COLUMN\_FLAGS|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DATETIME\_PRECISION|Int64|  
|CHARACTER\_SET\_CATALOG|Строковое|  
|CHARACTER\_SET\_SCHEMA|Строковое|  
|CHARACTER\_SET\_NAME|Строковое|  
|COLLATION\_CATALOG|Строковое|  
|COLLATION\_SCHEMA|Строковое|  
|COLLATION\_NAME|Строковое|  
|DOMAIN\_CATALOG|Строковое|  
|DOMAIN\_SCHEMA|Строковое|  
|DOMAIN\_NAME|Строковое|  
|DESCRIPTION|Строковое|  
|COLUMN\_LCID|Int32|  
|COLUMN\_COMPFLAGS|Int32|  
|COLUMN\_SORTID|Int32|  
|COLUMN\_TDSCOLLATION|Byte\[\]|  
|IS\_COMPUTED|Boolean|  
  
### Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_CATALOG|Строковое|  
|PROCEDURE\_SCHEMA|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|PROCEDURE\_TYPE|Int16|  
|PROCEDURE\_DEFINITION|Строковое|  
|DESCRIPTION|Строковое|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### ProcedureParameters  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_CATALOG|Строковое|  
|PROCEDURE\_SCHEMA|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|PARAMETER\_NAME|Строковое|  
|ORDINAL\_POSITION|Int32|  
|PARAMETER\_TYPE|Int32|  
|PARAMETER\_HASDEFAULT|Boolean|  
|PARAMETER\_DEFAULT|Строковое|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DESCRIPTION|Строковое|  
|TYPE\_NAME|Строковое|  
|LOCAL\_TYPE\_NAME|Строковое|  
  
### Catalog  
  
|ColumnName|DataType|  
|----------------|--------------|  
|CATALOG\_NAME|Строковое|  
|DESCRIPTION|Строковое|  
  
### Indexes  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|INDEX\_CATALOG|Строковое|  
|INDEX\_SCHEMA|Строковое|  
|INDEX\_NAME|Строковое|  
|PRIMARY\_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL\_FACTOR|Int32|  
|INITIAL\_SIZE|Int32|  
|NULLS|Int32|  
|SORT\_BOOKMARKS|Boolean|  
|AUTO\_UPDATE|Boolean|  
|NULL\_COLLATION|Int32|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Десятичное число|  
|PAGES|Int32|  
|FILTER\_CONDITION|Строковое|  
|INTEGRATED|Boolean|  
  
## Поставщик Microsoft OLE DB для Oracle  
 Драйвер OLE DB для Oracle \(Майкрософт\) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
-   Таблицы  
  
-   Столбцы  
  
-   Процедуры  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Представления  
  
-   Indexes  
  
### Таблицы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|TABLE\_TYPE|Строковое|  
|TABLE\_GUID|Guid|  
|DESCRIPTION|Строковое|  
|TABLE\_PROPID|Int64|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_HASDEFAULT|Boolean|  
|COLUMN\_DEFAULT|Строковое|  
|COLUMN\_FLAGS|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DATETIME\_PRECISION|Int64|  
|CHARACTER\_SET\_CATALOG|Строковое|  
|CHARACTER\_SET\_SCHEMA|Строковое|  
|CHARACTER\_SET\_NAME|Строковое|  
|COLLATION\_CATALOG|Строковое|  
|COLLATION\_SCHEMA|Строковое|  
|COLLATION\_NAME|Строковое|  
|DOMAIN\_CATALOG|Строковое|  
|DOMAIN\_SCHEMA|Строковое|  
|DOMAIN\_NAME|Строковое|  
|DESCRIPTION|Строковое|  
  
### Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_CATALOG|Строковое|  
|PROCEDURE\_SCHEMA|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|PROCEDURE\_TYPE|Int16|  
|PROCEDURE\_DEFINITION|Строковое|  
|DESCRIPTION|Строковое|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### ProcedureColumns  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_CATALOG|Строковое|  
|PROCEDURE\_SCHEMA|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ROWSET\_NUMBER|Int64|  
|ORDINAL\_POSITION|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DESCRIPTION|Строковое|  
|OVERLOAD|Int16|  
  
### Представления  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|VIEW\_DEFINITION|Строковое|  
|CHECK\_OPTION|Boolean|  
|IS\_UPDATABLE|Boolean|  
|DESCRIPTION|Строковое|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Indexes  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|INDEX\_CATALOG|Строковое|  
|INDEX\_SCHEMA|Строковое|  
|INDEX\_NAME|Строковое|  
|PRIMARY\_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL\_FACTOR|Int32|  
|INITIAL\_SIZE|Int32|  
|NULLS|Int32|  
|SORT\_BOOKMARKS|Boolean|  
|AUTO\_UPDATE|Boolean|  
|NULL\_COLLATION|Int32|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Десятичное число|  
|PAGES|Int32|  
|FILTER\_CONDITION|Строковое|  
|INTEGRATED|Boolean|  
  
## Поставщик OLE DB для Microsoft Jet  
 Драйвер OLE DB для Jet \(Майкрософт\) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
-   Таблицы  
  
-   Столбцы  
  
-   Процедуры  
  
-   Представления  
  
-   Indexes  
  
### Таблицы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|TABLE\_TYPE|Строковое|  
|TABLE\_GUID|Guid|  
|DESCRIPTION|Строковое|  
|TABLE\_PROPID|Int64|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_HASDEFAULT|Boolean|  
|COLUMN\_DEFAULT|Строковое|  
|COLUMN\_FLAGS|Int64|  
|IS\_NULLABLE|Boolean|  
|DATA\_TYPE|Int32|  
|TYPE\_GUID|Guid|  
|CHARACTER\_MAXIMUM\_LENGTH|Int64|  
|CHARACTER\_OCTET\_LENGTH|Int64|  
|NUMERIC\_PRECISION|Int32|  
|NUMERIC\_SCALE|Int16|  
|DATETIME\_PRECISION|Int64|  
|CHARACTER\_SET\_CATALOG|Строковое|  
|CHARACTER\_SET\_SCHEMA|Строковое|  
|CHARACTER\_SET\_NAME|Строковое|  
|COLLATION\_CATALOG|Строковое|  
|COLLATION\_SCHEMA|Строковое|  
|COLLATION\_NAME|Строковое|  
|DOMAIN\_CATALOG|Строковое|  
|DOMAIN\_SCHEMA|Строковое|  
|DOMAIN\_NAME|Строковое|  
|DESCRIPTION|Строковое|  
  
### Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE\_CATALOG|Строковое|  
|PROCEDURE\_SCHEMA|Строковое|  
|PROCEDURE\_NAME|Строковое|  
|PROCEDURE\_TYPE|Int16|  
|PROCEDURE\_DEFINITION|Строковое|  
|DESCRIPTION|Строковое|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Представления  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|VIEW\_DEFINITION|Строковое|  
|CHECK\_OPTION|Boolean|  
|IS\_UPDATABLE|Boolean|  
|DESCRIPTION|Строковое|  
|DATE\_CREATED|DateTime|  
|DATE\_MODIFIED|DateTime|  
  
### Indexes  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE\_CATALOG|Строковое|  
|TABLE\_SCHEMA|Строковое|  
|TABLE\_NAME|Строковое|  
|INDEX\_CATALOG|Строковое|  
|INDEX\_SCHEMA|Строковое|  
|INDEX\_NAME|Строковое|  
|PRIMARY\_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL\_FACTOR|Int32|  
|INITIAL\_SIZE|Int32|  
|NULLS|Int32|  
|SORT\_BOOKMARKS|Boolean|  
|AUTO\_UPDATE|Boolean|  
|NULL\_COLLATION|Int32|  
|ORDINAL\_POSITION|Int64|  
|COLUMN\_NAME|Строковое|  
|COLUMN\_GUID|Guid|  
|COLUMN\_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Десятичное число|  
|PAGES|Int32|  
|FILTER\_CONDITION|Строковое|  
|INTEGRATED|Boolean|  
  
## См. также  
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)