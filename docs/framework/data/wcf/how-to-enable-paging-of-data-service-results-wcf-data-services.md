---
title: Практическое руководство. Включить разбиение на страницы результатов службы данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 77dbeba89b352fa470ab0523a830db9175a1a21a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122906"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>Практическое руководство. Включить разбиение на страницы результатов службы данных (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет ограничить количество сущностей, возвращаемых запросом службы данных. Пределы разбиения на страницы определены в методе, который вызывается при инициализации службы, и могут устанавливаться отдельно для каждого набора сущностей.  
  
 Если включена подкачка страниц, то последняя запись в канале содержит ссылку на следующую страницу данных. Дополнительные сведения см. в разделе [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 В этом разделе показывается, как изменить службу данных, чтобы включить разбиение на страницы возвращаемых `Customers` и наборов сущностей `Orders`. В примере этого раздела используется образец службы данных Northwind. Эта служба создается после завершения [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>Как включить разбиение на страницы возвращаемых клиентов и наборов сущностей Orders  
  
-   В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>См. также

- [Загрузка отложенного содержимого](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)
- [Практическое руководство. Загрузка результатов, разбитых на страницы](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
