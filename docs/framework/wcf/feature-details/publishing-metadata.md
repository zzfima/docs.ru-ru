---
title: "Публикация метаданных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86d9eb8e7e7c78f091deea55322cbef6e6d0f3c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="publishing-metadata"></a>Публикация метаданных
Службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] публикуют метаданные путем публикации одной или нескольких конечных точек метаданных. Публикация метаданных службы позволяет получать доступ к метаданным с использованием стандартных протоколов, таких как WS-MetadataExchange (MEX) и запросы HTTP/GET. Конечные точки метаданных аналогичны другим конечным точкам служб в том, что они имеют адрес, привязку и контракт и могут быть добавлены в узел службы посредством конфигурации или принудительного кода.  
  
## <a name="publishing-metadata-endpoints"></a>Публикация конечных точек метаданных  
 Для публикации конечных точек метаданных для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сначала необходимо добавить в службу поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>. Добавление экземпляра <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> позволяет службе отображать конечные точки метаданных. После добавления поведения службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> можно отображать конечные точки метаданных, поддерживающие протокол MEX или отвечающие на запросы HTTP/GET.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> использует <xref:System.ServiceModel.Description.WsdlExporter> для экспорта метаданных для всех конечных точек службы. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Экспорт метаданных из службы, в разделе [Экспорт и импорт метаданных](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 Поведение службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> добавляет в узел службы экземпляр <xref:System.ServiceModel.Description.ServiceMetadataExtension> в качестве расширения. Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> обеспечивает реализацию протоколов публикации метаданных. Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> также можно использовать для получения метаданных службы во время выполнения, обратившись к свойству <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>.  
  
### <a name="mex-metadata-endpoints"></a>Конечные точки метаданных MEX  
 Чтобы добавить конечные точки метаданных, использующие протокол MEX, следует добавить в основное приложение службы конечные точки службы, которые используют контракт службы `IMetadataExchange`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] содержит интерфейс <xref:System.ServiceModel.Description.IMetadataExchange> с именем этого контракта службы, который можно использовать как часть модели программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Конечные точки WS-Metadata Exchange (или конечные точки MEX) могут использовать одну из четырех привязок по умолчанию, предоставляемых статическими методами производства в классе <xref:System.ServiceModel.Description.MetadataExchangeBindings> для сопоставления с привязками по умолчанию, используемыми средствами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], например Svcutil.exe. Настраивать конечные точки метаданных MEX также можно с помощью пользовательской привязки.  
  
### <a name="http-get-metadata-endpoints"></a>Конечные точки метаданных HTTP GET  
 Чтобы добавить конечную точку метаданных в службу, которая отвечает на запросы HTTP/GET, следует задать свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> в поведении <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> значение `true`. Кроме того, можно настроить конечную точку метаданных, которая использует протокол HTTPS, задав свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> в поведении <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> значение `true`.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Порядок настройки службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для публикации метаданных, чтобы клиенты могли извлекать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя строку запроса `?wsdl`.  
  
 [Практическое руководство. Публикация метаданных для службы с использованием кода](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Порядок включения публикации метаданных для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в коде, чтобы клиенты могли извлекать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя строку запроса `?wsdl`.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>См. также  
 [Экспорт и импорт метаданных](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
