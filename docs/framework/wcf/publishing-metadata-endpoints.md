---
title: "Публикация конечных точек метаданных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Публикация конечных точек метаданных
Службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] публикуют метаданные путем публикации одной или нескольких конечных точек метаданных.Публикация метаданных службы позволяет получать доступ к метаданным с использованием стандартных протоколов, таких как WS\-MetadataExchange \(MEX\) и запросы HTTP\/GET.Конечные точки подобны другим конечным точкам служб в том, что они имеют адрес, привязку и контракт, и могут быть добавлены в основное приложение службы посредством конфигурации или в коде.Для публикации конечных точек метаданных необходимо добавить в службу поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
## В этом разделе  
 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Порядок настройки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] для публикации метаданных, чтобы клиенты могли извлекать метаданные с помощью WS\-MetadataExchange или запроса HTTP\/GET, используя строку запроса `?wsdl`.  
  
 [Как опубликовать метаданные для службы с использованием кода](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Порядок включения публикации метаданных для службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] в коде, чтобы клиенты могли извлекать метаданные с помощью WS\-MetadataExchange или запроса HTTP\/GET, используя строку запроса `?wsdl`.  
  
## См. также  
 [Публикация метаданных](../../../docs/framework/wcf/feature-details/publishing-metadata.md)