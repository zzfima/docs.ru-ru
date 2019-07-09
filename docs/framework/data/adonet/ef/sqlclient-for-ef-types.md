---
title: Типы SqlClient для Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: 7e3abe86128670656bfb2607b8531c9ceb0e4134
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662119"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>Типы SqlClient для Entity Framework
Файл манифеста поставщика данных .NET Framework для SQL Server (SqlClient) содержит список типов-примитивов этого поставщика, аспекты каждого типа, сопоставления типов-примитивов между концептуальной моделью и режимом хранения, а также правила повышения и преобразования типов-примитивов концептуальной модели и модели хранения.  
  
 В следующей таблице описаны типы для баз данных SQL Server 2008, SQL Server 2005 и SQL Server 2000, а также как эти типы сопоставляются с типами концептуальной модели. Некоторые новые типы, которые появились в более поздних версиях SQL Server 2008, не поддерживаются в предыдущих версиях SQL Server. Эти типы указаны в таблице ниже.  
  
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
|`smallmoney`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -Значение по умолчанию: 10<br /><br /> -Константы: True<br /><br /> Масштаб:<br /><br /> -Значение по умолчанию: 4<br /><br /> -Константы: True|  
|`money`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -Значение по умолчанию: 19<br /><br /> -Константы: True<br /><br /> Масштаб:<br /><br /> -Значение по умолчанию: 4<br /><br /> -Константы: True|  
|`binary`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 8000<br /><br /> -Значение по умолчанию: 8000<br /><br /> -Константы: False<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: True<br /><br /> -Константы: True|  
|`varbinary`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 8000<br /><br /> -Значение по умолчанию: 8000<br /><br /> -Константы: False<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
|`varbinary(max)`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Значение по умолчанию: 214748364780<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
|`image`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Значение по умолчанию: 2147483647<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
|`timestamp`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Значение по умолчанию: 8<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: True<br /><br /> -Константы: True|  
|`rowversion`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Значение по умолчанию: 8<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: True<br /><br /> -Константы: True|  
|`smalldatetime`|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -Значение по умолчанию: 0<br /><br /> -Константы: True|  
|`datetime`|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -Значение по умолчанию: 3<br /><br /> -Константы: True|  
|`date`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -Значение по умолчанию: 0<br /><br /> -Константы: False|  
|`time`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.Time`|Точность:<br /><br /> -Значение по умолчанию: 7<br /><br /> -Константы: False|  
|`datetime2`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -Значение по умолчанию: 7<br /><br /> -Константы: False|  
|`datetimeoffset`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTimeOffset`|Точность:<br /><br /> -Значение по умолчанию: 7<br /><br /> -Константы: False|  
|`nvarchar`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 4000<br /><br /> -Значение по умолчанию: 4000<br /><br /> -Константы: False<br /><br /> Юникод:<br /><br /> -Значение по умолчанию: True<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
|`varchar`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 8000<br /><br /> -Значение по умолчанию: 8000<br /><br /> -Константы: False<br /><br /> Юникод:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
|`char`|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 8000<br /><br /> -Значение по умолчанию: 8000<br /><br /> -Константы: False<br /><br /> Юникод:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: True<br /><br /> -Константы: True|  
|`nchar`|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимум: 1<br /><br /> -Maximum: 4000<br /><br /> -Значение по умолчанию: 4000<br /><br /> -Константы: False<br /><br /> Юникод:<br /><br /> -Значение по умолчанию: True<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: True<br /><br /> -Константы: True|  
|`varchar`(`max`)|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 2147483647<br /><br /> -Константы: True<br /><br /> Юникод:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
|`nvarchar`(`max`)|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 1073741823<br /><br /> -Константы: True<br /><br /> Юникод:<br /><br /> -Значение по умолчанию: True<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
|`ntext`|Сравним равенства: False<br /><br /> Упорядочению: False|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 1073741823<br /><br /> -Константы: True<br /><br /> Юникод:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
|`text`|Сравним равенства: False<br /><br /> Упорядочению: False|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 2147483647<br /><br /> -Константы: True<br /><br /> Юникод:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
|`Unique`<br /><br /> `identifier`|Сравним равенства: True<br /><br /> Упорядочению: True|`Edm.Guid`|Н/Д|  
|`xml`|Сравним равенства: False<br /><br /> Упорядочению: False|`Edm.String`|MaxLength:<br /><br /> -Значение по умолчанию: 1073741823<br /><br /> -Константы: True<br /><br /> Юникод:<br /><br /> -Значение по умолчанию: True<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -Значение по умолчанию: False<br /><br /> -Константы: True|  
  
## <a name="see-also"></a>См. также

- [Спецификации CSDL, SSDL и MSL](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
