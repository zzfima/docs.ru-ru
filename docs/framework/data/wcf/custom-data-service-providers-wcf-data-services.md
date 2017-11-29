---
title: "Специализированные поставщики служб данных (службы WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 90e837739edc74ee469f42720f52789ee1c8f6fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Специализированные поставщики служб данных (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включают набор поставщиков, которые позволяют определить модель данных на основе типов данных с поздним связыванием.  
  
|Поставщик|Описание|  
|--------------|-----------------|  
|Поставщик метаданных|Это базовый специализированный поставщик служб данных, позволяющий определить специализированную модель данных во время выполнения путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.|  
|Поставщик запросов|Этот поставщик позволяет выполнять запросы к специализированной модели данных, определенной при помощи интерфейса <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>. Поставщик запросов создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceQueryProvider>.|  
|Поставщик обновлений|Этот поставщик позволяет производить обновления типов, предоставляемых специализированным поставщиком служб данных, а также управлять параллелизмом. Поставщик обновлений создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>.|  
|Поставщик подкачки|Этот поставщик используется вместе со специализированным поставщиком служб данных для поддержки подкачки страниц на сервере. Поставщик подкачки для специализированной службы данных создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServicePagingProvider>.|  
|Потоковый поставщик|Этот поставщик позволяет предоставлять данные больших двоичных объектов в виде потока. Потоковый поставщик создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Поставщик потока также может использоваться вместе с платформой Entity Framework и поставщиками отражений источников данных. Дополнительные сведения см. в разделе [потокового поставщика](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
 Дополнительные сведения см. в статье [настраиваемых поставщиков данных](http://go.microsoft.com/fwlink/?LinkID=186850) и [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Provider Toolkit in [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).  
  
## <a name="see-also"></a>См. также  
 [Поставщики служб данных](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Поставщик Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [Поставщик отражения](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
