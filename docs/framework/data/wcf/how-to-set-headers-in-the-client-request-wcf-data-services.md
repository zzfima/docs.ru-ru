---
title: "Как установить заголовки в клиентском запросе (службы WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, настройка запросов"
ms.assetid: 3d55168d-5901-4f48-8117-6c93da3ab5ae
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как установить заголовки в клиентском запросе (службы WCF Data Services)
При использовании клиентской библиотеки [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для доступа к службе данных, которая поддерживает [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], клиентская библиотека автоматически устанавливает необходимые заголовки HTTP в запросах, отправляемых службе данных.  Однако клиентская библиотека не может определить заголовки сообщений, которые необходимы в некоторых случаях, например когда службе данных требуется проверка подлинности на основе утверждений или файлы cookies.  Дополнительные сведения см. в разделе [Защита служб WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md#clientAuthentication).  В этих случаях необходимо вручную установить заголовки сообщений в запросе перед отправкой.  В примере в этом разделе показано, как обработать событие <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> и добавить новый заголовок в сообщение запроса перед его отправкой службе данных.  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  Можно также использовать [образец службы данных Northwind](http://go.microsoft.com/fwlink/?LinkId=187426), опубликованный на веб\-узле [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Этот образец службы данных доступен только для чтения, попытка сохранить изменения возвращает ошибку.  Образцы служб данных на веб\-узле [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] допускают анонимную проверку подлинности.  
  
## Пример  
 В следующем примере регистрируется обработчик для события <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>, после чего службе данных отправляется запрос.  
  
> [!NOTE]
>  Если служба данных требует задавать заголовок сообщения вручную для каждого запроса, попробуйте зарегистрировать обработчик для события <xref:System.Data.Services.Client.DataServiceContext.SendingRequest>, переопределив частичный метод `OnContextCreated` в контейнере сущностей, который представляет службу данных, то есть в данном примере `NorthwindEntities`.  
  
 [!code-csharp[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#registerheadersquery)]
 [!code-vb[Astoria Northwind Client#RegisterHeadersQuery](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#registerheadersquery)]  
  
## Пример  
 Следующей метод обрабатывает событие <xref:System.Data.Services.Client.DataServiceContext.SendingRequest> и добавляет заголовок проверки подлинности в запрос.  
  
 [!code-csharp[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#onsendingrequest)]
 [!code-vb[Astoria Northwind Client#OnSendingRequest](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#onsendingrequest)]  
  
## См. также  
 [Защита служб WCF Data Services](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)   
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)