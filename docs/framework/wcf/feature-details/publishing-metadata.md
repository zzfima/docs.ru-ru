---
title: Публикация метаданных
ms.date: 03/30/2017
helpviewer_keywords:
- meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
ms.openlocfilehash: 6e6c6d10eb0cd03ea2665f1787dba4e09528a141
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495019"
---
# <a name="publishing-metadata"></a>Публикация метаданных
Службы Windows Communication Foundation (WCF) публикуют метаданные путем публикации одной или нескольких конечных точек метаданных. Публикация метаданных службы позволяет получать доступ к метаданным с использованием стандартных протоколов, таких как WS-MetadataExchange (MEX) и запросы HTTP/GET. Конечные точки метаданных аналогичны другим конечным точкам служб в том, что они имеют адрес, привязку и контракт и могут быть добавлены в узел службы посредством конфигурации или принудительного кода.  
  
## <a name="publishing-metadata-endpoints"></a>Публикация конечных точек метаданных  
 Для публикации конечных точек метаданных для службы WCF, сначала необходимо добавить <xref:System.ServiceModel.Description.ServiceMetadataBehavior> службу поведение службы. Добавление экземпляра <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> позволяет службе отображать конечные точки метаданных. После добавления поведения службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> можно отображать конечные точки метаданных, поддерживающие протокол MEX или отвечающие на запросы HTTP/GET.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> использует <xref:System.ServiceModel.Description.WsdlExporter> для экспорта метаданных для всех конечных точек службы. Дополнительные сведения об экспорте метаданных из службы см. в разделе [Экспорт и импорт метаданных](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 Поведение службы <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> добавляет в узел службы экземпляр <xref:System.ServiceModel.Description.ServiceMetadataExtension> в качестве расширения. Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> обеспечивает реализацию протоколов публикации метаданных. Расширение <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> также можно использовать для получения метаданных службы во время выполнения, обратившись к свойству <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>.  
  
### <a name="mex-metadata-endpoints"></a>Конечные точки метаданных MEX  
 Чтобы добавить конечные точки метаданных, использующие протокол MEX, следует добавить в основное приложение службы конечные точки службы, которые используют контракт службы `IMetadataExchange`. WCF включает <xref:System.ServiceModel.Description.IMetadataExchange> интерфейс с именем этого контракта службы, который можно использовать как часть модели программирования WCF. Конечные точки WS-MetadataExchange или конечные точки MEX, можно использовать один из четырех привязок по умолчанию предоставляемых статическими методами производства в <xref:System.ServiceModel.Description.MetadataExchangeBindings> класса для сопоставления с привязками по умолчанию, используемый средствами WCF, например Svcutil.exe. Настраивать конечные точки метаданных MEX также можно с помощью пользовательской привязки.  
  
### <a name="http-get-metadata-endpoints"></a>Конечные точки метаданных HTTP GET  
 Чтобы добавить конечную точку метаданных в службу, которая отвечает на запросы HTTP/GET, следует задать свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> в поведении <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> значение `true`. Кроме того, можно настроить конечную точку метаданных, которая использует протокол HTTPS, задав свойству <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> в поведении <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> значение `true`.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Показано, как настроить службу WCF для публикации метаданных, чтобы клиенты могли извлекать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя `?wsdl` строку запроса.  
  
 [Практическое руководство. Публикация метаданных для службы с использованием кода](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Порядок включения публикации метаданных для службы WCF в коде, чтобы клиенты могли извлекать метаданные с помощью WS-MetadataExchange или запроса HTTP/GET, используя `?wsdl` строку запроса.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>См. также  
 [Экспорт и импорт метаданных](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
