---
title: Типы SqlClient для Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: b121020c8779cfb3959425b1019eaf085b97d6cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54505190"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>Типы SqlClient для Entity Framework
Файл манифеста поставщика данных .NET Framework для SQL Server (SqlClient) содержит список типов-примитивов этого поставщика, аспекты каждого типа, сопоставления типов-примитивов между концептуальной моделью и режимом хранения, а также правила повышения и преобразования типов-примитивов концептуальной модели и модели хранения.  
  
 В следующей таблице описаны типы для SQL Server 2008, [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], и [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] баз данных и сопоставлении этих типов в концептуальной модели типы. Некоторые новые типы, которые появились в более поздних версиях SQL Server 2008, не поддерживаются в предыдущих версиях SQL Server. Эти типы указаны в таблице ниже.  
  
|Тип поставщика<br /><br /> имя|Тип поставщика<br /><br /> атрибуты|`EDMSimpleType`<br /><br /> имя|Области|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|Н/Д|`Edm.Boolean`|Н/Д|  
|`tinyint`|Н/Д|`Edm.Byte`|Н/Д|  
|`smallint`|Н/Д|`Edm.Int16`|Н/Д|  
|`int`|Н/Д|`Edm.Int32`|Н/Д|  
|`bigint`|Н/Д|`Edm.Int64`|Н/Д|  
|`float`|Н/Д|`Edm.Double`|Н/Д|  
|`real`|Н/Д|`Edm.Double`|Н/Д|  
|`decimal`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 38<br /><br /> -Значение по умолчанию: 18<br /><br /> -Константы: False<br /><br /> Масштаб:<br /><br /> -Минимум: 0<br /><br /> -Maximum: 38<br /><br /> -Значение по умолчанию: 0<br /><br /> -Константы: False|  
|`numeric`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 38<br /><br /> -Значение по умолчанию: 18<br /><br /> -Константы: False<br /><br /> Масштаб:<br /><br /> -Минимум: 0<br /><br /> -Maximum: 38<br /><br /> -Значение по умолчанию: 0<br /><br /> -Константы: False|  
|`smallmoney`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -Значение по умолчанию: 10<br /><br /> -Константы: Да<br /><br /> Масштаб:<br /><br /> -Значение по умолчанию: 4<br /><br /> -Константы: Да|  
|`money`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -Значение по умолчанию: 19<br /><br /> -Константы: Да<br /><br /> Масштаб:<br /><br /> -Значение по умолчанию: 4<br /><br /> -Константы: Да|  
|`binary`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 8000<br /><br /> -Значение по умолчанию: 8000<br /><br /> -Константы: False<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: Да<br /><br /> -Константы: Да|  
|`varbinary`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 8000<br /><br /> -Значение по умолчанию: 8000<br /><br /> -Константы: False<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
|`varbinary(max)`<br /><br /> Примечание. Этот тип не поддерживается в [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Значение по умолчанию: 214748364780<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
|`image`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Значение по умолчанию: 2147483647<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
|`timestamp`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Значение по умолчанию: 8<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: Да<br /><br /> -Константы: Да|  
|`rowversion`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Значение по умолчанию: 8<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: Да<br /><br /> -Константы: Да|  
|`smalldatetime`|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -Значение по умолчанию: 0<br /><br /> -Константы: Да|  
|`datetime`|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -Значение по умолчанию: 3<br /><br /> -Константы: Да|  
|`date`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -Значение по умолчанию: 0<br /><br /> -Константы: False|  
|`time`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.Time`|Точность:<br /><br /> -Значение по умолчанию: 7<br /><br /> -Константы: False|  
|`datetime2`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -Значение по умолчанию: 7<br /><br /> -Константы: False|  
|`datetimeoffset`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTimeOffset`|Точность:<br /><br /> -Значение по умолчанию: 7<br /><br /> -Константы: False|  
|`nvarchar`<br /><br /> Примечание. Этот тип не поддерживается в [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 4000<br /><br /> -Значение по умолчанию: 4000<br /><br /> -Константы: False<br /><br /> Юникод.<br /><br /> -Значение по умолчанию: Да<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
|`varchar`<br /><br /> Примечание. Этот тип не поддерживается в [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 8000<br /><br /> -Значение по умолчанию: 8000<br /><br /> -Константы: False<br /><br /> Юникод.<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
|`char`|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 8000<br /><br /> -Значение по умолчанию: 8000<br /><br /> -Константы: False<br /><br /> Юникод.<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: Да<br /><br /> -Константы: Да|  
|`nchar`|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 4000<br /><br /> -Значение по умолчанию: 4000<br /><br /> -Константы: False<br /><br /> Юникод.<br /><br /> -Значение по умолчанию: Да<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: Да<br /><br /> -Константы: Да|  
|`varchar`(`max`)|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 2147483647<br /><br /> -Константы: Да<br /><br /> Юникод.<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
|`nvarchar`(`max`)|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 1073741823<br /><br /> -Константы: Да<br /><br /> Юникод.<br /><br /> -Значение по умолчанию: Да<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
|`ntext`|Сравним равенства: False<br /><br /> Упорядочению: False|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 1073741823<br /><br /> -Константы: Да<br /><br /> Юникод.<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
|`text`|Сравним равенства: False<br /><br /> Упорядочению: False|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 2147483647<br /><br /> -Константы: Да<br /><br /> Юникод.<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
|`Unique`<br /><br /> `identifier`|Сравним равенства: Да<br /><br /> Упорядочению: Да|`Edm.Guid`|Н/Д|  
|`xml`|Сравним равенства: False<br /><br /> Упорядочению: False|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 1073741823<br /><br /> -Константы: Да<br /><br /> Юникод.<br /><br /> -Значение по умолчанию: Да<br /><br /> -Константы: Да<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: Да|  
  
## <a name="see-also"></a>См. также
- [Спецификации CSDL, SSDL и MSL](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
