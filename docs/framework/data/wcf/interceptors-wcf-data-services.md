---
title: "Перехватчики (службы данных WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7aad516b819723c97a40a016a46ddcbe0fcdf4d2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="interceptors-wcf-data-services"></a>Перехватчики (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]позволяет приложению перехватывать сообщения запросов, так что можно добавить пользовательскую логику в операцию. Эта пользовательская логика можно использовать для проверки данных во входящих сообщениях. Можно также дальнейшим образом ограничить область запроса, например вставить специализированные правила проверки подлинности на основе отдельных запросов.  
  
 Перехват выполняется методами службы данных со специальными атрибутами. Эти методы вызываются службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] в соответствующие моменты обработки сообщений. Перехватчики определяются на основе набора сущностей и методы перехватчика не принимают параметры из запроса, как операции службы. Методы перехвата запросов, которые вызываются при обработке запросов HTTP GET, должны возвращать лямбда-выражение, определяющее, является ли экземпляр сущностей перехватчика набора должны возвращаться в результатах запроса. Это выражение используется службой данных для дальнейшего уточнения запрошенного действия. В следующем примере рассмотрено определение перехватчика запроса.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Дополнительные сведения см. в разделе [как: перехват сообщений службы данных](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Перехватчики изменений, которые вызываются при обработке операций, не связанных с запросами, должны возвращать значение `void` (`Nothing` в коде Visual Basic). Методы перехватчика изменений должны принимать следующие два параметра.  
  
1.  Параметр типа, совместимого с типом сущностей в наборе сущностей. При вызове службой данных перехватчика изменений значение этого параметра будет отражать сведения о сущности, отправленные в запросе.  
  
2.  Параметр типа <xref:System.Data.Services.UpdateOperations>. При вызове службой данных перехватчика изменений значение этого параметра будет отражать операцию, которую пытается выполнить запрос.  
  
 В следующем примере рассмотрено определение перехватчика изменений.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Дополнительные сведения см. в разделе [как: перехват сообщений службы данных](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Для перехватчиков поддерживаются следующие атрибуты.  
  
 **[QueryInterceptor (** *EnitySetName* **)]**  
 Методы с атрибутом <xref:System.Data.Services.QueryInterceptorAttribute> вызываются при получении запроса HTTP GET к целевому ресурсу набора сущностей. Эти методы всегда должны возвращать лямбда-выражение в форме `Expression<Func<T,bool>>`.  
  
 **[ChangeInterceptor (** *EnitySetName* **)]**  
 Методы с атрибутом <xref:System.Data.Services.ChangeInterceptorAttribute> вызываются при получении запроса HTTP, отличного от HTTP GET, к целевому ресурсу набора сущностей. Эти методы должны всегда возвращать значение `void` (`Nothing` в коде Visual Basic).  
  
 Дополнительные сведения см. в разделе [как: перехват сообщений службы данных](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Операции службы](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)
