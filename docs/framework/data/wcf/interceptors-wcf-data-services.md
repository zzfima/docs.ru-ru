---
title: "Перехватчики (службы WCF Data Services) | Microsoft Docs"
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
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Перехватчики (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют приложению перехватывать сообщения запросов, что дает возможность добавить в операцию специализированную логику.  Эта логика может применяться для проверки данных во входящих сообщениях.  Можно также дальнейшим образом ограничить область запроса, например вставить специализированные правила проверки подлинности на основе отдельных запросов.  
  
 Перехват выполняется методами службы данных со специальными атрибутами.  Эти методы вызываются службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] в соответствующие моменты обработки сообщений.  Перехватчики определяются индивидуально для наборов сущностей. Методы перехватчика, в отличие от операций службы, не принимают параметры из запроса.  Методы перехвата запросов, которые вызываются при обработке запросов HTTP GET, должны возвращать лямбда\-выражение, определяющее, должен ли экземпляр набора сущностей перехватчика возвращаться в результатах запроса.  Это выражение используется службой данных для дальнейшего уточнения запрошенного действия.  В следующем примере рассмотрено определение перехватчика запроса.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Для получения дополнительной информации см. [Как перехватить сообщения службы данных](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Перехватчики изменений, которые вызываются при обработке операций, не связанных с запросами, должны возвращать значение `void` \(`Nothing` в коде Visual Basic\).  Методы перехватчика изменений должны принимать следующие два параметра.  
  
1.  Параметр типа, совместимого с типом сущностей в наборе сущностей.  При вызове службой данных перехватчика изменений значение этого параметра будет отражать сведения о сущности, отправленные в запросе.  
  
2.  Параметр типа <xref:System.Data.Services.UpdateOperations>.  При вызове службой данных перехватчика изменений значение этого параметра будет отражать операцию, которую пытается выполнить запрос.  
  
 В следующем примере рассмотрено определение перехватчика изменений.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Для получения дополнительной информации см. [Как перехватить сообщения службы данных](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Для перехватчиков поддерживаются следующие атрибуты.  
  
 **\[QueryInterceptor\(** *EnitySetName* **\)\]**  
 Методы с атрибутом <xref:System.Data.Services.QueryInterceptorAttribute> вызываются при получении запроса HTTP GET к целевому ресурсу набора сущностей.  Эти методы всегда должны возвращать лямбда\-выражение в форме `Expression<Func<T,bool>>`.  
  
 **\[ChangeInterceptor\(** *EnitySetName* **\)\]**  
 Методы с атрибутом <xref:System.Data.Services.ChangeInterceptorAttribute> вызываются при получении запроса HTTP, отличного от HTTP GET, к целевому ресурсу набора сущностей.  Эти методы должны всегда возвращать значение `void` \(`Nothing` в коде Visual Basic\).  
  
 Для получения дополнительной информации см. [Как перехватить сообщения службы данных](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## См. также  
 [Операции служб](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)