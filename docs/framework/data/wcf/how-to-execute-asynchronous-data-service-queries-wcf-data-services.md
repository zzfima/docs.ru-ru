---
title: "Как выполнить асинхронные запросы службы данных (службы WCF Data Services) | Microsoft Docs"
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
  - "асинхронные операции [службы WCF Data Services]"
  - "Службы WCF Data Services, асинхронные операции"
ms.assetid: 902a2dc1-d0e9-4b00-90a8-becc4cb1f6a7
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как выполнить асинхронные запросы службы данных (службы WCF Data Services)
С помощью клиентской библиотеки [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] можно асинхронно выполнять операции «клиент\-сервер», например выполнение запросов и сохранение изменений. Дополнительные сведения см. в разделе [Асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
> [!NOTE]
>  В приложении, в котором метод обратного вызова должен быть вызван из определенного потока, необходимо выполнить явный маршалинг выполнения метода <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A>.  Для получения дополнительной информации см. [Асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Пример в этом разделе использует образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## Пример  
 Следующий пример иллюстрирует выполнение асинхронного запроса путем вызова метода <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> для запуска запроса.  Встроенный делегат вызывает метод <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> для отображения результатов запроса.  
  
 [!code-csharp[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#executequeryasync)]
 [!code-vb[Astoria Northwind Client#ExecuteQueryAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#executequeryasync)]  
  
## См. также  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)