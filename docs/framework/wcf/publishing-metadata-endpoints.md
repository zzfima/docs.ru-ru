---
title: "Публикация конечных точек метаданных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64032fbc675e30e9f01a5db4d56ecc36574e08de
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="publishing-metadata-endpoints"></a>Публикация конечных точек метаданных
Службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] публикуют метаданные путем публикации одной или нескольких конечных точек метаданных. Публикация метаданных службы позволяет получать доступ к метаданным с использованием стандартных протоколов, таких как WS-MetadataExchange (MEX) и запросы HTTP/GET. Конечные точки подобны другим конечным точкам служб в том, что они имеют адрес, привязку и контракт, и могут быть добавлены в основное приложение службы посредством конфигурации или в коде. Для публикации конечных точек метаданных необходимо добавить в службу поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
## <a name="in-this-section"></a>Содержание  
 [Как: публикация метаданных для службы с помощью файла конфигурации](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Порядок настройки службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] для публикации метаданных, чтобы клиенты могли извлекать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя строку запроса `?wsdl`.  
  
 [Как: публикация метаданных для службы в коде](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Порядок включения публикации метаданных для службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] в коде, чтобы клиенты могли извлекать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя строку запроса `?wsdl`.  
  
## <a name="see-also"></a>См. также  
 [Публикация метаданных](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
