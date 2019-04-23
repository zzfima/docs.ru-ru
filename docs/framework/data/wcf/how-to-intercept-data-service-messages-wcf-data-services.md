---
title: Практическое руководство. Перехват сообщений службы данных (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- query interceptors [WCF Data Services]
ms.assetid: 24b9df1b-b54b-4795-a033-edf333675de6
ms.openlocfilehash: ad0673f72b1a81d6bcfaf0704ccd698eda7bb20c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59517851"
---
# <a name="how-to-intercept-data-service-messages-wcf-data-services"></a>Практическое руководство. Перехват сообщений службы данных (службы данных WCF)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет приложению перехватывать сообщения запросов, что дает возможность добавить в операцию специализированную логику. Для перехвата сообщений используются методы со специальными атрибутами в службе данных. Дополнительные сведения см. в разделе [перехватчики](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).  
  
 В примере этого раздела используется образец службы данных Northwind. Эта служба создается после завершения [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="to-define-a-query-interceptor-for-the-orders-entity-set"></a>Определение перехватчика запросов для набора сущностей Orders  
  
1. Откройте в проекте службы данных Northwind файл Northwind.svc.  
  
2. На странице кода класса `Northwind` добавьте следующую инструкцию `using` (`Imports` в коде Visual Basic):  
  
     [!code-csharp[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#usinglinqexpressions)]
     [!code-vb[Astoria Northwind Service#UsingLinqExpressions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#usinglinqexpressions)]  
  
3. Определите в классе `Northwind` метод операции службы с именем `OnQueryOrders`, как показано дальше:  
  
     [!code-csharp[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptordef)]
     [!code-vb[Astoria Northwind Service#QueryInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptordef)]  
  
### <a name="to-define-a-change-interceptor-for-the-products-entity-set"></a>Определение перехватчика изменений для набора сущностей Products  
  
1. Откройте в проекте службы данных Northwind файл Northwind.svc.  
  
2. Определите в классе `Northwind` метод операции службы с именем `OnChangeProducts`, как показано дальше:  
  
     [!code-csharp[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptordef)]
     [!code-vb[Astoria Northwind Service#ChangeInterceptorDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptordef)]  
  
## <a name="example"></a>Пример  
 Этот пример определяет метод перехватчика запросов для набора сущностей `Orders`, который возвращает лямбда-выражение. Это выражение содержит делегат, который фильтрует запрошенный набор сущностей `Orders` на основе связанных сущностей `Customers` с определенным именем контакта. Имя в свою очередь определяется в зависимости от вызывающего пользователя. Пример предполагает, что служба данных размещена в веб-приложении ASP.NET, использующем WCF, и что проверка подлинности включена. Класс <xref:System.Web.HttpContext> используется для извлечения участника текущего запроса.  
  
 [!code-csharp[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#queryinterceptor)]
 [!code-vb[Astoria Northwind Service#QueryInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#queryinterceptor)]  
  
## <a name="example"></a>Пример  
 Этот пример определяет метод перехватчика изменений для набора сущностей `Products`. Метод проверяет входные данные службы для операции <xref:System.Data.Services.UpdateOperations.Add> или <xref:System.Data.Services.UpdateOperations.Change> и формирует исключение, если изменение производится над отсутствующим продуктом. Кроме того, удаление продуктов блокируется как неподдерживаемая операция.  
  
 [!code-csharp[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#changeinterceptor)]
 [!code-vb[Astoria Northwind Service#ChangeInterceptor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#changeinterceptor)]  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Определение операции службы](../../../../docs/framework/data/wcf/how-to-define-a-service-operation-wcf-data-services.md)
- [Определение служб данных WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
