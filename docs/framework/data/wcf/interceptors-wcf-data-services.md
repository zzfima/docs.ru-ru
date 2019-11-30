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
ms.openlocfilehash: c9799037ae0ea8b29b5e989859aff29c310593d4
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568974"
---
# <a name="interceptors-wcf-data-services"></a>Перехватчики (службы данных WCF)
WCF Data Services позволяет приложению перехватывать сообщения запроса, чтобы можно было добавить в операцию пользовательскую логику. Эту пользовательскую логику можно использовать для проверки данных во входящих сообщениях. Можно также дальнейшим образом ограничить область запроса, например вставить специализированные правила проверки подлинности на основе отдельных запросов.  
  
 Перехват выполняется методами службы данных со специальными атрибутами. Эти методы вызываются WCF Data Services в соответствующей точке обработки сообщения. Перехватчики определяются для каждого набора сущностей, и методы перехватчика не могут принимать параметры запроса, например операции службы. Методы перехватчика запросов, которые вызываются при обработке HTTP-запроса GET, должны возвращать лямбда-выражение, определяющее, должен ли экземпляр набора сущностей перехватчика возвращаться в результатах запроса. Это выражение используется службой данных для дальнейшего уточнения запрошенного действия. В следующем примере рассмотрено определение перехватчика запроса.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
 [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
 Дополнительные сведения см. [в разделе как перехватывать сообщения службы данных](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Перехватчики изменений, которые вызываются при обработке операций, не связанных с запросами, должны возвращать значение `void` (`Nothing` в коде Visual Basic). Методы перехватчика изменений должны принимать следующие два параметра.  
  
1. Параметр типа, совместимого с типом сущностей в наборе сущностей. При вызове службой данных перехватчика изменений значение этого параметра будет отражать сведения о сущности, отправленные в запросе.  
  
2. Параметр типа <xref:System.Data.Services.UpdateOperations>. При вызове службой данных перехватчика изменений значение этого параметра будет отражать операцию, которую пытается выполнить запрос.  
  
 В следующем примере рассмотрено определение перехватчика изменений.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
 Дополнительные сведения см. [в разделе как перехватывать сообщения службы данных](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
 Для перехватчиков поддерживаются следующие атрибуты.  
  
 **[Куеринтерцептор (** *EntitySetName* **)]**  
 Методы с атрибутом <xref:System.Data.Services.QueryInterceptorAttribute> вызываются при получении запроса HTTP GET к целевому ресурсу набора сущностей. Эти методы всегда должны возвращать лямбда-выражение в форме `Expression<Func<T,bool>>`.  
  
 **[Чанжеинтерцептор (** *EntitySetName* **)]**  
 Методы с атрибутом <xref:System.Data.Services.ChangeInterceptorAttribute> вызываются при получении запроса HTTP, отличного от HTTP GET, к целевому ресурсу набора сущностей. Эти методы должны всегда возвращать значение `void` (`Nothing` в коде Visual Basic).  
  
 Дополнительные сведения см. [в разделе как перехватывать сообщения службы данных](how-to-intercept-data-service-messages-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также:

- [Операции служб](service-operations-wcf-data-services.md)
