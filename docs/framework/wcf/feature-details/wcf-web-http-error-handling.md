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
# <a name="wcf-web-http-error-handling"></a><span data-ttu-id="72300-102">Обработка ошибок веб-протокола HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="72300-102">WCF Web HTTP Error Handling</span></span>
<span data-ttu-id="72300-103">Обработка ошибок веб-протокола HTTP Windows Communication Foundation (WCF) позволяет возвращать ошибки из служб WCF Web HTTP, которые указывают код состояния HTTP и возвращают сведения об ошибке, используя тот же формат, что и операция (например, XML или JSON).</span><span class="sxs-lookup"><span data-stu-id="72300-103">Windows Communication Foundation (WCF) Web HTTP error handling enables you to return errors from WCF Web HTTP services that specify an HTTP status code and return error details using the same format as the operation (for example, XML or JSON).</span></span>  
  
## <a name="wcf-web-http-error-handling"></a><span data-ttu-id="72300-104">Обработка ошибок веб-протокола HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="72300-104">WCF Web HTTP Error Handling</span></span>  
 <span data-ttu-id="72300-105">Класс <xref:System.ServiceModel.Web.WebFaultException> содержит конструктор, позволяющий указать код состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="72300-105">The <xref:System.ServiceModel.Web.WebFaultException> class defines a constructor that allows you to specify an HTTP status code.</span></span> <span data-ttu-id="72300-106">Затем этот код состояния возвращается клиенту.</span><span class="sxs-lookup"><span data-stu-id="72300-106">This status code is then returned to the client.</span></span> <span data-ttu-id="72300-107">Общая версия класса <xref:System.ServiceModel.Web.WebFaultException>, <xref:System.ServiceModel.Web.WebFaultException%601> позволяет возвращать определенный пользователем тип, содержащий сведения о возникшей ошибке.</span><span class="sxs-lookup"><span data-stu-id="72300-107">A generic version of the <xref:System.ServiceModel.Web.WebFaultException> class, <xref:System.ServiceModel.Web.WebFaultException%601> enables you to return a user-defined type that contains information about the error that occurred.</span></span> <span data-ttu-id="72300-108">Этот пользовательский объект сериализуется с помощью формата, указанного операцией и возвращенного клиенту.</span><span class="sxs-lookup"><span data-stu-id="72300-108">This custom object is serialized using the format specified by the operation and returned to the client.</span></span> <span data-ttu-id="72300-109">Следующий пример показывает, как вернуть код состояния HTTP.</span><span class="sxs-lookup"><span data-stu-id="72300-109">The following example shows how to return an HTTP status code.</span></span>  
  
```csharp
public string Operation1()
{
    // Operation logic  
   // ...
   throw new WebFaultException(HttpStatusCode.Forbidden);
}  
```  
  
 <span data-ttu-id="72300-110">В следующем примере показано, как вернуть код состояния HTTP и дополнительные сведения в типе, определяемом пользователем.</span><span class="sxs-lookup"><span data-stu-id="72300-110">The following example shows how to return an HTTP status code and extra information in a user-defined type.</span></span> <span data-ttu-id="72300-111">`MyErrorDetail` - определяемый пользователем тип, который содержит дополнительные сведения о возникшей ошибке.</span><span class="sxs-lookup"><span data-stu-id="72300-111">`MyErrorDetail` is a user-defined type that contains extra information about the error that occurred.</span></span>  
  
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
  
 <span data-ttu-id="72300-112">В приведенном выше коде возвращается ответ HTTP с кодом состояния «доступ запрещен» и экземпляром объекта `MyErrorDetails` в теле ответа.</span><span class="sxs-lookup"><span data-stu-id="72300-112">The preceding code returns an HTTP response with the forbidden status code and a body that contains an instance of the `MyErrorDetails` object.</span></span> <span data-ttu-id="72300-113">Формат объекта `MyErrorDetails` определяется следующими элементами.</span><span class="sxs-lookup"><span data-stu-id="72300-113">The format of the `MyErrorDetails` object is determined by:</span></span>  
  
- <span data-ttu-id="72300-114">Значение параметра `ResponseFormat` атрибута <xref:System.ServiceModel.Web.WebGetAttribute> или <xref:System.ServiceModel.Web.WebInvokeAttribute>, указанного в операции службы.</span><span class="sxs-lookup"><span data-stu-id="72300-114">The value of the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute specified on the service operation.</span></span>  
  
- <span data-ttu-id="72300-115">Значение <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="72300-115">The value of <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span></span>  
  
- <span data-ttu-id="72300-116">Значение свойства <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> при обращении к <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span><span class="sxs-lookup"><span data-stu-id="72300-116">The value of the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property by accessing the <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span></span>  
  
 <span data-ttu-id="72300-117">Дополнительные сведения о влиянии этих значений на форматирование операции см. в разделе [веб-форматирование WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="72300-117">For more information about how these values affect the formatting of the operation, see [WCF Web HTTP Formatting](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>  
  
 <span data-ttu-id="72300-118">Исключение <xref:System.ServiceModel.Web.WebFaultException> является <xref:System.ServiceModel.FaultException> и, следовательно, может быть использовано в качестве модели программирования ошибок для служб, предоставляющих конечные точки SOAP, а также сетевые конечные точки HTTP.</span><span class="sxs-lookup"><span data-stu-id="72300-118"><xref:System.ServiceModel.Web.WebFaultException> is a <xref:System.ServiceModel.FaultException> and therefore can be used as the fault exception programming model for services that expose SOAP endpoints as well as web HTTP endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72300-119">См. также</span><span class="sxs-lookup"><span data-stu-id="72300-119">See also</span></span>

- [<span data-ttu-id="72300-120">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="72300-120">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="72300-121">Форматирование веб-объектов HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="72300-121">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)
- [<span data-ttu-id="72300-122">Определение и указание сбоев</span><span class="sxs-lookup"><span data-stu-id="72300-122">Defining and Specifying Faults</span></span>](../../../../docs/framework/wcf/defining-and-specifying-faults.md)
- [<span data-ttu-id="72300-123">Обработка исключений и сбоев</span><span class="sxs-lookup"><span data-stu-id="72300-123">Handling Exceptions and Faults</span></span>](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)
- [<span data-ttu-id="72300-124">Сбои при отправке и получении</span><span class="sxs-lookup"><span data-stu-id="72300-124">Sending and Receiving Faults</span></span>](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
