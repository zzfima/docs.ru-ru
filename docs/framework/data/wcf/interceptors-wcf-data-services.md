---
title: Перехватчики (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: e33ae8dc-8069-41d0-99a0-75ff28db7050
ms.openlocfilehash: c2086d451af72157785796052af123cd210ee036
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45969175"
---
# <a name="interceptors-wcf-data-services"></a>Перехватчики (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет приложению перехватывать сообщения запросов, таким образом, можно добавить пользовательскую логику в операцию. Эта логика можно использовать для проверки данных во входящих сообщениях. Можно также дальнейшим образом ограничить область запроса, например вставить специализированные правила проверки подлинности на основе отдельных запросов.  
  
 Перехват выполняется методами службы данных со специальными атрибутами. Эти методы вызываются службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] в соответствующие моменты обработки сообщений. Перехватчики определяются на основе набора сущностей, а методы перехватчика не может принимать параметры запроса, как операции службы. Методы перехвата запросов, которые вызываются при обработке запроса HTTP GET, необходимо возвращаемое лямбда-выражение, определяющее, имеет ли экземпляр сущностей перехватчика значение должен возвращаться в результатах запроса. Это выражение используется службой данных для дальнейшего уточнения запрошенного действия. В следующем примере рассмотрено определение перехватчика запроса.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Дополнительные сведения см. в разделе [как: перехватывать сообщения службы данных](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Перехватчики изменений, которые вызываются при обработке операций, не связанных с запросами, должны возвращать значение `void` (`Nothing` в коде Visual Basic). Методы перехватчика изменений должны принимать следующие два параметра.  
  
1.  Параметр типа, совместимого с типом сущностей в наборе сущностей. При вызове службой данных перехватчика изменений значение этого параметра будет отражать сведения о сущности, отправленные в запросе.  
  
2.  Параметр типа <xref:System.Data.Services.UpdateOperations>. При вызове службой данных перехватчика изменений значение этого параметра будет отражать операцию, которую пытается выполнить запрос.  
  
 В следующем примере рассмотрено определение перехватчика изменений.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Дополнительные сведения см. в разделе [как: перехватывать сообщения службы данных](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Для перехватчиков поддерживаются следующие атрибуты.  
  
 **[QueryInterceptor (** *EntitySetName* **)]**  
 Методы с атрибутом <xref:System.Data.Services.QueryInterceptorAttribute> вызываются при получении запроса HTTP GET к целевому ресурсу набора сущностей. Эти методы всегда должны возвращать лямбда-выражение в форме `Expression<Func<T,bool>>`.  
  
 **[ChangeInterceptor (** *EntitySetName* **)]**  
 Методы с атрибутом <xref:System.Data.Services.ChangeInterceptorAttribute> вызываются при получении запроса HTTP, отличного от HTTP GET, к целевому ресурсу набора сущностей. Эти методы должны всегда возвращать значение `void` (`Nothing` в коде Visual Basic).  
  
 Дополнительные сведения см. в разделе [как: перехватывать сообщения службы данных](../../../../docs/framework/data/wcf/how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также  
 [Операции служб](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)
