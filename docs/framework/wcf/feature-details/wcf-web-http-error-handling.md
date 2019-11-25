---
title: Обработка ошибок веб-протокола HTTP WCF
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: 34912bccaefb645541f47d083c5c307b20ff77c5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975959"
---
# <a name="wcf-web-http-error-handling"></a>Обработка ошибок веб-протокола HTTP WCF
Обработка ошибок веб-протокола HTTP Windows Communication Foundation (WCF) позволяет возвращать ошибки из служб WCF Web HTTP, которые указывают код состояния HTTP и возвращают сведения об ошибке, используя тот же формат, что и операция (например, XML или JSON).  
  
## <a name="wcf-web-http-error-handling"></a>Обработка ошибок веб-протокола HTTP WCF  
 Класс <xref:System.ServiceModel.Web.WebFaultException> содержит конструктор, позволяющий указать код состояния HTTP. Затем этот код состояния возвращается клиенту. Общая версия класса <xref:System.ServiceModel.Web.WebFaultException>, <xref:System.ServiceModel.Web.WebFaultException%601> позволяет возвращать определенный пользователем тип, содержащий сведения о возникшей ошибке. Этот пользовательский объект сериализуется с помощью формата, указанного операцией и возвращенного клиенту. Следующий пример показывает, как вернуть код состояния HTTP.  
  
```csharp
public string Operation1()
{
    // Operation logic  
   // ...
   throw new WebFaultException(HttpStatusCode.Forbidden);
}  
```  
  
 В следующем примере показано, как вернуть код состояния HTTP и дополнительные сведения в типе, определяемом пользователем. `MyErrorDetail` - определяемый пользователем тип, который содержит дополнительные сведения о возникшей ошибке.  
  
```csharp
public string Operation2()
{
   // Operation logic  
   // ...
   MyErrorDetail detail = new MyErrorDetail()
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 В приведенном выше коде возвращается ответ HTTP с кодом состояния «доступ запрещен» и экземпляром объекта `MyErrorDetails` в теле ответа. Формат объекта `MyErrorDetails` определяется следующими элементами.  
  
- Значение параметра `ResponseFormat` атрибута <xref:System.ServiceModel.Web.WebGetAttribute> или <xref:System.ServiceModel.Web.WebInvokeAttribute>, указанного в операции службы.  
  
- Значение <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.  
  
- Значение свойства <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> при обращении к <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.  
  
 Дополнительные сведения о влиянии этих значений на форматирование операции см. в разделе [веб-форматирование WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).  
  
 Исключение <xref:System.ServiceModel.Web.WebFaultException> является <xref:System.ServiceModel.FaultException> и, следовательно, может быть использовано в качестве модели программирования ошибок для служб, предоставляющих конечные точки SOAP, а также сетевые конечные точки HTTP.  
  
## <a name="see-also"></a>См. также

- [Модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [Форматирование веб-объектов HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)
- [Определение и указание сбоев](../../../../docs/framework/wcf/defining-and-specifying-faults.md)
- [Обработка исключений и сбоев](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)
- [Сбои при отправке и получении](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
