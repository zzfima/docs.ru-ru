---
title: Обработка ошибок веб-протокола HTTP WCF
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: 834c642e36e1551081dbe1f14529ed7596df1360
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152702"
---
# <a name="wcf-web-http-error-handling"></a>Обработка ошибок веб-протокола HTTP WCF
Обработка ошибок Web HTTP Windows Communication Foundation (WCF) позволяет возвращать ошибки из службы WCF Web HTTP, которые указывают код состояния HTTP и возвращают сведения об ошибке, используя формат операции (например, XML или JSON).  
  
## <a name="wcf-web-http-error-handling"></a>Обработка ошибок веб-протокола HTTP WCF  
 Класс <xref:System.ServiceModel.Web.WebFaultException> содержит конструктор, позволяющий указать код состояния HTTP. Затем этот код состояния возвращается клиенту. Общая версия класса <xref:System.ServiceModel.Web.WebFaultException>, <xref:System.ServiceModel.Web.WebFaultException%601> позволяет возвращать определенный пользователем тип, содержащий сведения о возникшей ошибке. Этот пользовательский объект сериализуется с помощью формата, указанного операцией и возвращенного клиенту. Следующий пример показывает, как вернуть код состояния HTTP.  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 В следующем примере показано, как вернуть код состояния HTTP и дополнительные сведения в типе, определяемом пользователем. `MyErrorDetail` является определяемого пользователем типа, который содержит дополнительные сведения о возникшей ошибке.  
  
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
  
 Дополнительные сведения о том, как эти значения влияют на форматирование операции см. в разделе [WCF Web HTTP форматирование](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).  
  
 <xref:System.ServiceModel.Web.WebFaultException> является <xref:System.ServiceModel.FaultException> и поэтому может использоваться как модель программирования исключения сбоя для служб, предоставляющих конечные точки SOAP, а также сетевые конечные точки HTTP.  
  
## <a name="see-also"></a>См. также

- [Модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [Форматирование веб-объектов HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)
- [Определение и задание сбоев](../../../../docs/framework/wcf/defining-and-specifying-faults.md)
- [Обработка исключений и сбоев](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)
- [Сбои при отправке и получении](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
