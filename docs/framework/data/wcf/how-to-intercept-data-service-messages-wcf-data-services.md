---
title: "Как перехватить сообщения службы данных (службы WCF Data Services) | Microsoft Docs"
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
  - "перехватчики запросов [службы WCF Data Services]"
  - "Службы WCF Data Services, настройка"
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как перехватить сообщения службы данных (службы WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет приложению перехватывать сообщения запросов, что дает возможность добавить в операцию специализированную логику.  Для перехвата сообщений используются методы службы данных со специальными атрибутами.  Для получения дополнительной информации см. [Перехватчики](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).  
  
 В примере этого раздела используется образец службы данных Northwind.  Эта служба создается после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### Определение перехватчика запросов для набора сущностей Orders  
  
1.  Откройте в проекте службы данных Northwind файл Northwind.svc.  
  
2.  На странице кода класса `Northwind` добавьте следующую инструкцию `using` \(`Imports` в коде Visual Basic\):  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3.  Определите в классе `Northwind` метод операции службы с именем `OnQueryOrders`, как показано дальше:  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### Определение перехватчика изменений для набора сущностей Products  
  
1.  Откройте в проекте службы данных Northwind файл Northwind.svc.  
  
2.  Определите в классе `Northwind` метод операции службы с именем `OnChangeProducts`, как показано дальше:  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## Пример  
 Этот пример определяет метод перехватчика запросов для набора сущностей `Orders`, который возвращает лямбда\-выражение.  Это выражение содержит делегат, который фильтрует запрошенный набор сущностей `Orders` на основе связанных сущностей `Customers` с определенным именем контакта.  Имя в свою очередь определяется в зависимости от вызывающего пользователя.  Пример предполагает, что служба данных размещена в веб\-приложении ASP.NET, использующем WCF, и что проверка подлинности включена.  Класс <xref:System.Web.HttpContext> используется для извлечения участника текущего запроса.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## Пример  
 Этот пример определяет метод перехватчика изменений для набора сущностей `Products`.  Метод проверяет входные данные службы для операции <xref:System.Data.Services.UpdateOperations> или <xref:System.Data.Services.UpdateOperations> и формирует исключение, если изменение производится над отсутствующим продуктом.  Кроме того, удаление продуктов блокируется как неподдерживаемая операция.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## См. также  
 [Как определить операцию службы](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)   
 [Определение службы WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)