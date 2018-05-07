---
title: Создание библиотеки клиентов службы данных (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 999cbaa98c26d2d00b7e8f319ee87f8b07d7f5c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Создание библиотеки клиентов службы данных (службы данных WCF)
Службы данных, которая реализует [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] может возвращать документ метаданных службы, описывающий модель данных, предоставляемые [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала. Дополнительные сведения см. в разделе [OData: документ метаданных службы](http://go.microsoft.com/fwlink/?LinkId=186070). Можно использовать **добавить ссылку на службу** диалогового окна в Visual Studio, чтобы добавить ссылку на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-служба на основе. При использовании этого средства для добавления ссылки на метаданные, возвращаемые функциями [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канала в клиентский проект, он выполняет следующие действия:  
  
-   Запрашивает документ с метаданными службы из службы данных и интерпретирует возвращенные метаданные.  
  
    > [!NOTE]
    >  Возвращенные метаданные сохраняются в клиентском проекте в виде файла EDMX. Файл EDMX нельзя открыть с помощью конструктора моделей EDM, поскольку его формат отличается от формата файла EDMX, используемого платформой Entity Framework. Открыть этот файл метаданных можно с помощью редактора XML или любого текстового редактора. Дополнительные сведения см. в разделе [ \[MC-EDMX\]: модели EDM для формата упаковки служб данных](http://go.microsoft.com/fwlink/?LinkID=178833) спецификации  
  
-   Формирует представление службы в виде класса контейнера сущностей, порожденного от класса <xref:System.Data.Services.Client.DataServiceContext>. Этот сформированный класс контейнера сущностей аналогичен контейнеру сущностей, формируемому программами для работы с моделью EDM. Дополнительные сведения см. в разделе [Обзор служб объектов (Entity Framework)](http://msdn.microsoft.com/library/43014cf9-c9cb-4538-bfbb-197820b60038).  
  
-   Формирует классы данных типов модели данных, обнаруженных в метаданных службы.  
  
-   Добавляет в проект ссылку на сборку `System.Data.Services.Client`.  
  
 Дополнительные сведения см. в разделе [как: Добавление ссылки на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Клиентские классы службы данных также можно создать с помощью [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) средство командной строки. Дополнительные сведения см. в разделе [как: вручную создавать клиентские классы службы данных](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="client-data-type-mapping"></a>Сопоставление клиентских типов данных  
 При использовании **добавить ссылку на службу** диалоговое окно в Visual Studio или `DataSvcUtil.exe` сформировать клиентские классы данных, основанные на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канал, типы данных .NET Framework сопоставляются с примитивными типами из модель данных:  
  
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
  
 Дополнительные сведения см. в разделе [OData: примитивные типы данных](http://go.microsoft.com/fwlink/?LinkId=186072).  
  
## <a name="see-also"></a>См. также  
 [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
