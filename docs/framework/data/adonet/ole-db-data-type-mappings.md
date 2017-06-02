---
title: "Сопоставления типов данных OLE DB | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Сопоставления типов данных OLE DB
В приведенной ниже таблице показаны выводимые типы [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] для типов данных поставщика данных .NET Framework для ADO и OLE DB \(<xref:System.Data.OleDb>\).  Приведены также типизированные методы доступа для <xref:System.Data.OleDb.OleDbDataReader>.  
  
|Тип ADO|Тип OLE DB|Тип [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|Типизированный метод доступа [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]|  
|-------------|----------------|---------------------------------------------------------------------|----------------------------------------------------------------------------------------------|  
|adBigInt|DBTYPE\_I8|Int64|GetInt64\(\)|  
|adBinary|DBTYPE\_BYTES|Byte\[\]|GetBytes\(\)|  
|adBoolean|DBTYPE\_BOOL|Boolean|GetBoolean\(\)|  
|adBSTR|DBTYPE\_BSTR|Строковое|GetString\(\)|  
|adChapter|DBTYPE\_HCHAPTER|Поддерживается с помощью `DataReader`.  См. раздел [Извлечение данных с помощью DataReader](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).|GetValue\(\)|  
|adChar|DBTYPE\_STR|Строковое|GetString\(\)|  
|adCurrency|DBTYPE\_CY|Десятичное число|GetDecimal\(\)|  
|adDate|DBTYPE\_DATE|DateTime|GetDateTime\(\)|  
|adDBDate|DBTYPE\_DBDATE|DateTime|GetDateTime\(\)|  
|adDBTime|DBTYPE\_DBTIME|DateTime|GetDateTime\(\)|  
|adDBTimeStamp|DBTYPE\_DBTIMESTAMP|DateTime|GetDateTime\(\)|  
|adDecimal|DBTYPE\_DECIMAL|Десятичное число|GetDecimal\(\)|  
|adDouble|DBTYPE\_R8|Double|GetDouble\(\)|  
|adError|DBTYPE\_ERROR|ExternalException|GetValue\(\)|  
|adFileTime|DBTYPE\_FILETIME|DateTime|GetDateTime\(\)|  
|adGUID|DBTYPE\_GUID|Guid|GetGuid\(\)|  
|adIDispatch|DBTYPE\_IDISPATCH \*|Объект|GetValue\(\)|  
|adInteger|DBTYPE\_I4|Int32|GetInt32\(\)|  
|adIUnknown|DBTYPE\_IUNKNOWN \*|Объект|GetValue\(\)|  
|adNumeric|DBTYPE\_NUMERIC|Десятичное число|GetDecimal\(\)|  
|adPropVariant|DBTYPE\_PROPVARIANT|Объект|GetValue\(\)|  
|adSingle|DBTYPE\_R4|Single|GetFloat\(\)|  
|adSmallInt|DBTYPE\_I2|Int16|GetInt16\(\)|  
|adTinyInt|DBTYPE\_I1|Byte|GetByte\(\)|  
|adUnsignedBigInt|DBTYPE\_UI8|UInt64|GetValue\(\)|  
|adUnsignedInt|DBTYPE\_UI4|UInt32|GetValue\(\)|  
|adUnsignedSmallInt|DBTYPE\_UI2|UInt16|GetValue\(\)|  
|adUnsignedTinyInt|DBTYPE\_UI1|Byte|GetByte\(\)|  
|adVariant|DBTYPE\_VARIANT|Объект|GetValue\(\)|  
|adWChar|DBTYPE\_WSTR|Строковое|GetString\(\)|  
|adUserDefined|DBTYPE\_UDT|не поддерживается||  
|adVarNumeric|DBTYPE\_VARNUMERIC|не поддерживается||  
  
 \* Для таких типов OLE DB, как `DBTYPE_IUNKNOWN` и `DBTYPE_IDISPATCH`, ссылка на объект служит представлением указателя в упакованном виде.  
  
## См. также  
 [Получение и изменение данных в ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)