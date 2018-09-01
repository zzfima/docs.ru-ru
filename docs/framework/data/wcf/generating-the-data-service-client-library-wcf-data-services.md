---
title: Создание библиотеки клиентов службы данных (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 170f9714f3cfbf2350423f28316d665d427fd56e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389378"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Создание библиотеки клиентов службы данных (службы данных WCF)
Служба данных, которая реализует [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] может возвращать документ метаданных службы, описывающий модель данных, предоставленная [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала. Дополнительные сведения см. в разделе [OData: документ метаданных службы](https://go.microsoft.com/fwlink/?LinkId=186070). Можно использовать **Add Service Reference** диалоговое окно в Visual Studio для добавления ссылки на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-службу на основе. При использовании этого средства для добавления ссылки на метаданные, возвращаемые функциями [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала в клиентский проект, он выполняет следующие действия:  
  
-   Запрашивает документ с метаданными службы из службы данных и интерпретирует возвращенные метаданные.  
  
    > [!NOTE]
    >  Возвращенные метаданные сохраняются в клиентском проекте в виде файла EDMX. Файл EDMX нельзя открыть с помощью конструктора моделей EDM, поскольку его формат отличается от формата файла EDMX, используемого платформой Entity Framework. Открыть этот файл метаданных можно с помощью редактора XML или любого текстового редактора. Дополнительные сведения см. в разделе [ \[MC-EDMX\]: модели EDM для формата упаковки служб данных](https://go.microsoft.com/fwlink/?LinkID=178833) спецификации  
  
-   Формирует представление службы в виде класса контейнера сущностей, порожденного от класса <xref:System.Data.Services.Client.DataServiceContext>. Этот сформированный класс контейнера сущностей аналогичен контейнеру сущностей, формируемому программами для работы с моделью EDM. Дополнительные сведения см. в разделе [Обзор служб объектов (Entity Framework)](https://msdn.microsoft.com/library/43014cf9-c9cb-4538-bfbb-197820b60038).  
  
-   Формирует классы данных типов модели данных, обнаруженных в метаданных службы.  
  
-   Добавляет в проект ссылку на сборку `System.Data.Services.Client`.  
  
 Дополнительные сведения см. в разделе [как: Добавление ссылки на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Клиентские классы службы данных также могут создаваться с помощью [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) средство в командной строке. Дополнительные сведения см. в разделе [как: вручную сформировать клиентские классы службы данных](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Сопоставление клиентских типов данных  
 При использовании **Add Service Reference** диалоговое окно в Visual Studio или `DataSvcUtil.exe` средства для формирования клиентских классов данных, основанных на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала, типы данных .NET Framework сопоставляются с примитивными типами из модели данных следующим образом:  
  
|Тип модели данных|Тип данных .NET Framework|  
|---------------------|------------------------------|  
|`Edm.Binary`|<xref:System.Byte> `[]`|  
|`Edm.Boolean`|<xref:System.Boolean>|  
|`Edm.Byte`|<xref:System.Byte>|  
|`Edm.DateTime`|<xref:System.DateTime>|  
|`Edm.Decimal`|<xref:System.Decimal>|  
|`Edm.Double`|<xref:System.Double>|  
|`Edm.Guid`|<xref:System.Guid>|  
|`Edm.Int16`|<xref:System.Int16>|  
|`Edm.Int32`|<xref:System.Int32>|  
|`Edm.Int64`|<xref:System.Int64>|  
|`Edm.SByte`|<xref:System.SByte>|  
|`Edm.Single`|<xref:System.Single>|  
|`Edm.String`|<xref:System.String>|  
  
 Дополнительные сведения см. в разделе [OData: примитивные типы данных](https://go.microsoft.com/fwlink/?LinkId=186072).  
  
## <a name="see-also"></a>См. также  
 [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
