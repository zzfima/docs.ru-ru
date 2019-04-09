---
title: Публикация конечных точек метаданных
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 143a46ce18a0d9dee89bbbffac9be9a467e951df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121736"
---
# <a name="publishing-metadata-endpoints"></a>Публикация конечных точек метаданных
Службы Windows Communication Foundation (WCF) публикуют метаданные путем публикации одной или нескольких конечных точек метаданных. Публикация метаданных службы позволяет получать доступ к метаданным с использованием стандартных протоколов, таких как WS-MetadataExchange (MEX) и запросы HTTP/GET. Конечные точки подобны другим конечным точкам служб в том, что они имеют адрес, привязку и контракт, и могут быть добавлены в ведущее приложение службы посредством конфигурации или в коде. Для публикации конечных точек метаданных необходимо добавить в службу поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Показано, как настроить службу WCF для публикации метаданных таким образом, чтобы клиенты могли извлекать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя `?wsdl` строка запроса.  
  
 [Практическое руководство. Публикация метаданных для службы с использованием кода](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Показано, как включить публикацию метаданных для службы WCF в коде, чтобы клиенты могли извлекать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя `?wsdl` строка запроса.  
  
## <a name="see-also"></a>См. также

- [Публикация метаданных](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
