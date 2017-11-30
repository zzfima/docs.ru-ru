---
title: "Mappings1 тип данных Oracle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 746013a11d10162a78116ff41d0b09d942f7651b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="oracle-data-type-mappings"></a>Сопоставления типов данных Oracle
В следующей таблице представлены типы данных Oracle и их сопоставления объекту <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Тип данных Oracle|Тип данных .NET Framework, возвращаемый OracleDataReader.GetValue|Тип данных OracleClient, возвращаемый OracleDataReader.GetOracleValue|Примечания|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB-ОБЪЕКТ**|**Byte]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для **номер** тип данных и разработана, чтобы <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо значение с плавающей запятой. Использование типа данных .NET Framework может вызвать переполнение.|  
|**ЦЕЛОЕ ЧИСЛО СО ЗНАКОМ**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для **NUMBER(38)** тип данных и разработана, чтобы <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого значения. Использование типа данных .NET Framework может вызвать переполнение.|  
|**ИНТЕРВАЛ ГОД, МЕСЯЦ**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**ДЕНЬ ИНТЕРВАЛА В СЕКУНДУ**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**НОМЕР**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Использование типа данных .NET Framework может вызвать переполнение.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**НЕОБРАБОТАННЫЕ**|**Byte]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** тип данных не поддерживается <xref:System.Data.OracleClient.OracleDataReader> объекта.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**ОТМЕТКА ВРЕМЕНИ**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ОТМЕТКА ВРЕМЕНИ С МЕСТНЫМ ЧАСОВЫМ ПОЯСОМ**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ОТМЕТКА ВРЕМЕНИ С ЧАСОВЫМ ПОЯСОМ**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ЦЕЛОЕ ЧИСЛО БЕЗ ЗНАКА**|**Число**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для **NUMBER(38)** тип данных и разработана, чтобы <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целое число без знака. Использование типа данных .NET Framework может вызвать переполнение.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 В следующей таблице перечислены типы данных Oracle и типы данных .NET Framework (**System.Data.DbType** и <xref:System.Data.OracleClient.OracleType>) для использования при привязке их как параметров.  
  
|Тип данных Oracle|Перечисление DbType, которое привязывается как параметр|Перечисление OracleType, которое привязывается как параметр|Примечания|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle допускает привязку только **BFILE** как **BFILE** параметра. Поставщик данных .NET для Oracle не создает автоматически для пользователя при попытке привязать значение не -**BFILE** значений, таких как **byte []** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB-ОБЪЕКТ**||**BLOB-объект**|Oracle допускает привязку только **большого двоичного ОБЪЕКТА** как **большого двоичного ОБЪЕКТА** параметра. Поставщик данных .NET для Oracle не создает автоматически для пользователя при попытке привязать значение не -**большого двоичного ОБЪЕКТА** значений, таких как **byte []** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**CLOB**|Oracle допускает привязку только **CLOB** как **CLOB** параметра. Поставщик данных .NET для Oracle не создает автоматически для пользователя при попытке привязать значение не -**CLOB** значений, таких как **System.String** или <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, десятичное число**|**Число с плавающей запятой, дважды, а**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**ЦЕЛОЕ ЧИСЛО СО ЗНАКОМ**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, номер**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**ИНТЕРВАЛ ГОД, МЕСЯЦ**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**ДЕНЬ ИНТЕРВАЛА В СЕКУНДУ**|**Объект**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle допускает привязку только **NCLOB** как **NCLOB** параметра. Поставщик данных .NET для Oracle не создает автоматически для пользователя при попытке привязать значение не -**NCLOB** значений, таких как **System.String** или <xref:System.Data.OracleClient.OracleString>.|  
|**НОМЕР**|**VarNumeric**|**Число**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**НЕОБРАБОТАННЫЕ**|**Binary**|**Необработанные**||  
|**REF CURSOR**||**Курсор**|Дополнительные сведения см. в разделе [REF CURSOR в Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**RowId**||  
|**ОТМЕТКА ВРЕМЕНИ**|**DateTime**|**Метка времени**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**ОТМЕТКА ВРЕМЕНИ С МЕСТНЫМ ЧАСОВЫМ ПОЯСОМ**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**ОТМЕТКА ВРЕМЕНИ С ЧАСОВЫМ ПОЯСОМ**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**ЦЕЛОЕ ЧИСЛО БЕЗ ЗНАКА**|**Байт, UInt16, UInt32, UInt64, Decimal**|**Байт, UInt16, Uint32, номер**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 **InputOutput**, **вывода**, и **ReturnValue** **ParameterDirection** значений, используемых в <xref:System.Data.OracleClient.OracleParameter.Value%2A> свойство <xref:System.Data.OracleClient.OracleParameter> объекта являются типами данных .NET Framework, если входное значение имеет тип данных Oracle (например, <xref:System.Data.OracleClient.OracleNumber> или <xref:System.Data.OracleClient.OracleString>). Это не относится к **REF CURSOR**, **BFILE**, или **LOB** типов данных.  
  
## <a name="see-also"></a>См. также  
 [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
