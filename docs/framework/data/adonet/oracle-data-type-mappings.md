---
title: "Сопоставления типов данных Oracle | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Сопоставления типов данных Oracle
В следующей таблице представлены типы данных Oracle и их сопоставления объекту <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Тип данных Oracle|Тип данных .NET Framework, возвращаемый OracleDataReader.GetValue|Тип данных OracleClient, возвращаемый OracleDataReader.GetOracleValue|Примечания|  
|-----------------------|-----------------------------------------------------------------------|---------------------------------------------------------------------------|----------------|  
|**BFILE**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**Строковое**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**Строковое**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Десятичное число**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для типа данных **NUMBER** и разработан так, что <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо значения с плавающей запятой.  Использование типа данных .NET Framework может вызвать переполнение.|  
|**INTEGER**|**Десятичное число**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для типа данных **NUMBER\(38\)** и разработан так, что <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого значения.  Использование типа данных .NET Framework может вызвать переполнение.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**Строковое**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**Строковое**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**Строковое**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMBER**|**Десятичное число**|<xref:System.Data.OracleClient.OracleNumber>|Использование типа данных .NET Framework может вызвать переполнение.|  
|**NVARCHAR2**|**Строковое**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte\[\]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Тип данных Oracle **REF CURSOR** не поддерживается объектом <xref:System.Data.OracleClient.OracleDataReader>.|  
|**ROWID**|**Строковое**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**UNSIGNED INTEGER**|**Числовой**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для типа данных **NUMBER\(38\)** и разработан так, что <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого числа без знака.  Использование типа данных .NET Framework может вызвать переполнение.|  
|**VARCHAR2**|**Строковое**|<xref:System.Data.OracleClient.OracleString>||  
  
 В следующей таблице представлены типы данных Oracle и типы данных .NET Framework \(**System.Data.DbType** и <xref:System.Data.OracleClient.OracleType>\), которые используются при привязке их как параметров.  
  
|Тип данных Oracle|Перечисление DbType, которое привязывается как параметр|Перечисление OracleType, которое привязывается как параметр|Примечания|  
|-----------------------|-------------------------------------------------------------|-----------------------------------------------------------------|----------------|  
|**BFILE**||**BFile**|Oracle допускает привязку только **BFILE** как параметр **BFILE**.  Поставщик данных .NET для Oracle автоматически не конструирует параметр при попытке привязать значение не\-**BFILE**, например **byte\[\]** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**Blob**|Oracle допускает привязку только **BLOB** как параметр **BLOB**.  Поставщик данных .NET для Oracle автоматически не конструирует параметр при попытке привязать значение не\-**BLOB**, например **byte\[\]** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle допускает привязку только **CLOB** как параметр **CLOB**.  Поставщик данных .NET для Oracle автоматически не конструирует параметр при попытке привязать значение не\-**CLOB**, например **System.String** или <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**INTERVAL DAY TO SECOND**|**Объект**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle допускает привязку только **NCLOB** как параметр **NCLOB**.  Поставщик данных .NET для Oracle автоматически не конструирует параметр при попытке привязать значение не\-**NCLOB**, например **System.String** или <xref:System.Data.OracleClient.OracleString>.|  
|**NUMBER**|**VarNumeric**|**Числовой**||  
|**NVARCHAR2**|**Строковое**|**NVarChar**||  
|**RAW**|**Binary**|**Raw**||  
|**REF CURSOR**||**Курсор**|Для получения дополнительной информации см. [Курсоры REF CURSOR в Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**TIMESTAMP**|**DateTime**|**Отметка времени**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**UNSIGNED INTEGER**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 Значения **InputOutput**, **Output** и **ReturnValue** **ParameterDirection**, используемые свойством <xref:System.Data.OracleClient.OracleParameter.Value%2A> объекта <xref:System.Data.OracleClient.OracleParameter>, являются типами данных .NET Framework, если входное значение является типом данных Oracle \(например, <xref:System.Data.OracleClient.OracleNumber> или <xref:System.Data.OracleClient.OracleString>\).  Это не применяется к типам данных **REF CURSOR**, **BFILE** или **LOB**.  
  
## См. также  
 [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)