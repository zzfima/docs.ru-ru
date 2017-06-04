---
title: "Как определить версию обнаружения зондирующего запроса | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Как определить версию обнаружения зондирующего запроса
Прокси\-сервер обнаружения может выдать несколько конечных точек обнаружения с помощью разных версий обнаружения.  При поступлении на прокси\-сервер многоадресного зондирующего запроса UDP прокси\-сервер должен ответить многоадресным сообщением отмены.  Чтобы сделать это, ему требуется знать версию обнаружения запроса.  
  
### Определение версии обнаружения зондирующего запроса  
  
1.  В методе, который отвечает на зондирующий запрос \(например, <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>\), используйте статическое свойство <xref:System.ServiceModel.OperationContext.Current%2A>, чтобы выполнить поиск <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, как показано в следующем коде.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
  
    ```  
  
## См. также  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>   
 [Реализация прокси\-сервера обнаружения](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)   
 [Образец прокси\-сервера обнаружения](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)