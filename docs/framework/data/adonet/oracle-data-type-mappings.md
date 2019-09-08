---
title: Сопоставления типов данных Oracle
ms.date: 03/30/2017
ms.assetid: ec34ae21-bbbb-4adb-b672-83865e2a8451
ms.openlocfilehash: be478741069e9edd406d73c0b75d5960b9909896
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783418"
---
# <a name="oracle-data-type-mappings"></a>Сопоставления типов данных Oracle
В следующей таблице представлены типы данных Oracle и их сопоставления объекту <xref:System.Data.OracleClient.OracleDataReader>.  
  
|Тип данных Oracle|Тип данных .NET Framework, возвращаемый OracleDataReader.GetValue|Тип данных OracleClient, возвращаемый OracleDataReader.GetOracleValue|Примечания|  
|----------------------|--------------------------------------------------------------------|------------------------------------------------------------------------|-------------|  
|**BСВЕДЕНИЯ**|**Byte []**|<xref:System.Data.OracleClient.OracleBFile>||  
|**ОБЪЕКТЕ**|**Byte []**|<xref:System.Data.OracleClient.OracleLob>||  
|**CHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**CLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**DATE**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**FLOAT**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для типа данных **Number** и предназначен для того <xref:System.Data.OracleClient.OracleDataReader> , чтобы функция возвращала **System. Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо значения с плавающей запятой. Использование типа данных .NET Framework может вызвать переполнение.|  
|**ЦЕЛО**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для типа данных **Number (38)** и предназначен для того <xref:System.Data.OracleClient.OracleDataReader> , чтобы функция возвращала **System. Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого значения. Использование типа данных .NET Framework может вызвать переполнение.|  
|**ИНТЕРВАЛ ОТ ГОДА ДО МЕСЯЦА**|**Int32**|<xref:System.Data.OracleClient.OracleMonthSpan>||  
|**ИНТЕРВАЛ В ДЕНЬ ДО СЕКУНДЫ**|**TimeSpan**|<xref:System.Data.OracleClient.OracleTimeSpan>||  
|**LONG**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**LONG RAW**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**NCHAR**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**NCLOB**|**String**|<xref:System.Data.OracleClient.OracleLob>||  
|**НУМЕРАЦИЯ**|**Decimal**|<xref:System.Data.OracleClient.OracleNumber>|Использование типа данных .NET Framework может вызвать переполнение.|  
|**NVARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**ЧТЕН**|**Byte []**|<xref:System.Data.OracleClient.OracleBinary>||  
|**REF CURSOR**|||Тип данных **курсора Oracle ref** не поддерживается <xref:System.Data.OracleClient.OracleDataReader> объектом.|  
|**ROWID**|**String**|<xref:System.Data.OracleClient.OracleString>||  
|**TIMESTAMP**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**МЕТКА ВРЕМЕНИ С МЕСТНЫМ ЧАСОВЫМ ПОЯСОМ**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**МЕТКА ВРЕМЕНИ С ЧАСОВЫМ ПОЯСОМ**|**DateTime**|<xref:System.Data.OracleClient.OracleDateTime>||  
|**ЦЕЛОЕ ЧИСЛО БЕЗ ЗНАКА**|**Число**|<xref:System.Data.OracleClient.OracleNumber>|Этот тип данных является псевдонимом для типа данных **Number (38)** и предназначен для того <xref:System.Data.OracleClient.OracleDataReader> , чтобы функция возвращала значение **System. Decimal** или <xref:System.Data.OracleClient.OracleNumber> вместо целого числа без знака. Использование типа данных .NET Framework может вызвать переполнение.|  
|**VARCHAR2**|**String**|<xref:System.Data.OracleClient.OracleString>||  
  
 В следующей таблице перечислены типы данных Oracle и типы данных .NET Framework (**System. Data. DbType** и <xref:System.Data.OracleClient.OracleType>), которые используются при их привязке в качестве параметров.  
  
