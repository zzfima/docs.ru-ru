---
title: Коллекции схемы OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f1cb5e1fe967088b44fa4045dfe50c1c57d963eb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ole-db-schema-collections"></a>Коллекции схемы OLE DB
В данном разделе рассматривается поддержка коллекций схем для поставщиков OLE DB для Microsoft SQL Server, Oracle и Microsoft Jet.  
  
## <a name="microsoft-sql-server-ole-db-provider"></a>Поставщик OLE DB для Microsoft SQL Server  
 Драйвер Microsoft SQL Server OLE DB поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям схем:  
  
-   Таблицы  
  
-   Столбцы  
  
-   Процедуры  
  
-   ProcedureParameters  
  
-   Catalog  
  
-   Indexes  
  
### <a name="tables"></a>Таблицы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|TABLE_TYPE|Строковое|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Строковое|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|COLUMN_NAME|Строковое|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|Строковое|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Строковое|  
|CHARACTER_SET_SCHEMA|Строковое|  
|CHARACTER_SET_NAME|Строковое|  
|COLLATION_CATALOG|Строковое|  
|COLLATION_SCHEMA|Строковое|  
|COLLATION_NAME|Строковое|  
|DOMAIN_CATALOG|Строковое|  
|DOMAIN_SCHEMA|Строковое|  
|DOMAIN_NAME|Строковое|  
|DESCRIPTION|Строковое|  
|COLUMN_LCID|Int32|  
|COLUMN_COMPFLAGS|Int32|  
|COLUMN_SORTID|Int32|  
|COLUMN_TDSCOLLATION|Byte[]|  
|IS_COMPUTED|Boolean|  
  
### <a name="procedures"></a>Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строковое|  
|PROCEDURE_SCHEMA|Строковое|  
|PROCEDURE_NAME|Строковое|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Строковое|  
|DESCRIPTION|Строковое|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedureparameters"></a>ProcedureParameters  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строковое|  
|PROCEDURE_SCHEMA|Строковое|  
|PROCEDURE_NAME|Строковое|  
|PARAMETER_NAME|Строковое|  
|ORDINAL_POSITION|Int32|  
|PARAMETER_TYPE|Int32|  
|PARAMETER_HASDEFAULT|Boolean|  
|PARAMETER_DEFAULT|Строковое|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|Строковое|  
|TYPE_NAME|Строковое|  
|LOCAL_TYPE_NAME|Строковое|  
  
### <a name="catalog"></a>Catalog  
  
|ColumnName|DataType|  
|----------------|--------------|  
|CATALOG_NAME|Строковое|  
|DESCRIPTION|Строковое|  
  
