---
title: Mappings1 тип данных Oracle
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: 9057a19abb1abc22924b5542f06e21a57a36ed94
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856339"
---
# <a name="oracle-data-type-mappings"></a>Сопоставления типов данных Oracle
В следующей таблице представлены типы данных Oracle и их сопоставления объекту <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Тип данных Oracle|Тип данных .NET Framework, возвращаемый OracleDataReader.GetValue|Тип данных OracleClient, возвращаемый OracleDataReader.GetOracleValue|Примечания|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB-ОБЪЕКТОВ**|**Byte]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для **номер** тип данных он разработан таким образом, чтобы <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо значение с плавающей запятой. Использование типа данных .NET Framework может вызвать переполнение.|  
|**ЦЕЛОЕ ЧИСЛО**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для **NUMBER(38)** тип данных он разработан таким образом, чтобы <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого значения. Использование типа данных .NET Framework может вызвать переполнение.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
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
|**МЕТКА ВРЕМЕНИ**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**МЕТКА ВРЕМЕНИ С МЕСТНЫМ ЧАСОВЫМ ПОЯСОМ**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**МЕТКА ВРЕМЕНИ С ЧАСОВЫМ ПОЯСОМ**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ЦЕЛОЕ ЧИСЛО БЕЗ ЗНАКА**|**Число**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для **NUMBER(38)** тип данных он разработан таким образом, чтобы <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого числа без знака. Использование типа данных .NET Framework может вызвать переполнение.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 В следующей таблице перечислены типы данных Oracle и типы данных .NET Framework (**System.Data.DbType** и <xref:System.Data.OracleClient.OracleType>) для использования при привязке их как параметров.  
  
|Тип данных Oracle|Перечисление DbType, которое привязывается как параметр|Перечисление OracleType, которое привязывается как параметр|Примечания|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle допускает привязку только **BFILE** как **BFILE** параметра. Поставщик данных .NET для Oracle автоматически не конструирует для вас при попытке привязать отличный от**BFILE** значений, таких как **byte []** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB-ОБЪЕКТОВ**||**BLOB-объектов**|Oracle допускает привязку только **BLOB-ОБЪЕКТОВ** как **BLOB-ОБЪЕКТОВ** параметра. Поставщик данных .NET для Oracle автоматически не конструирует для вас при попытке привязать отличный от**BLOB-ОБЪЕКТОВ** значений, таких как **byte []** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**CLOB**|Oracle допускает привязку только **CLOB** как **CLOB** параметра. Поставщик данных .NET для Oracle автоматически не конструирует для вас при попытке привязать отличный от**CLOB** значений, таких как **System.String** или <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Число с плавающей запятой, дважды, а**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**ЦЕЛОЕ ЧИСЛО**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, номер**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**ДЕНЬ ИНТЕРВАЛА В СЕКУНДУ**|**Объект**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle допускает привязку только **NCLOB** как **NCLOB** параметра. Поставщик данных .NET для Oracle автоматически не конструирует для вас при попытке привязать отличный от**NCLOB** значений, таких как **System.String** или <xref:System.Data.OracleClient.OracleString>.|  
|**НОМЕР**|**VarNumeric**|**Число**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**НЕОБРАБОТАННЫЕ**|**Binary**|**необработанные**||  
|**REF CURSOR**||**курсор**|Дополнительные сведения см. в разделе [REF CURSOR в Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**RowId**||  
|**МЕТКА ВРЕМЕНИ**|**DateTime**|**Метка времени**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**МЕТКА ВРЕМЕНИ С МЕСТНЫМ ЧАСОВЫМ ПОЯСОМ**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**МЕТКА ВРЕМЕНИ С ЧАСОВЫМ ПОЯСОМ**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**ЦЕЛОЕ ЧИСЛО БЕЗ ЗНАКА**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, номер**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 **InputOutput**, **вывода**, и **ReturnValue** **ParameterDirection** значения, используемые свойством <xref:System.Data.OracleClient.OracleParameter.Value%2A> свойство <xref:System.Data.OracleClient.OracleParameter> являются типами данных .NET Framework, если входное значение имеет тип данных Oracle (например, <xref:System.Data.OracleClient.OracleNumber> или <xref:System.Data.OracleClient.OracleString>). Это относится к **REF CURSOR**, **BFILE**, или **LOB** типов данных.  
  
## <a name="see-also"></a>См. также  
 [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
