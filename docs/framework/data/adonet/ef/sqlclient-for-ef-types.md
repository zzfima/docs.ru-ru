---
title: Типы SqlClient для Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: d132583bba2520d37693be6c4b085cfa514003e0
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737850"
---
# <a name="sqlclient-for-entity-frameworktypes"></a>Типы SqlClient для Entity Framework
Файл манифеста поставщика данных .NET Framework для SQL Server (SqlClient) содержит список типов-примитивов этого поставщика, аспекты каждого типа, сопоставления типов-примитивов между концептуальной моделью и режимом хранения, а также правила повышения и преобразования типов-примитивов концептуальной модели и модели хранения.  
  
 В следующей таблице описываются типы баз данных SQL Server 2008, SQL Server 2005 и SQL Server 2000, а также о том, как эти типы сопоставляются с типами концептуальной модели. Некоторые новые типы, которые появились в более поздних версиях SQL Server 2008, не поддерживаются в предыдущих версиях SQL Server. Эти типы указаны в таблице ниже.  
  
|Тип поставщика<br /><br /> имя|Тип поставщика<br /><br /> атрибуты|`EDMSimpleType`<br /><br /> имя|Области|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|Н/Д|`Edm.Boolean`|Н/Д|  
|`tinyint`|Н/Д|`Edm.Byte`|Н/Д|  
|`smallint`|Н/Д|`Edm.Int16`|Н/Д|  
|`int`|Н/Д|`Edm.Int32`|Н/Д|  
|`bigint`|Н/Д|`Edm.Int64`|Н/Д|  
|`float`|Н/Д|`Edm.Double`|Н/Д|  
|`real`|Н/Д|`Edm.Double`|Н/Д|  
|`decimal`|Н/Д|`Edm.Decimal`|Обеспечивают<br /><br /> — Минимум: 1<br /><br /> — Максимум: 38<br /><br /> -По умолчанию: 18<br /><br /> -Constant: false<br /><br /> Измените<br /><br /> — Минимум: 0<br /><br /> — Максимум: 38<br /><br /> -По умолчанию: 0<br /><br /> -Constant: false|  
|`numeric`|Н/Д|`Edm.Decimal`|Обеспечивают<br /><br /> — Минимум: 1<br /><br /> — Максимум: 38<br /><br /> -По умолчанию: 18<br /><br /> -Constant: false<br /><br /> Измените<br /><br /> — Минимум: 0<br /><br /> — Максимум: 38<br /><br /> -По умолчанию: 0<br /><br /> -Constant: false|  
|`smallmoney`|Н/Д|`Edm.Decimal`|Обеспечивают<br /><br /> -По умолчанию: 10<br /><br /> -Constant: true<br /><br /> Измените<br /><br /> -По умолчанию: 4<br /><br /> -Constant: true|  
|`money`|Н/Д|`Edm.Decimal`|Обеспечивают<br /><br /> -По умолчанию: 19<br /><br /> -Constant: true<br /><br /> Измените<br /><br /> -По умолчанию: 4<br /><br /> -Constant: true|  
|`binary`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Constant: false<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`varbinary`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Constant: false<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`varbinary(max)`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Н/Д|`Edm.Binary`|MaxLength<br /><br /> -По умолчанию: 214748364780<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`image`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> -По умолчанию: 2147483647<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`timestamp`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> -По умолчанию: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`rowversion`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> -По умолчанию: 8<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`smalldatetime`|Н/Д|`Edm.DateTime`|Обеспечивают<br /><br /> -По умолчанию: 0<br /><br /> -Constant: true|  
|`datetime`|Н/Д|`Edm.DateTime`|Обеспечивают<br /><br /> -По умолчанию: 3<br /><br /> -Constant: true|  
|`date`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Обеспечивают<br /><br /> -По умолчанию: 0<br /><br /> -Constant: false|  
|`time`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.Time`|Обеспечивают<br /><br /> -По умолчанию: 7<br /><br /> -Constant: false|  
|`datetime2`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Обеспечивают<br /><br /> -По умолчанию: 7<br /><br /> -Constant: false|  
|`datetimeoffset`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTimeOffset`|Обеспечивают<br /><br /> -По умолчанию: 7<br /><br /> -Constant: false|  
|`nvarchar`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Н/Д|`Edm.String`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 4000<br /><br /> -По умолчанию: 4000<br /><br /> -Constant: false<br /><br /> Юникод:<br /><br /> -По умолчанию: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`varchar`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Н/Д|`Edm.String`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Constant: false<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`char`|Н/Д|`Edm.String`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Constant: false<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`nchar`|Н/Д|`Edm.String`|MaxLength<br /><br /> — Минимум: 1<br /><br /> — Максимум: 4000<br /><br /> -По умолчанию: 4000<br /><br /> -Constant: false<br /><br /> Юникод:<br /><br /> -По умолчанию: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: true<br /><br /> -Constant: true|  
|`varchar`(`max`)|Н/Д|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 2147483647<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`nvarchar`(`max`)|Н/Д|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 1073741823<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`ntext`|Равное сравнимое: false<br /><br /> Сравниваемые порядок: false|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 1073741823<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`text`|Равное сравнимое: false<br /><br /> Сравниваемые порядок: false|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 2147483647<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: false<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
|`Unique`<br /><br /> `identifier`|Равное сравнимое: true<br /><br /> Сравниваемые порядок: true|`Edm.Guid`|Н/Д|  
|`xml`|Равное сравнимое: false<br /><br /> Сравниваемые порядок: false|`Edm.String`|MaxLength<br /><br /> -По умолчанию: 1073741823<br /><br /> -Constant: true<br /><br /> Юникод:<br /><br /> -По умолчанию: true<br /><br /> -Constant: true<br /><br /> FixedLength<br /><br /> -По умолчанию: false<br /><br /> -Constant: true|  
  
## <a name="see-also"></a>См. также

- [Спецификации CSDL, SSDL и MSL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
