---
title: "Поставщики служб данных (службы WCF Data Services) | Microsoft Docs"
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
  - "Службы WCF Data Services, поставщики"
ms.assetid: a0160b1b-3d9c-4cc8-8391-cb0986a60a41
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Поставщики служб данных (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] поддерживают несколько моделей поставщиков для предоставления данных в виде канала [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)].  Этот раздел содержит сведения, позволяющие выбрать поставщик служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], наилучшим образом подходящий для имеющегося источника данных.  
  
## Поставщики источников данных  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] поддерживают следующие поставщики для определения модели данных службы данных.  
  
|Поставщик|Описание|  
|---------------|--------------|  
|Поставщик Entity Framework|Этот поставщик использует ADO.NET Entity Framework, позволяя использовать реляционные данные с помощью службы данных путем определения модели данных, сопоставленной с реляционными данными.  Источником данных может выступить SQL Server или любой другой источник данных с поддержкой Entity Framework от стороннего производителя.  Поставщик Entity Framework следует использовать при работе с реляционным источником данных, таким как база данных SQL Server.  Для получения дополнительной информации см. [Поставщик Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md).|  
|Поставщик отражения|Этот поставщик использует отражение, позволяя определить модель данных на основе существующих классов данных, предоставляемых как экземпляры интерфейса <xref:System.Linq.IQueryable%601>.  Обновления поддерживаются путем реализации интерфейса <xref:System.Data.Services.IUpdatable>.  Этот поставщик следует использовать, если имеются статические классы данных, сформированные во время выполнения, например формируемые LINQ to SQL или определяемые типизированным набором данных.  Для получения дополнительной информации см. [Поставщик отражения](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md).|  
|Специализированные поставщики служб данных|В состав служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] также включен набор поставщиков, позволяющий динамически определить модель данных на основе типов данных с поздним связыванием.  Эти интерфейсы следует реализовывать, если предоставляемые данные неизвестны на этапе разработки приложения или если использование Entity Framework или поставщиков отражения не является достаточным.  Для получения дополнительной информации см. [Специализированные поставщики служб данных](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).|  
  
## Другие поставщики служб данных  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] имеют следующие дополнительные поставщики служб данных, позволяющие повысить производительность источника данных, определенного с помощью одного из других поставщиков.  
  
|Поставщик|Описание|  
|---------------|--------------|  
|Потоковый поставщик|Этот поставщик позволяет предоставлять данные больших двоичных объектов с помощью служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  Потоковый поставщик создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceStreamProvider>.  Этот поставщик можно реализовать совместно с любым другим поставщиком источника данных.  Для получения дополнительной информации см. [Потоковый поставщик](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
## См. также  
 [Определение службы WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)   
 [Размещение службы данных](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)