|Тип данных Oracle|Перечисление DbType, которое привязывается как параметр|Перечисление OracleType, которое привязывается как параметр|Примечания|  
|----------------------|-----------------------------------------------|---------------------------------------------------|-------------|  
|**BСВЕДЕНИЯ**||**BСведения**|Oracle допускает привязку типа **BFILE** только в качестве параметра **BFILE** . Поставщик данных .NET для Oracle не создает его автоматически при попытке привязать значение, отличное от**BFILE** , например **Byte []** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**ОБЪЕКТЕ**||**Объекте**|Oracle позволяет привязать **большой двоичный объект** только в качестве параметра **большого двоичного объекта** . Поставщик данных .NET для Oracle не создает его автоматически при попытке привязать значение, отличное от**большого двоичного объекта** , например **Byte []** или <xref:System.Data.OracleClient.OracleBinary>.|  
|**CHAR**|**ансистрингфикседленгс**|**Char**||  
|**CLOB**||**CLOB**|Oracle допускает привязку **CLOB** только в качестве параметра **CLOB** . Поставщик данных .NET для Oracle не создает его автоматически при попытке привязать значение, не являющееся**CLOB** , например **System. String** или <xref:System.Data.OracleClient.OracleString>.|  
|**DATE**|**DateTime**|**DateTime**||  
|**FLOAT**|**Одинарный, двойной, десятичный**|**Float, Double, число**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Определяет **System. Data. DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**ЦЕЛО**|**SByte, Int16, Int32, Int64, Decimal**|**SByte, Int16, Int32, число**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Определяет **System. Data. DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**ИНТЕРВАЛ ОТ ГОДА ДО МЕСЯЦА**|**Int32**|**интервалеартомонс**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**ИНТЕРВАЛ В ДЕНЬ ДО СЕКУНДЫ**|**Объект**|**интервалдайтосеконд**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**LONG**|**ансистринг**|**LongVarChar**||  
|**LONG RAW**|**Binary**|**лонграв**||  
|**NCHAR**|**стрингфикседленгс**|**NChar**||  
|**NCLOB**||**NClob**|Oracle позволяет привязать параметр **NCLOB** только в качестве параметра **NCLOB** . Поставщик данных .NET для Oracle не создает его автоматически при попытке привязать значение, отличное от**NCLOB** , например **System. String** или <xref:System.Data.OracleClient.OracleString>.|  
|**НУМЕРАЦИЯ**|**Типа VARNUMERIC**|**Число**||  
|**NVARCHAR2**|**String**|**NVarChar**||  
|**ЧТЕН**|**Binary**|**Чтен**||  
|**REF CURSOR**||**Набора**|Дополнительные сведения см. в разделе [Oracle REF CURSOR](oracle-ref-cursors.md).|  
|**ROWID**|**ансистринг**|**ROWID**||  
|**TIMESTAMP**|**DateTime**|**Метка времени**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**МЕТКА ВРЕМЕНИ С МЕСТНЫМ ЧАСОВЫМ ПОЯСОМ**|**DateTime**|**тиместамплокал**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**МЕТКА ВРЕМЕНИ С ЧАСОВЫМ ПОЯСОМ**|**DateTime**|**тиместампвистз**|<xref:System.Data.OracleClient.OracleType> доступен только при использование как клиентского, так и серверного программного обеспечения Oracle 9i.|  
|**ЦЕЛОЕ ЧИСЛО БЕЗ ЗНАКА**|**Byte, UInt16, UInt32, UInt64, Decimal**|**Byte, UInt16, UInt32, число**|<xref:System.Data.OracleClient.OracleParameter.Size%2A>Определяет **System. Data. DBType** и <xref:System.Data.OracleClient.OracleType>.|  
|**VARCHAR2**|**ансистринг**|**VarChar**||  
  
 **Значения инпутаутпут**, **Output**и **ReturnValue** **параметердиректион** , используемые <xref:System.Data.OracleClient.OracleParameter.Value%2A> свойством объекта,являются.NETFrameworkтипамиданных,еслитольковходноезначениенеявляетсятипомданныхOracle(для<xref:System.Data.OracleClient.OracleParameter> Например, <xref:System.Data.OracleClient.OracleNumber> или <xref:System.Data.OracleClient.OracleString>). Это не относится к типам данных **ref Cursor**, **BFILE**или **LOB** .  
  
## <a name="see-also"></a>См. также

- [Oracle и ADO.NET](oracle-and-adonet.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
