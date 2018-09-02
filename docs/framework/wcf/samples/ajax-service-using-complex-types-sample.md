---
title: Образец службы AJAX, использующей сложные типы
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: 4574e5d33ebed7184e229c71e03496db34a95575
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415657"
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="f8e77-102">Образец службы AJAX, использующей сложные типы</span><span class="sxs-lookup"><span data-stu-id="f8e77-102">AJAX Service Using Complex Types Sample</span></span>
<span data-ttu-id="f8e77-103">В этом примере показано, как использовать Windows Communication Foundation (WCF) для создания служб ASP.NET асинхронных скриптов JavaScript и XML (AJAX), создающей экземпляры сложных типов и отправляющей их между службой и клиентом как нотации объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="f8e77-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="f8e77-104">К службе AJAX можно обращаться с помощью кода JavaScript из веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="f8e77-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="f8e77-105">Этот пример основан на [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) образца.</span><span class="sxs-lookup"><span data-stu-id="f8e77-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>  
  
 <span data-ttu-id="f8e77-106">Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX с помощью <xref:System.Web.UI.ScriptManager> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f8e77-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="f8e77-107">Пример использования WCF с ASP.NET AJAX, см. в разделе [образцы AJAX](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="f8e77-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](https://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8e77-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="f8e77-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="f8e77-109">Служба в следующем примере — это служба WCF без написания кода относящегося к AJAX.</span><span class="sxs-lookup"><span data-stu-id="f8e77-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span> <span data-ttu-id="f8e77-110">Поскольку атрибут <xref:System.ServiceModel.Web.WebGetAttribute> не применяется, используется HTTP-команда по умолчанию ("POST").</span><span class="sxs-lookup"><span data-stu-id="f8e77-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="f8e77-111">Служба имеет одну операцию, `DoMath`, возвращающую сложный тип с именем `MathResult`.</span><span class="sxs-lookup"><span data-stu-id="f8e77-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="f8e77-112">Сложный тип является стандартным типом контракта данных, также не содержащим код, относящийся к AJAX.</span><span class="sxs-lookup"><span data-stu-id="f8e77-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>  

```csharp
[DataContract]  
public class MathResult  
{  
    [DataMember]  
    public double sum;  
    [DataMember]  
    public double difference;  
    [DataMember]  
    public double product;  
    [DataMember]  
    public double quotient;  
}  
```

 <span data-ttu-id="f8e77-113">Создайте конечную точку AJAX в службе с помощью <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> точно так же, как в образце базовой службы AJAX.</span><span class="sxs-lookup"><span data-stu-id="f8e77-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>  
  
 <span data-ttu-id="f8e77-114">Клиентская веб-страница ComplexTypeClientPage.aspx содержит код ASP.NET и JavaScript для вызова службы, когда пользователь щелкает **выполнить расчет** кнопку на странице.</span><span class="sxs-lookup"><span data-stu-id="f8e77-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="f8e77-115">Код для вызова службы создает тело JSON и отправляет его с помощью HTTP POST, аналогичную [служба AJAX с помощью HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) образца.</span><span class="sxs-lookup"><span data-stu-id="f8e77-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>  
  
 <span data-ttu-id="f8e77-116">После успешного вызова службы можно получать доступ к отдельным членам данных (`sum`, `difference`, `product` и `quotient`) в полученном объекте JavaScript.</span><span class="sxs-lookup"><span data-stu-id="f8e77-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>  

```javascript
function onSuccess(mathResult){  
     document.getElementById("sum").value = mathResult.sum;  
     document.getElementById("difference").value = mathResult.difference;  
     document.getElementById("product").value = mathResult.product;  
     document.getElementById("quotient").value = mathResult.quotient;  
}  
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f8e77-117">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="f8e77-117">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f8e77-118">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8e77-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="f8e77-119">Построение решения complextypeajaxservice.sln, описанное в разделе [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f8e77-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="f8e77-120">Перейдите к http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (не открывайте ComplexTypeClientPage.aspx в браузере из каталога проекта).</span><span class="sxs-lookup"><span data-stu-id="f8e77-120">Navigate to http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8e77-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f8e77-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f8e77-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f8e77-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8e77-123">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="f8e77-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8e77-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f8e77-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`  
  
## <a name="see-also"></a><span data-ttu-id="f8e77-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f8e77-125">See Also</span></span>  
 [<span data-ttu-id="f8e77-126">Базовая служба AJAX</span><span class="sxs-lookup"><span data-stu-id="f8e77-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
