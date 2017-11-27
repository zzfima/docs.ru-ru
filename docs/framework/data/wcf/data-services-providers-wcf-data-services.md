---
title: "Поставщики служб данных (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, providers
ms.assetid: a0160b1b-3d9c-4cc8-8391-cb0986a60a41
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3f794088f2494157e22b8551c6241786c7a73398
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="data-services-providers-wcf-data-services"></a>Поставщики служб данных (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]поддерживает несколько моделей поставщиков для предоставления данных в виде [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] веб-канала. Этот раздел содержит сведения, позволяющие выбрать поставщик служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], наилучшим образом подходящий для имеющегося источника данных.  
  
## <a name="data-source-providers"></a>Поставщики источников данных  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]поддерживает следующие поставщики для определения модели данных службы данных.  
  
|Поставщик|Описание|  
|--------------|-----------------|  
|Поставщик Entity Framework|Этот поставщик использует ADO.NET Entity Framework, позволяя использовать реляционные данные с помощью службы данных путем определения модели данных, сопоставленной с реляционными данными. Источником данных может выступить SQL Server или любой другой источник данных с поддержкой Entity Framework от стороннего производителя. Поставщик Entity Framework следует использовать при работе с реляционным источником данных, таким как база данных SQL Server. Дополнительные сведения см. в разделе [поставщика Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md).|  
|Поставщик отражения|Этот поставщик использует отражение, позволяя определить модель данных на основе существующих классов данных, предоставляемых как экземпляры интерфейса <xref:System.Linq.IQueryable%601>. Обновления поддерживаются путем реализации интерфейса <xref:System.Data.Services.IUpdatable>. Этот поставщик следует использовать, если имеются статические классы данных, сформированные во время выполнения, например формируемые LINQ to SQL или определяемые типизированным набором данных. Дополнительные сведения см. в разделе [поставщик отражения](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md).|  
|Специализированные поставщики служб данных|В состав служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] также включен набор поставщиков, позволяющий динамически определить модель данных на основе типов данных с поздним связыванием. Эти интерфейсы следует реализовывать, если предоставляемые данные неизвестны на этапе разработки приложения или если использование Entity Framework или поставщиков отражения не является достаточным. Дополнительные сведения см. в разделе [настраиваемых поставщиков данных](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).|  
  
## <a name="other-data-service-providers"></a>Другие поставщики служб данных  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]имеет следующие дополнительные поставщики служб данных, позволяющие повысить производительность источника данных, определенного с помощью одного из других поставщиков.  
  
|Поставщик|Описание|  
|--------------|-----------------|  
|Потоковый поставщик|Этот поставщик позволяет предоставлять данные больших двоичных объектов с помощью служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Потоковый поставщик создается путем реализации интерфейса <xref:System.Data.Services.Providers.IDataServiceStreamProvider>. Этот поставщик можно реализовать совместно с любым другим поставщиком источника данных. Дополнительные сведения см. в разделе [потокового поставщика](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
## <a name="see-also"></a>См. также  
 [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)  
 [Размещение служб данных](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)
