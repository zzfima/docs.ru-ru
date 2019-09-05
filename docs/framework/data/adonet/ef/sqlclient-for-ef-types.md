---
title: Типы SqlClient для Entity Framework
ms.date: 03/30/2017
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
ms.openlocfilehash: af3a4eea08dd3f4e1a134fcb66d92bc4a3b077c7
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248381"
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
|`decimal`|Н/Д|`Edm.Decimal`|Обеспечивают<br /><br /> Минимальное 1<br /><br /> Выше 38<br /><br /> Параметры 18<br /><br /> Выходит False<br /><br /> Измените<br /><br /> Минимальное 0<br /><br /> Выше 38<br /><br /> Параметры 0<br /><br /> Выходит False|  
|`numeric`|Н/Д|`Edm.Decimal`|Обеспечивают<br /><br /> Минимальное 1<br /><br /> Выше 38<br /><br /> Параметры 18<br /><br /> Выходит False<br /><br /> Измените<br /><br /> Минимальное 0<br /><br /> Выше 38<br /><br /> Параметры 0<br /><br /> Выходит False|  
|`smallmoney`|Н/Д|`Edm.Decimal`|Обеспечивают<br /><br /> Параметры 10<br /><br /> Выходит True<br /><br /> Измените<br /><br /> Параметры 4<br /><br /> Выходит True|  
|`money`|Н/Д|`Edm.Decimal`|Обеспечивают<br /><br /> Параметры 19<br /><br /> Выходит True<br /><br /> Измените<br /><br /> Параметры 4<br /><br /> Выходит True|  
|`binary`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> Минимальное 1<br /><br /> Выше 8000<br /><br /> Параметры 8000<br /><br /> Выходит False<br /><br /> FixedLength<br /><br /> Параметры True<br /><br /> Выходит True|  
|`varbinary`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> Минимальное 1<br /><br /> Выше 8000<br /><br /> Параметры 8000<br /><br /> Выходит False<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
|`varbinary(max)`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Н/Д|`Edm.Binary`|MaxLength<br /><br /> Параметры 214748364780<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
|`image`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> Параметры 2147483647<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
|`timestamp`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> Параметры 8<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры True<br /><br /> Выходит True|  
|`rowversion`|Н/Д|`Edm.Binary`|MaxLength<br /><br /> Параметры 8<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры True<br /><br /> Выходит True|  
|`smalldatetime`|Н/Д|`Edm.DateTime`|Обеспечивают<br /><br /> Параметры 0<br /><br /> Выходит True|  
|`datetime`|Н/Д|`Edm.DateTime`|Обеспечивают<br /><br /> Параметры 3<br /><br /> Выходит True|  
|`date`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Обеспечивают<br /><br /> Параметры 0<br /><br /> Выходит False|  
|`time`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.Time`|Обеспечивают<br /><br /> Параметры 7<br /><br /> Выходит False|  
|`datetime2`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Обеспечивают<br /><br /> Параметры 7<br /><br /> Выходит False|  
|`datetimeoffset`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTimeOffset`|Обеспечивают<br /><br /> Параметры 7<br /><br /> Выходит False|  
|`nvarchar`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Н/Д|`Edm.String`|MaxLength<br /><br /> Минимальное 1<br /><br /> Выше 4000<br /><br /> Параметры 4000<br /><br /> Выходит False<br /><br /> Юникод:<br /><br /> Параметры True<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
|`varchar`<br /><br /> Примечание. Этот тип не поддерживается в SQL Server 2000.|Н/Д|`Edm.String`|MaxLength<br /><br /> Минимальное 1<br /><br /> Выше 8000<br /><br /> Параметры 8000<br /><br /> Выходит False<br /><br /> Юникод:<br /><br /> Параметры False<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
|`char`|Н/Д|`Edm.String`|MaxLength<br /><br /> Минимальное 1<br /><br /> Выше 8000<br /><br /> Параметры 8000<br /><br /> Выходит False<br /><br /> Юникод:<br /><br /> Параметры False<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры True<br /><br /> Выходит True|  
|`nchar`|Н/Д|`Edm.String`|MaxLength<br /><br /> Минимальное 1<br /><br /> Выше 4000<br /><br /> Параметры 4000<br /><br /> Выходит False<br /><br /> Юникод:<br /><br /> Параметры True<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры True<br /><br /> Выходит True|  
|`varchar`(`max`)|Н/Д|`Edm.String`|MaxLength<br /><br /> Параметры 2147483647<br /><br /> Выходит True<br /><br /> Юникод:<br /><br /> Параметры False<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
|`nvarchar`(`max`)|Н/Д|`Edm.String`|MaxLength<br /><br /> Параметры 1073741823<br /><br /> Выходит True<br /><br /> Юникод:<br /><br /> Параметры True<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
|`ntext`|Сравнимое сравнение: False<br /><br /> Сравниваемые порядок: False|`Edm.String`|MaxLength<br /><br /> Параметры 1073741823<br /><br /> Выходит True<br /><br /> Юникод:<br /><br /> Параметры False<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
|`text`|Сравнимое сравнение: False<br /><br /> Сравниваемые порядок: False|`Edm.String`|MaxLength<br /><br /> Параметры 2147483647<br /><br /> Выходит True<br /><br /> Юникод:<br /><br /> Параметры False<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
|`Unique`<br /><br /> `identifier`|Сравнимое сравнение: True<br /><br /> Сравниваемые порядок: True|`Edm.Guid`|Н/Д|  
|`xml`|Сравнимое сравнение: False<br /><br /> Сравниваемые порядок: False|`Edm.String`|MaxLength<br /><br /> Параметры 1073741823<br /><br /> Выходит True<br /><br /> Юникод:<br /><br /> Параметры True<br /><br /> Выходит True<br /><br /> FixedLength<br /><br /> Параметры False<br /><br /> Выходит True|  
  
## <a name="see-also"></a>См. также

- [Спецификации CSDL, SSDL и MSL](./language-reference/csdl-ssdl-and-msl-specifications.md)
