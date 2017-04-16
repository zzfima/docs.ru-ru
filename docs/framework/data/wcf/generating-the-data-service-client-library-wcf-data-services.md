---
title: "Формирование клиентской библиотеки службы данных (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "диалоговое окно «Добавить ссылку на службу»"
  - "клиентские приложения, Службы WCF Data Services"
  - "Службы WCF Data Services, клиентская библиотека"
ms.assetid: 314077c1-ac10-47e1-bed4-940b5462359d
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Формирование клиентской библиотеки службы данных (службы WCF Data Services)
Служба данных, реализующая [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], может возвратить документ с метаданными службы, в котором описывается модель данных, предоставленная каналом [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Дополнительные сведения см. в разделе [OData: документ метаданных службы](http://go.microsoft.com/fwlink/?LinkId=186070). Для добавления ссылки на службу на основе [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] можно использовать диалоговое окно **Добавить ссылку на службу** в Visual Studio.  При использовании этой программы для добавления ссылки на метаданные, возвращенные каналом [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] в клиентский проект, она выполняет следующие действия.  
  
-   Запрашивает документ с метаданными службы из службы данных и интерпретирует возвращенные метаданные.  
  
    > [!NOTE]
    >  Возвращенные метаданные сохраняются в клиентском проекте в виде файла EDMX.  Файл EDMX нельзя открыть с помощью конструктора моделей EDM, поскольку его формат отличается от формата файла EDMX, используемого платформой Entity Framework.  Открыть этот файл метаданных можно с помощью редактора XML или любого текстового редактора.  Дополнительные сведения см. в спецификации [\[MC\-EDMX\]: модели EDM для формата упаковки служб данных](http://go.microsoft.com/fwlink/?LinkID=178833)  
  
-   Формирует представление службы в виде класса контейнера сущностей, порожденного от класса <xref:System.Data.Services.Client.DataServiceContext>.  Этот сформированный класс контейнера сущностей аналогичен контейнеру сущностей, формируемому программами для работы с моделью EDM.  Для получения дополнительной информации см. [Object Services Overview \(Entity Framework\)](http://msdn.microsoft.com/ru-ru/43014cf9-c9cb-4538-bfbb-197820b60038).  
  
-   Формирует классы данных типов модели данных, обнаруженных в метаданных службы.  
  
-   Добавляет в проект ссылку на сборку `System.Data.Services.Client`.  
  
 Для получения дополнительной информации см. [Как добавить ссылку на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
 Клиентские классы службы данных можно также сформировать при помощи программы [DataSvcUtil.exe](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md) из командной строки.  Для получения дополнительной информации см. [Как формировать клиентские классы службы данных вручную](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## Сопоставление клиентских типов данных  
 При использовании диалога **Добавление ссылки на службу** в среде Visual Studio или программы `DataSvcUtil.exe` для формирования клиентских классов данных на основе канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], типы данных .NET Framework сопоставляются с примитивными типами модели данных следующим образом.  
  
|Тип модели данных|Тип данных .NET Framework|  
|-----------------------|-------------------------------|  
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
  
## См. также  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)