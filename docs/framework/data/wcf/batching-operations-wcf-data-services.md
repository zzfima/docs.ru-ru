---
title: Пакетные операции (службы данных WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
ms.openlocfilehash: 2a642bdfd6a8891c54c01a07609760bede2f5d5d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780498"
---
# <a name="batching-operations-wcf-data-services"></a>Пакетные операции (службы данных WCF)
Поддерживает пакетную обработку запросов к службе, [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]основанной на службах. [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Дополнительные сведения см. в [разделе OData: Пакетная](https://go.microsoft.com/fwlink/?LinkId=186075)обработка. В [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]каждая операция, <xref:System.Data.Services.Client.DataServiceContext>использующая, например выполнение запроса или сохранение изменений, приводит к отправке в службу данных отдельного запроса. Для создания логической области видимости для набора операций можно явно определить пакеты операций. Это гарантирует, что все операции в пакете отправляются в службу данных в одном HTTP-запросе, что позволяет серверу обрабатывать операции атомарно и сокращает количество обращений к службе данных.  
  
## <a name="batching-query-operations"></a>Операции пакетных запросов  
 Для выполнения нескольких запросов в одном пакете необходимо создать каждый запрос пакета в виде отдельного экземпляра класса <xref:System.Data.Services.Client.DataServiceRequest%601>. При создании запроса таким способом сам он определяется как URI и соответствует правилам адресации ресурсов. Дополнительные сведения см. в разделе [доступ к ресурсам службы данных](accessing-data-service-resources-wcf-data-services.md). Пакетные запросы отправляются в службу данных при вызове метода <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>, содержащего объекты запросов. Этот метод возвращает объект <xref:System.Data.Services.Client.DataServiceResponse>, представляющий собой коллекцию объектов <xref:System.Data.Services.Client.QueryOperationResponse%601>, каждый из которых содержит ответ на индивидуальный запрос в пакете, то есть либо коллекцию возвращаемых объектов, либо сведения об ошибке. Если отдельная операция в пакете завершается с ошибкой, сведения об ошибке возвращаются в объекте <xref:System.Data.Services.Client.QueryOperationResponse%601> для конкретной операции, в то время как оставшиеся операции все равно выполняются. Дополнительные сведения см. в разделе [Практическое руководство. Выполнение запросов в пакете](how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Пакетные запросы также могут быть выполнены асинхронно. Дополнительные сведения см. в разделе [асинхронные операции](asynchronous-operations-wcf-data-services.md).  
  
## <a name="batching-the-savechanges-operation"></a>Пакетирование операции SaveChanges  
 При вызове <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> метода все изменения, отслеживаемые контекстом, преобразуются в операции на основе RESTful, которые отправляются как [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] запросы к службе. По умолчанию эти изменения не отправляются в одном сообщении запроса. Чтобы обеспечить отправку всех изменений в одном запросе, необходимо вызвать <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> метод и включить <xref:System.Data.Services.Client.SaveChangesOptions.Batch> значение в <xref:System.Data.Services.Client.SaveChangesOptions> перечисление, предоставленное в метод.  
  
 Можно также сохранить пакет изменений асинхронно. Дополнительные сведения см. в разделе [асинхронные операции](asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](wcf-data-services-client-library.md)
