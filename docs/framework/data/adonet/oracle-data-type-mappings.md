---
title: Сопоставления типов данных Oracle
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: c1fb3a6838e6a1b242255d4035c10ab0ec07d536
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104576"
---
# <a name="oracle-data-type-mappings"></a>Сопоставления типов данных Oracle
В следующей таблице представлены типы данных Oracle и их сопоставления объекту <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Тип данных Oracle|Тип данных .NET Framework, возвращаемый OracleDataReader.GetValue|Тип данных OracleClient, возвращаемый OracleDataReader.GetOracleValue|Примечания|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BFILE**|**Byte[]**|<xref:System.Data.OracleClient.OracleBFile>||  
|**BLOB**|**Byte[]**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Десятичное число**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для **номер** тип данных он разработан таким образом, чтобы <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо значение с плавающей запятой. Использование типа данных .NET Framework может вызвать переполнение.|  
|**INTEGER**|**Десятичное число**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для **NUMBER(38)** тип данных он разработан таким образом, чтобы <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого значения. Использование типа данных .NET Framework может вызвать переполнение.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**INTERVAL DAY TO SECOND**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**NUMBER**|**Десятичное число**|<xref:System.Data.OracleClient.OracleNumber>|Использование типа данных .NET Framework может вызвать переполнение.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**RAW**|**Byte[]**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Oracle **REF CURSOR** тип данных не поддерживается <xref:System.Data.OracleClient.OracleDataReader> объекта.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**UNSIGNED INTEGER**|**Число**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для **NUMBER(38)** тип данных он разработан таким образом, чтобы <xref:System.Data.OracleClient.OracleDataReader> возвращает **System.Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого числа без знака. Использование типа данных .NET Framework может вызвать переполнение.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 В следующей таблице перечислены типы данных Oracle и типы данных .NET Framework (**System.Data.DbType** и <xref:System.Data.OracleClient.OracleType>) для использования при привязке их как параметров.  
  
|Тип данных Oracle|Перечисление DbType, которое привязывается как параметр|Перечисление OracleType, которое привязывается как параметр|Примечания|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BFILE**||**BFile**|Oracle допускает привязку только **BFILE** как **BFILE** параметра. Поставщик данных .NET для Oracle автоматически не конструирует для вас при попытке привязать отличный от**BFILE** значений, таких как **byte []** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**BLOB**||**Blob**|Oracle допускает привязку только **BLOB-ОБЪЕКТОВ** как **BLOB-ОБЪЕКТОВ** параметра. Поставщик данных .NET для Oracle автоматически не конструирует для вас при попытке привязать отличный от**BLOB-ОБЪЕКТОВ** значений, таких как **byte []** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**AnsiStringFixedLength**|**Char**||  
|**CLOB**||**Clob**|Oracle допускает привязку только **CLOB** как **CLOB** параметра. Поставщик данных .NET для Oracle автоматически не конструирует для вас при попытке привязать отличный от**CLOB** значений, таких как **System.String** или <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Single, Double, Decimal**|**Float, Double, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**INTEGER**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**INTERVAL YEAR TO MONTH**|**Int32**|**IntervalYearToMonth**|<xref:System.Data.OracleClient.OracleType> доступен только при с помощью обоих клиентских и серверных программного обеспечения Oracle 9i.|  
|**INTERVAL DAY TO SECOND**|**Object**|**IntervalDayToSecond**|<xref:System.Data.OracleClient.OracleType> доступен только при с помощью обоих клиентских и серверных программного обеспечения Oracle 9i.|  
|**LONG**|**AnsiString**|**LongVarChar**||  
|**LONG RAW**|**Бинарный**|**LongRaw**||  
|**NCHAR**|**StringFixedLength**|**NChar**||  
|**NCLOB**||**NClob**|Oracle допускает привязку только **NCLOB** как **NCLOB** параметра. Поставщик данных .NET для Oracle автоматически не конструирует для вас при попытке привязать отличный от**NCLOB** значений, таких как **System.String** или <xref:System.Data.OracleClient.OracleString>.|  
|**NUMBER**|**VarNumeric**|**Число**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**RAW**|**Бинарный**|**Raw**||  
|**REF CURSOR**||**Курсор**|Дополнительные сведения см. в разделе [REF CURSOR в Oracle](../../../../docs/framework/data/adonet/oracle-ref-cursors.md).|  
|**ROWID**|**AnsiString**|**Rowid**||  
|**TIMESTAMP**|**DateTime**|**Метка времени**|<xref:System.Data.OracleClient.OracleType> доступен только при с помощью обоих клиентских и серверных программного обеспечения Oracle 9i.|  
|**TIMESTAMP WITH LOCAL TIME ZONE**|**DateTime**|**TimestampLocal**|<xref:System.Data.OracleClient.OracleType> доступен только при с помощью обоих клиентских и серверных программного обеспечения Oracle 9i.|  
|**TIMESTAMP WITH TIME ZONE**|**DateTime**|**TimestampWithTz**|<xref:System.Data.OracleClient.OracleType> доступен только при с помощью обоих клиентских и серверных программного обеспечения Oracle 9i.|  
|**UNSIGNED INTEGER**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, Uint32, Number**|<xref:System.Data.OracleClient.OracleParameter.Size%2A> Определяет **System.Data.DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**AnsiString**|**VarChar**||  
  
 **InputOutput**, **вывода**, и **ReturnValue** **ParameterDirection** значения, используемые свойством <xref:System.Data.OracleClient.OracleParameter.Value%2A> свойство <xref:System.Data.OracleClient.OracleParameter> являются типами данных .NET Framework, если входное значение имеет тип данных Oracle (например, <xref:System.Data.OracleClient.OracleNumber> или <xref:System.Data.OracleClient.OracleString>). Это относится к **REF CURSOR**, **BFILE**, или **LOB** типов данных.  
  
## <a name="see-also"></a>См. также

- [Oracle и ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Управляемые поставщики ADO.NET и центр разработчиков DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
