---
title: "Публикация и получение метаданных через пользовательскую привязку | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Публикация и получение метаданных через пользовательскую привязку
Класс <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=fullName> поддерживает добавление конечной точки метаданных в службу.Эти конечные точки метаданных могут отвечать на запросы HTTP GET в URL, имеющем строку запроса `?wsdl` , и на запросы WS\-Transfer GET, согласно спецификации WS\-MetadataExchange \(MEX\).Конечные точки MEX реализуют контракт <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=fullName>.  
  
## Публикация метаданных через настраиваемую привязку.  
 Чтобы включить конечные точки метаданных HTTP GET и HTTPS GET, необходимо присвоить логическое значение `true` свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=fullName> или <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=fullName>.Привязки для этих конечных точек не могут быть настроены.  
  
 Впрочем, контракт <xref:System.ServiceModel.Description.IMetadataExchange> может использоваться с любой конечной точкой, включая те, которые используют настраиваемые привязки. Это объясняется тем, что конечные точки <xref:System.ServiceModel.Description.IMetadataExchange> идентичны любым другим конечным точкам службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Настройка привязки для использования с конечной точкой <xref:System.ServiceModel.Description.IMetadataExchange> требует навыков изменения конфигурации привязки, предоставляемой системой, или настройки <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>.  
  
## Получение метаданных через настраиваемую привязку.  
 Метаданные могут быть получены из конечных точек метаданных HTTP Get и HTTPS Get с использованием стандартных запросов HTTP или HTTPS GET.  
  
 Чтобы извлечь метаданные из конечной точки метаданных MEX, используется одна из стандартных привязок MEX, поддерживаемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=fullName>.Тип <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> и средство Svcutil.exe автоматически выбирают одну из стандартных привязок MEX на основе адреса заданной конечной точки метаданных.  
  
 Если конечная точка метаданных MEX использует привязку, отличающуюся от стандартных привязок MEX, существует возможность настроить привязку, используемую классом <xref:System.ServiceModel.Description.MetadataExchangeClient>, используя код или предоставляя конфигурацию конечной точки клиента <xref:System.ServiceModel.Description.IMetadataExchange>.Инструмент Svcutil.exe автоматически загружает из своего файла конфигурации конфигурацию конечной точки клиента <xref:System.ServiceModel.Description.IMetadataExchange> с именем, аналогичным имени схемы URI для адреса конечной точки метаданных.  
  
## Безопасность  
 При публикации метаданных через настраиваемую привязку, убедитесь, что привязка обеспечивает поддержку безопасности, требуемую для метаданных.Например, для предотвращения раскрытия информации и контроля прав клиента на получение метаданных существует возможность дополнительной защиты метаданных и приложения путем настройки конечной точки <xref:System.ServiceModel.Description.IMetadataExchange> таким образом, чтобы требовались шифрование и проверка подлинности.Пример [Пользовательская конечная точка защищенных метаданных](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) демонстрирует такой сценарий.  
  
## См. также  
 [Защита служб](../../../../docs/framework/wcf/securing-services.md)   
 [Привязки WS\-MetadataExchange](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)   
 [Практическое руководство. Настройка пользовательской привязки для обмена WS\-Metadata](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)   
 [Как получить метаданные через привязку, не использующую MEX](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)