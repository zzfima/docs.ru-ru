---
title: "Пакетные операции (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3bcb29fa522f706f5500ab3cb12f956d5e2236b5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="batching-operations-wcf-data-services"></a>Пакетные операции (службы данных WCF)
[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Поддерживает пакетную обработку запросов для [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-служба на основе. Дополнительные сведения см. в разделе [OData: пакетная обработка](http://go.microsoft.com/fwlink/?LinkId=186075). В [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], каждая операция, использующая <xref:System.Data.Services.Client.DataServiceContext>, такие как выполнение запроса или сохранения изменений, порождает отдельный запрос, отправляемых в службу данных. Для создания логической области видимости для набора операций можно явно определить пакеты операций. Это гарантирует, что все операции в пакете, отправляются в службу данных в одном HTTP-запросе, позволяет серверу обработать их единым блоком и сокращает количество циклов приема-передачи в службу данных.  
  
## <a name="batching-query-operations"></a>Операции пакетных запросов  
 Для выполнения нескольких запросов в одном пакете необходимо создать каждый запрос пакета в виде отдельного экземпляра класса <xref:System.Data.Services.Client.DataServiceRequest%601>. При создании запроса таким способом сам он определяется как URI и соответствует правилам адресации ресурсов. Дополнительные сведения см. в разделе [доступ к ресурсам службы данных](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md). Пакетные запросы отправляются в службу данных при вызове метода <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>, содержащего объекты запросов. Этот метод возвращает объект <xref:System.Data.Services.Client.DataServiceResponse>, представляющий собой коллекцию объектов <xref:System.Data.Services.Client.QueryOperationResponse%601>, каждый из которых содержит ответ на индивидуальный запрос в пакете, то есть либо коллекцию возвращаемых объектов, либо сведения об ошибке. Если отдельная операция в пакете завершается с ошибкой, сведения об ошибке возвращаются в объекте <xref:System.Data.Services.Client.QueryOperationResponse%601> для конкретной операции, в то время как оставшиеся операции все равно выполняются. Дополнительные сведения см. в разделе [как: выполнение запросов в пакете](../../../../docs/framework/data/wcf/how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Пакетные запросы также могут быть выполнены асинхронно. Дополнительные сведения см. в разделе [асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## <a name="batching-the-savechanges-operation"></a>Пакетирование операции SaveChanges  
 При вызове <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> метод, все изменения, которые запрашивает контекст отслеживает преобразуются в операции на основе REST, которые отправляются в виде [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] службы. По умолчанию эти изменения не отправляются в одном сообщении запроса. Если требуется отправить все изменения в одном запросе, необходимо вызвать <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> метод и включить значение <xref:System.Data.Services.Client.SaveChangesOptions.Batch> в <xref:System.Data.Services.Client.SaveChangesOptions> перечисление, передаваемое этому методу.  
  
 Можно также сохранить пакет изменений асинхронно. Дополнительные сведения см. в разделе [асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
