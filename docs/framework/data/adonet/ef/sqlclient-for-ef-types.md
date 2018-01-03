---
title: "Типы SqlClient для Entity Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2a95ead-c845-4e97-9fb3-04b444f7ed81
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b04a7199fefc5df93d5e3472163d16c66e9279c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="sqlclient-for-entity-frameworktypes"></a>Типы SqlClient для Entity Framework
Файл манифеста поставщика данных .NET Framework для SQL Server (SqlClient) содержит список типов-примитивов этого поставщика, аспекты каждого типа, сопоставления типов-примитивов между концептуальной моделью и режимом хранения, а также правила повышения и преобразования типов-примитивов концептуальной модели и модели хранения.  
  
 В следующей таблице описаны типы для SQL Server 2008 [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], и [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] баз данных и как эти типы сопоставляются с концептуальной модели типы. Некоторые новые типы, которые появились в более поздних версиях SQL Server 2008, не поддерживаются в предыдущих версиях SQL Server. Эти типы указаны в таблице ниже.  
  
|Тип поставщика<br /><br /> имя|Тип поставщика<br /><br /> атрибуты|`EDMSimpleType`<br /><br /> имя|Области|  
|----------------------------|----------------------------------|------------------------------|------------|  
|`bit`|Н/Д|`Edm.Boolean`|Н/Д|  
|`tinyint`|Н/Д|`Edm.Byte`|Н/Д|  
|`smallint`|Н/Д|`Edm.Int16`|Н/Д|  
|`int`|Н/Д|`Edm.Int32`|Н/Д|  
|`bigint`|Н/Д|`Edm.Int64`|Н/Д|  
|`float`|Н/Д|`Edm.Double`|Н/Д|  
|`real`|Н/Д|`Edm.Double`|Н/Д|  
|`decimal`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -Минимальное: 1<br /><br /> -Максимальное: 38<br /><br /> -По умолчанию: 18<br /><br /> -Константа: False<br /><br /> Масштаб:<br /><br /> -Минимальное: 0<br /><br /> -Максимальное: 38<br /><br /> -По умолчанию: 0<br /><br /> -Константа: False|  
|`numeric`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -Минимальное: 1<br /><br /> -Максимальное: 38<br /><br /> -По умолчанию: 18<br /><br /> -Константа: False<br /><br /> Масштаб:<br /><br /> -Минимальное: 0<br /><br /> -Максимальное: 38<br /><br /> -По умолчанию: 0<br /><br /> -Константа: False|  
|`smallmoney`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -По умолчанию: 10<br /><br /> -Константы: True<br /><br /> Масштаб:<br /><br /> -По умолчанию: 4<br /><br /> -Константы: True|  
|`money`|Н/Д|`Edm.Decimal`|Точность:<br /><br /> -По умолчанию: 19<br /><br /> -Константы: True<br /><br /> Масштаб:<br /><br /> -По умолчанию: 4<br /><br /> -Константы: True|  
|`binary`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Минимальное: 1<br /><br /> -Максимальное: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Константа: False<br /><br /> FixedLength:<br /><br /> -По умолчанию: True<br /><br /> -Константы: True|  
|`varbinary`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -Минимальное: 1<br /><br /> -Максимальное: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Константа: False<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
|`varbinary(max)`<br /><br /> Примечание: Этот тип не поддерживается в [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -По умолчанию: 214748364780<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
|`image`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -По умолчанию: 2147483647<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
|`timestamp`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -По умолчанию: 8<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: True<br /><br /> -Константы: True|  
|`rowversion`|Н/Д|`Edm.Binary`|MaxLength:<br /><br /> -По умолчанию: 8<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: True<br /><br /> -Константы: True|  
|`smalldatetime`|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -По умолчанию: 0<br /><br /> -Константы: True|  
|`datetime`|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -По умолчанию: 3<br /><br /> -Константы: True|  
|`date`<br /><br /> Примечание: Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -По умолчанию: 0<br /><br /> -Константа: False|  
|`time`<br /><br /> Примечание: Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.Time`|Точность:<br /><br /> -По умолчанию: 7<br /><br /> -Константа: False|  
|`datetime2`<br /><br /> Примечание: Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTime`|Точность:<br /><br /> -По умолчанию: 7<br /><br /> -Константа: False|  
|`datetimeoffset`<br /><br /> Примечание: Этот тип не поддерживается в SQL Server 2005 и SQL Server 2000.|Н/Д|`Edm.DateTimeOffset`|Точность:<br /><br /> -По умолчанию: 7<br /><br /> -Константа: False|  
|`nvarchar`<br /><br /> Примечание: Этот тип не поддерживается в [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимальное: 1<br /><br /> -Максимальное: 4000<br /><br /> -По умолчанию: 4000<br /><br /> -Константа: False<br /><br /> Юникод.<br /><br /> -По умолчанию: True<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
|`varchar`<br /><br /> Примечание: Этот тип не поддерживается в [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)].|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимальное: 1<br /><br /> -Максимальное: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Константа: False<br /><br /> Юникод.<br /><br /> -По умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
|`char`|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимальное: 1<br /><br /> -Максимальное: 8000<br /><br /> -По умолчанию: 8000<br /><br /> -Константа: False<br /><br /> Юникод.<br /><br /> -По умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: True<br /><br /> -Константы: True|  
|`nchar`|Н/Д|`Edm.String`|MaxLength:<br /><br /> -Минимальное: 1<br /><br /> -Максимальное: 4000<br /><br /> -По умолчанию: 4000<br /><br /> -Константа: False<br /><br /> Юникод.<br /><br /> -По умолчанию: True<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: True<br /><br /> -Константы: True|  
|`varchar`(`max`)|Н/Д|`Edm.String`|MaxLength:<br /><br /> -По умолчанию: 2147483647<br /><br /> -Константы: True<br /><br /> Юникод.<br /><br /> -По умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
|`nvarchar`(`max`)|Н/Д|`Edm.String`|MaxLength:<br /><br /> -По умолчанию: 1073741823<br /><br /> -Константы: True<br /><br /> Юникод.<br /><br /> -По умолчанию: True<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
|`ntext`|Сравним равенства: False<br /><br /> Упорядочению: False|`Edm.String`|MaxLength:<br /><br /> -По умолчанию: 1073741823<br /><br /> -Константы: True<br /><br /> Юникод.<br /><br /> -По умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
|`text`|Сравним равенства: False<br /><br /> Упорядочению: False|`Edm.String`|MaxLength:<br /><br /> -По умолчанию: 2147483647<br /><br /> -Константы: True<br /><br /> Юникод.<br /><br /> -По умолчанию: False<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
|`Unique`<br /><br /> `identifier`|Сравним равенства: True<br /><br /> Упорядочению: True|`Edm.Guid`|Н/Д|  
|`xml`|Сравним равенства: False<br /><br /> Упорядочению: False|`Edm.String`|MaxLength:<br /><br /> -По умолчанию: 1073741823<br /><br /> -Константы: True<br /><br /> Юникод.<br /><br /> -По умолчанию: True<br /><br /> -Константы: True<br /><br /> FixedLength:<br /><br /> -По умолчанию: False<br /><br /> -Константы: True|  
  
## <a name="see-also"></a>См. также  
 [Спецификации CSDL, SSDL и MSL](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
