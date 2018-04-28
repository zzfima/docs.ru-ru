---
title: Публикация и получение метаданных через пользовательскую привязку
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f6226f01a284a9a24593c1be4fed2f96f3eae730
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Публикация и получение метаданных через пользовательскую привязку
Класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> поддерживает добавление конечной точки метаданных в службу. Эти конечные точки метаданных могут отвечать на запросы HTTP GET в URL-адрес, который имеет `?wsdl` строки запроса и на запросы WS-Transfer GET, определенный в спецификации WS-MetadataExchange (MEX). Конечные точки MEX реализуют контракт <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType>.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Публикация метаданных через настраиваемую привязку.  
 Чтобы включить конечные точки метаданных HTTP GET и HTTPS GET, необходимо присвоить логическое значение <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> или `true`. Привязки для этих конечных точек не могут быть настроены.  
  
 Впрочем, контракт <xref:System.ServiceModel.Description.IMetadataExchange> может использоваться с любой конечной точкой, включая те, которые используют настраиваемые привязки. Это объясняется тем, что конечные точки <xref:System.ServiceModel.Description.IMetadataExchange> идентичны любым другим конечным точкам службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Настройка привязки для использования с конечной точкой <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> требует навыков изменения конфигурации привязки, предоставляемой системой, или настройки <xref:System.ServiceModel.Description.IMetadataExchange>.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Получение метаданных через настраиваемую привязку.  
 Метаданные могут быть получены из конечных точек метаданных HTTP Get и HTTPS Get с использованием стандартных запросов HTTP или HTTPS GET.  
  
 Чтобы извлечь метаданные из конечной точки метаданных MEX, используется одна из стандартных привязок MEX, поддерживаемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. Тип <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> и средство Svcutil.exe автоматически выбирают одну из стандартных привязок MEX на основе адреса заданной конечной точки метаданных.  
  
 Если конечная точка метаданных MEX использует привязку, отличающуюся от стандартных привязок MEX, существует возможность настроить привязку, используемую классом <xref:System.ServiceModel.Description.MetadataExchangeClient>, используя код или предоставляя конфигурацию конечной точки клиента <xref:System.ServiceModel.Description.IMetadataExchange>. Инструмент Svcutil.exe автоматически загружает из своего файла конфигурации конфигурацию конечной точки клиента <xref:System.ServiceModel.Description.IMetadataExchange> с именем, аналогичным имени схемы URI для адреса конечной точки метаданных.  
  
## <a name="security"></a>Безопасность  
 При публикации метаданных через настраиваемую привязку, убедитесь, что привязка обеспечивает поддержку безопасности, требуемую для метаданных. Например, для предотвращения раскрытия информации и контроля прав клиента на получение метаданных существует возможность дополнительной защиты метаданных и приложения путем настройки конечной точки <xref:System.ServiceModel.Description.IMetadataExchange> таким образом, чтобы требовались шифрование и проверка подлинности. Образец [конечной точки метаданных защиты пользовательских](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) демонстрирует этот сценарий.  
  
## <a name="see-also"></a>См. также  
 [Защита служб](../../../../docs/framework/wcf/securing-services.md)  
 [Привязки WS-MetadataExchange](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)  
 [Практическое руководство. Настройка пользовательской привязки WS-Metadata Exchange](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)  
 [Практическое руководство. Получение метаданных через привязку, не использующую MEX](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
