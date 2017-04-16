---
title: "Представление данных в виде службы (службы WCF Data Services) | Microsoft Docs"
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
  - "начало работы, Службы WCF Data Services"
  - "Службы WCF Data Services, настройка"
  - "Службы WCF Data Services, начало работы"
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Представление данных в виде службы (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] интегрируются со средой Visual Studio, что упрощает определение служб для предоставления данных в качестве каналов [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)].  Создание службы данных, предоставляющей канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], включает следующие основные шаги:  
  
1.  **Определите** **модель данных**.  Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] стандартно поддерживают модели данных на основе [Платформа ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).  Для получения дополнительной информации см. [Как создать службу данных с использованием источника данных ADO.NET Entity Framework](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
     Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] поддерживают также модели данных на основе объектов CLR, возвращающих экземпляр интерфейса <xref:System.Linq.IQueryable%601>.  Это позволяет развертывать службы данных, основанные на списках, массивах и коллекциях платформы .NET Framework. Чтобы создавать, обновлять и удалять операции в этих структурах данных, необходимо также реализовать интерфейс <xref:System.Data.Services.IUpdatable>.  Для получения дополнительной информации см. [Как создать службу данных с помощью поставщика отражения](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
     Для более сложных сценариев службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включают набор поставщиков, позволяющий определить модель данных на основе типов данных с поздним связыванием.  Для получения дополнительной информации см. [Специализированные поставщики служб данных](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).  
  
2.  **Создание службы данных.** Самая базовая служба данных предоставляет класс, производный от класса <xref:System.Data.Services.DataService%601>, с типом `T`, представляющим имя контейнера сущностей, квалифицированное пространством имен.  Для получения дополнительной информации см. [Определение службы WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).  
  
3.  **Настройте службу данных.** По умолчанию [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] отключает доступ к ресурсам, предоставляемым контейнером сущностей. Интерфейс <xref:System.Data.Services.DataServiceConfiguration> позволяет настроить доступ к ресурсам и операциям службы, задать поддерживаемую версию [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] и определить другие разновидности поведения в рамках всей службы, такие как пакетная обработка или максимальное количество сущностей, которые могут быть возвращены в одном ответе. Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Пример создания простой службы данных на основе образца базы данных Northwind см. в разделе [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## См. также  
 [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)   
 [Общие сведения](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)