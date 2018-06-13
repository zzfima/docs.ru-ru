---
title: Как определить версию обнаружения зондирующего запроса
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8ac9804b0fe46ca5fbe580d713ec82a2f9bb0128
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489785"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Как определить версию обнаружения зондирующего запроса
Прокси-сервер обнаружения может выдать несколько конечных точек обнаружения с помощью разных версий обнаружения. При поступлении на прокси-сервер многоадресного зондирующего запроса UDP прокси-сервер должен ответить многоадресным сообщением отмены. Чтобы сделать это, ему требуется знать версию обнаружения запроса.  
  
### <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Определение версии обнаружения зондирующего запроса  
  
1.  В методе, который отвечает на зондирующий запрос (например, <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A>), используйте статическое свойство <xref:System.ServiceModel.OperationContext.Current%2A>, чтобы выполнить поиск <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, как показано в следующем коде.  
  
    ```  
    DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();  
    // Access the discovery version from the DiscoveryOperationContextExtension  
    doce.DiscoveryVersion;  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>  
 [Реализация прокси-сервера обнаружения](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)  
 [Образец прокси-сервера обнаружения](../../../../docs/framework/wcf/samples/discovery-proxy-sample.md)
