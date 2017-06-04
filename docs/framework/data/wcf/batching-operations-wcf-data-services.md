---
title: "Пакетные операции (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы WCF Data Services, клиентская библиотека"
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Пакетные операции (службы WCF Data Services)
Службы [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] поддерживают пакетную обработку запросов к службам на основе [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Дополнительные сведения см. в разделе [OData: пакетная обработка](http://go.microsoft.com/fwlink/?LinkId=186075). В [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] каждая операция, в которой используется контекст <xref:System.Data.Services.Client.DataServiceContext>, например выполнение запроса или сохранения изменений, приведет к созданию отдельного запроса к службе данных.  Для создания логической области видимости для набора операций можно явно определить пакеты операций.  При этом все операции в пакете гарантированно отправляются в службу данных в виде одного HTTP\-запроса, что позволяет серверу обработать их единым блоком и сокращает количество циклов обращений в службу данных.  
  
## Операции пакетных запросов  
 Для выполнения нескольких запросов в одном пакете необходимо создать каждый запрос пакета в виде отдельного экземпляра класса <xref:System.Data.Services.Client.DataServiceRequest%601>.  При создании запроса таким способом сам он определяется как URI и соответствует правилам адресации ресурсов.  Для получения дополнительной информации см. [Доступ к ресурсам службы данных](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md).  Пакетные запросы отправляются в службу данных при вызове метода <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>, содержащего объекты запросов.  Этот метод возвращает объект <xref:System.Data.Services.Client.DataServiceResponse>, представляющий собой коллекцию объектов <xref:System.Data.Services.Client.QueryOperationResponse%601>, каждый из которых содержит ответ на индивидуальный запрос в пакете, то есть либо коллекцию возвращаемых объектов, либо сведения об ошибке.  Если отдельная операция в пакете завершается с ошибкой, сведения об ошибке возвращаются в объекте <xref:System.Data.Services.Client.QueryOperationResponse%601> для конкретной операции, в то время как оставшиеся операции все равно выполняются.  Для получения дополнительной информации см. [Как выполнять запросы в пакете](../../../../docs/framework/data/wcf/how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Пакетные запросы также могут быть выполнены асинхронно.  Для получения дополнительной информации см. [Асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## Пакетирование операции SaveChanges  
 При вызове метода <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> все изменения, отслеженные контекстом, преобразуются в операции на основе REST, которые отправляются в качестве запросов службе [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  По умолчанию эти изменения не отправляются в одном сообщении запроса.  Чтобы принудительно отправить все изменения в одном запросе, необходимо вызвать метод <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> и включить значение <xref:System.Data.Services.Client.SaveChangesOptions> в перечисление <xref:System.Data.Services.Client.SaveChangesOptions>, передаваемое этому методу.  
  
 Можно также сохранить пакет изменений асинхронно.  Для получения дополнительной информации см. [Асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## См. также  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)