---
title: "Обработка ошибок веб-протокола HTTP WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3c5f397d50a5a97801241afd8e64abf2e56b05dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-web-http-error-handling"></a>Обработка ошибок веб-протокола HTTP WCF
Обработка ошибок протокола HTTP в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет возвращать из веб-служб HTTP [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ошибки, указывающие код состояния HTTP, причем в том формате, который используется в операции, например XML или JSON.  
  
## <a name="wcf-web-http-error-handling"></a>Обработка ошибок веб-протокола HTTP WCF  
 Класс <xref:System.ServiceModel.Web.WebFaultException> содержит конструктор, позволяющий указать код состояния HTTP. Затем этот код состояния возвращается клиенту. Общая версия класса <xref:System.ServiceModel.Web.WebFaultException>, <xref:System.ServiceModel.Web.WebFaultException%601> позволяет возвращать определенный пользователем тип, содержащий сведения о возникшей ошибке. Этот пользовательский объект сериализуется с помощью формата, указанного операцией и возвращенного клиенту. Следующий пример показывает, как вернуть код состояния HTTP.  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 В следующем примере показано, как вернуть код состояния HTTP и дополнительные сведения в типе, определяемом пользователем. `MyErrorDetail` - определяемый пользователем тип, который содержит дополнительные сведения о возникшей ошибке.  
  
```  
Public string Operation2()  
   // Operation logic  
   // ...   MyErrorDetail detail = new MyErrorDetail  
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 В приведенном выше коде возвращается ответ HTTP с кодом состояния «доступ запрещен» и экземпляром объекта `MyErrorDetails` в теле ответа. Формат объекта `MyErrorDetails` определяется следующими элементами.  
  
-   Значение параметра `ResponseFormat` атрибута <xref:System.ServiceModel.Web.WebGetAttribute> или <xref:System.ServiceModel.Web.WebInvokeAttribute>, указанного в операции службы.  
  
-   Значение <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.  
  
-   Значение свойства <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> при обращении к <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Эти значения влияют на форматирование операции, разделе [WCF Web HTTP форматирование](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).  
  
 Исключение <xref:System.ServiceModel.Web.WebFaultException> является <xref:System.ServiceModel.FaultException> и, следовательно, может быть использовано в качестве модели программирования ошибок для служб, предоставляющих конечные точки SOAP, а также сетевые конечные точки HTTP.  
  
## <a name="see-also"></a>См. также  
 [Модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [Форматирование веб-объектов HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)  
 [Определение и указание сбоев](../../../../docs/framework/wcf/defining-and-specifying-faults.md)  
 [Обработка исключений и сбоев](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)  
 [Сбои при отправке и получении](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
