---
title: Создание библиотеки клиентов службы данных (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- Add Service Reference dialog box
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
ms.openlocfilehash: 14ea550715c1b224945137f123eed3b53e56cead
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918641"
---
# <a name="generating-the-data-service-client-library-wcf-data-services"></a>Создание библиотеки клиентов службы данных (службы данных WCF)
Служба данных, реализующая интерфейс [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] , может возвращать документ метаданных службы, описывающий модель данных, предоставляемую [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналом. Дополнительные сведения см. в [разделе OData: Документ](https://go.microsoft.com/fwlink/?LinkId=186070)метаданных службы. Для добавления ссылки на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]службу на основе можно использовать диалоговое окно Добавление ссылки на службу в Visual Studio. При использовании этого средства для добавления ссылки на метаданные, возвращаемые [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-каналом в клиентский проект, выполняются следующие действия.  
  
- Запрашивает документ с метаданными службы из службы данных и интерпретирует возвращенные метаданные.  
  
    > [!NOTE]
    > Возвращенные метаданные сохраняются в клиентском проекте в виде файла EDMX. Файл EDMX нельзя открыть с помощью конструктора моделей EDM, поскольку его формат отличается от формата файла EDMX, используемого платформой Entity Framework. Открыть этот файл метаданных можно с помощью редактора XML или любого текстового редактора. Дополнительные сведения см. на [ \[странице MC-EDMX\]: Спецификация формата](https://go.microsoft.com/fwlink/?LinkID=178833) упаковки для служб данных EDM  
  
- Формирует представление службы в виде класса контейнера сущностей, порожденного от класса <xref:System.Data.Services.Client.DataServiceContext>. Этот сформированный класс контейнера сущностей аналогичен контейнеру сущностей, формируемому программами для работы с моделью EDM. Дополнительные сведения см. в разделе [Обзор служб объектов (Entity Framework)](https://docs.microsoft.com/previous-versions/bb386871(v=vs.100)).  
  
- Формирует классы данных типов модели данных, обнаруженных в метаданных службы.  
  
- Добавляет в проект ссылку на сборку `System.Data.Services.Client`.  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Добавьте ссылку](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)на службу данных.  
  
 Классы клиентской службы данных также можно создать с помощью средства [DataSvcUtil. exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) из командной строки. Дополнительные сведения см. в разделе [Практическое руководство. Создание классов](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md)клиентской службы данных вручную.  
  
## <a name="client-data-type-mapping"></a>Сопоставление клиентских типов данных  
 При использовании диалогового окна **Добавление ссылки на службу** в Visual Studio или `DataSvcUtil.exe` средства для создания клиентских классов данных, основанных на [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] веб-канале, типы данных .NET Framework сопоставляются с типами-примитивами из модели данных следующим образом:  
  
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
  
 Дополнительные сведения см. в [разделе OData: Примитивные типы](https://go.microsoft.com/fwlink/?LinkId=186072)данных.  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