### <a name="indexes"></a>Indexes  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|INDEX_CATALOG|Строковое|  
|INDEX_SCHEMA|Строковое|  
|INDEX_NAME|Строковое|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Строковое|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Десятичное число|  
|PAGES|Int32|  
|FILTER_CONDITION|Строковое|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-oracle-ole-db-provider"></a>Поставщик Microsoft OLE DB для Oracle  
 Драйвер OLE DB для Oracle (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
-   Таблицы  
  
-   Столбцы  
  
-   Процедуры  
  
-   ProcedureColumns  
  
-   ProcedureParameters  
  
-   Представления  
  
-   Indexes  
  
### <a name="tables"></a>Таблицы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|TABLE_TYPE|Строковое|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Строковое|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|COLUMN_NAME|Строковое|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|Строковое|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Строковое|  
|CHARACTER_SET_SCHEMA|Строковое|  
|CHARACTER_SET_NAME|Строковое|  
|COLLATION_CATALOG|Строковое|  
|COLLATION_SCHEMA|Строковое|  
|COLLATION_NAME|Строковое|  
|DOMAIN_CATALOG|Строковое|  
|DOMAIN_SCHEMA|Строковое|  
|DOMAIN_NAME|Строковое|  
|DESCRIPTION|Строковое|  
  
### <a name="procedures"></a>Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строковое|  
|PROCEDURE_SCHEMA|Строковое|  
|PROCEDURE_NAME|Строковое|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Строковое|  
|DESCRIPTION|Строковое|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="procedurecolumns"></a>ProcedureColumns  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строковое|  
|PROCEDURE_SCHEMA|Строковое|  
|PROCEDURE_NAME|Строковое|  
|COLUMN_NAME|Строковое|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ROWSET_NUMBER|Int64|  
|ORDINAL_POSITION|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DESCRIPTION|Строковое|  
|OVERLOAD|Int16|  
  
### <a name="views"></a>Представления  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|VIEW_DEFINITION|Строковое|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|Строковое|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indexes  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|INDEX_CATALOG|Строковое|  
|INDEX_SCHEMA|Строковое|  
|INDEX_NAME|Строковое|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Строковое|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Десятичное число|  
|PAGES|Int32|  
|FILTER_CONDITION|Строковое|  
|INTEGRATED|Boolean|  
  
## <a name="microsoft-jet-ole-db-provider"></a>Поставщик OLE DB для Microsoft Jet  
 Драйвер OLE DB для Jet (Майкрософт) поддерживает следующие специальные коллекции схем в дополнение к общим коллекциям.  
  
-   Таблицы  
  
-   Столбцы  
  
-   Процедуры  
  
-   Представления  
  
-   Indexes  
  
### <a name="tables"></a>Таблицы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|TABLE_TYPE|Строковое|  
|TABLE_GUID|Guid|  
|DESCRIPTION|Строковое|  
|TABLE_PROPID|Int64|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="columns"></a>Столбцы  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|COLUMN_NAME|Строковое|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|ORDINAL_POSITION|Int64|  
|COLUMN_HASDEFAULT|Boolean|  
|COLUMN_DEFAULT|Строковое|  
|COLUMN_FLAGS|Int64|  
|IS_NULLABLE|Boolean|  
|DATA_TYPE|Int32|  
|TYPE_GUID|Guid|  
|CHARACTER_MAXIMUM_LENGTH|Int64|  
|CHARACTER_OCTET_LENGTH|Int64|  
|NUMERIC_PRECISION|Int32|  
|NUMERIC_SCALE|Int16|  
|DATETIME_PRECISION|Int64|  
|CHARACTER_SET_CATALOG|Строковое|  
|CHARACTER_SET_SCHEMA|Строковое|  
|CHARACTER_SET_NAME|Строковое|  
|COLLATION_CATALOG|Строковое|  
|COLLATION_SCHEMA|Строковое|  
|COLLATION_NAME|Строковое|  
|DOMAIN_CATALOG|Строковое|  
|DOMAIN_SCHEMA|Строковое|  
|DOMAIN_NAME|Строковое|  
|DESCRIPTION|Строковое|  
  
### <a name="procedures"></a>Процедуры  
  
|ColumnName|DataType|  
|----------------|--------------|  
|PROCEDURE_CATALOG|Строковое|  
|PROCEDURE_SCHEMA|Строковое|  
|PROCEDURE_NAME|Строковое|  
|PROCEDURE_TYPE|Int16|  
|PROCEDURE_DEFINITION|Строковое|  
|DESCRIPTION|Строковое|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="views"></a>Представления  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|VIEW_DEFINITION|Строковое|  
|CHECK_OPTION|Boolean|  
|IS_UPDATABLE|Boolean|  
|DESCRIPTION|Строковое|  
|DATE_CREATED|DateTime|  
|DATE_MODIFIED|DateTime|  
  
### <a name="indexes"></a>Indexes  
  
|ColumnName|DataType|  
|----------------|--------------|  
|TABLE_CATALOG|Строковое|  
|TABLE_SCHEMA|Строковое|  
|TABLE_NAME|Строковое|  
|INDEX_CATALOG|Строковое|  
|INDEX_SCHEMA|Строковое|  
|INDEX_NAME|Строковое|  
|PRIMARY_KEY|Boolean|  
|UNIQUE|Boolean|  
|CLUSTERED|Boolean|  
|TYPE|Int32|  
|FILL_FACTOR|Int32|  
|INITIAL_SIZE|Int32|  
|NULLS|Int32|  
|SORT_BOOKMARKS|Boolean|  
|AUTO_UPDATE|Boolean|  
|NULL_COLLATION|Int32|  
|ORDINAL_POSITION|Int64|  
|COLUMN_NAME|Строковое|  
|COLUMN_GUID|Guid|  
|COLUMN_PROPID|Int64|  
|COLLATION|Int16|  
|CARDINALITY|Десятичное число|  
|PAGES|Int32|  
|FILTER_CONDITION|Строковое|  
|INTEGRATED|Boolean|  
  
## <a name="see-also"></a>См. также  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
