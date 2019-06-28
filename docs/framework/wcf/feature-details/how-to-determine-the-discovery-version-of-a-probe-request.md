---
title: Как определить версию обнаружения зондирующего запроса
ms.date: 03/30/2017
ms.assetid: b3c4e2e2-2957-4074-ae6a-776a5ca84278
ms.openlocfilehash: 8fbc3936278a5c6f403f48b59390c69c64378004
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425266"
---
# <a name="how-todetermine-the-discovery-version-of-a-probe-request"></a>Как определить версию обнаружения зондирующего запроса

Прокси-сервер обнаружения может выдать несколько конечных точек обнаружения с помощью разных версий обнаружения. При многоадресной рассылки UDP Зондирующий запрос прибывает в прокси-сервер, прокси-сервер должен вернуть ответ с многоадресное сообщение отмены. Чтобы сделать это, необходимо знать версию обнаружения запроса.

## <a name="to-determine-the-discovery-version-of-a-probe-request"></a>Определение версии обнаружения зондирующего запроса

В методе, который отвечает на Зондирующий запрос (например <xref:System.ServiceModel.Discovery.DiscoveryProxy.OnBeginFind%2A?displayProperty=nameWithType>) используйте статический <xref:System.ServiceModel.OperationContext.Current%2A?displayProperty=nameWithType> искомое свойство <xref:System.ServiceModel.Discovery.DiscoveryOperationContextExtension>, как показано в следующем коде.

```csharp
DiscoveryOperationContextExtension doce = OperationContext.Current.Extensions.Find<DiscoveryOperationContextExtension>();
// Access the discovery version from the DiscoveryOperationContextExtension
doce.DiscoveryVersion;
```

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Discovery.Configuration.AnnouncementEndpointElement.DiscoveryVersion%2A>
- [Реализация прокси-сервера обнаружения](../../../../docs/framework/wcf/feature-details/implementing-a-discovery-proxy.md)
