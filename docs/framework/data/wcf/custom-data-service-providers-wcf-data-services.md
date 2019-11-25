---
title: Специализированные поставщики служб данных (службы WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
ms.openlocfilehash: fd76f456665da76138b927d85a53924e8169c30a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975372"
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Специализированные поставщики служб данных (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включают набор поставщиков, которые позволяют определить модель данных на основе типов данных с поздним связыванием.  
  
|Поставщик|Описание|  
|--------------|-----------------|  
|Поставщик метаданных|Это базовый специализированный поставщик служб данных, позволяющий определить специализированную модель данных во время выполнения путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>.|  
|Поставщик запросов|Этот поставщик позволяет выполнять запросы к специализированной модели данных, определенной при помощи интерфейса <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>. Поставщик запросов создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceQueryProvider>.|  
|Поставщик обновлений|Этот поставщик позволяет производить обновления типов, предоставляемых специализированным поставщиком служб данных, а также управлять параллелизмом. Поставщик обновлений создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceUpdateProvider>.|  
|Поставщик подкачки|Этот поставщик используется вместе со специализированным поставщиком служб данных для поддержки подкачки страниц на сервере. Поставщик подкачки для специализированной службы данных создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServicePagingProvider>.|  
|Потоковый поставщик|Этот поставщик позволяет предоставлять данные больших двоичных объектов в виде потока. Потоковый поставщик создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Поставщик потока также может использоваться вместе с платформой Entity Framework и поставщиками отражений источников данных. Дополнительные сведения см. в разделе [Streaming Provider](streaming-provider-wcf-data-services.md).|  
  
 Дополнительные сведения см. в статье [поставщики пользовательских служб данных](https://go.microsoft.com/fwlink/?LinkID=186850) и набор средств поставщика Open Data Protocol (OData) в [пакете SDK OData](https://go.microsoft.com/fwlink/?LinkId=186069).  
  
## <a name="see-also"></a>См. также

- [Поставщики служб данных](data-services-providers-wcf-data-services.md)
- [Поставщик Entity Framework](entity-framework-provider-wcf-data-services.md)
- [Поставщик отражений](reflection-provider-wcf-data-services.md)
