---
title: Образец службы AJAX, использующей сложные типы
ms.date: 03/30/2017
ms.assetid: 88242b99-4811-4cbe-8201-52ddf48fb174
ms.openlocfilehash: be8db36be7ed1639d839113174fdb95505466534
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716239"
---
# <a name="ajax-service-using-complex-types-sample"></a><span data-ttu-id="51ea3-102">Образец службы AJAX, использующей сложные типы</span><span class="sxs-lookup"><span data-stu-id="51ea3-102">AJAX Service Using Complex Types Sample</span></span>

<span data-ttu-id="51ea3-103">В этом примере демонстрируется использование Windows Communication Foundation (WCF) для создания асинхронной службы JavaScript и XML (AJAX) ASP.NET, которая создает экземпляры сложных типов и отправляет их между службой и клиентом как нотация объектов JavaScript (JSON).</span><span class="sxs-lookup"><span data-stu-id="51ea3-103">This sample demonstrates how to use Windows Communication Foundation (WCF) to create an ASP.NET Asynchronous JavaScript and XML (AJAX) service that creates instances of complex types and sends them between service and client as JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="51ea3-104">К службе AJAX можно обращаться с помощью кода JavaScript из веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="51ea3-104">You can access an AJAX service by using JavaScript code from a Web browser client.</span></span> <span data-ttu-id="51ea3-105">Этот пример основан на образце [базовой службы AJAX](../../../../docs/framework/wcf/samples/basic-ajax-service.md) .</span><span class="sxs-lookup"><span data-stu-id="51ea3-105">This sample builds on the [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) sample.</span></span>

<span data-ttu-id="51ea3-106">Поддержка AJAX в WCF оптимизирована для использования с ASP.NET AJAX через элемент управления <xref:System.Web.UI.ScriptManager>.</span><span class="sxs-lookup"><span data-stu-id="51ea3-106">AJAX support in WCF is optimized for use with ASP.NET AJAX through the <xref:System.Web.UI.ScriptManager> control.</span></span> <span data-ttu-id="51ea3-107">Пример использования WCF с ASP.NET AJAX см. в разделе [примеры AJAX](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="51ea3-107">For an example of using WCF with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>

> [!NOTE]
> <span data-ttu-id="51ea3-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="51ea3-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="51ea3-109">Служба в следующем примере представляет собой службу WCF без кода, зависящего от AJAX.</span><span class="sxs-lookup"><span data-stu-id="51ea3-109">The service in the following sample is a WCF service with no AJAX-specific code.</span></span> <span data-ttu-id="51ea3-110">Поскольку атрибут <xref:System.ServiceModel.Web.WebGetAttribute> не применяется, используется HTTP-команда по умолчанию ("POST").</span><span class="sxs-lookup"><span data-stu-id="51ea3-110">Because the <xref:System.ServiceModel.Web.WebGetAttribute> attribute is not applied, the default HTTP verb ("POST") is used.</span></span> <span data-ttu-id="51ea3-111">Служба имеет одну операцию, `DoMath`, возвращающую сложный тип с именем `MathResult`.</span><span class="sxs-lookup"><span data-stu-id="51ea3-111">The service has one operation, `DoMath`, which returns a complex type named `MathResult`.</span></span> <span data-ttu-id="51ea3-112">Сложный тип является стандартным типом контракта данных, также не содержащим код, относящийся к AJAX.</span><span class="sxs-lookup"><span data-stu-id="51ea3-112">The complex type is a standard data contract type, which also contains no AJAX-specific code.</span></span>

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

<span data-ttu-id="51ea3-113">Создайте конечную точку AJAX в службе с помощью <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> точно так же, как в образце базовой службы AJAX.</span><span class="sxs-lookup"><span data-stu-id="51ea3-113">Create an AJAX endpoint on the service by using the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, just as in the Basic AJAX Service sample.</span></span>

<span data-ttu-id="51ea3-114">Клиентская веб-страница Комплекстипеклиентпаже. aspx содержит код ASP.NET и JavaScript для вызова службы, когда пользователь нажимает кнопку **выполнить вычисление** на странице.</span><span class="sxs-lookup"><span data-stu-id="51ea3-114">The client Web page ComplexTypeClientPage.aspx contains ASP.NET and JavaScript code to invoke the service when the user clicks the **Perform calculation** button on the page.</span></span> <span data-ttu-id="51ea3-115">Код для вызова службы создает тело JSON и отправляет его с помощью HTTP POST, аналогично [службе AJAX с примером HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) .</span><span class="sxs-lookup"><span data-stu-id="51ea3-115">The code to invoke the service constructs a JSON body and sends it using HTTP POST, similar to the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md) sample.</span></span>

<span data-ttu-id="51ea3-116">После успешного вызова службы можно получать доступ к отдельным членам данных (`sum`, `difference`, `product` и `quotient`) в полученном объекте JavaScript.</span><span class="sxs-lookup"><span data-stu-id="51ea3-116">After the service call succeeds, you can access the individual data members (`sum`, `difference`, `product` and `quotient`) on the resulting JavaScript object.</span></span>

```javascript
function onSuccess(mathResult){
     document.getElementById("sum").value = mathResult.sum;
     document.getElementById("difference").value = mathResult.difference;
     document.getElementById("product").value = mathResult.product;
     document.getElementById("quotient").value = mathResult.quotient;
}
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="51ea3-117">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="51ea3-117">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="51ea3-118">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="51ea3-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="51ea3-119">Создайте решение Комплекстипеажакссервице. sln, как описано в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="51ea3-119">Build the solution ComplexTypeAjaxService.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="51ea3-120">Перейдите к `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (не открывайте Комплекстипеклиентпаже. aspx в браузере из каталога проекта).</span><span class="sxs-lookup"><span data-stu-id="51ea3-120">Navigate to `http://localhost/ServiceModelSamples/ComplexTypeClientPage.aspx` (do not open ComplexTypeClientPage.aspx in the browser from the project directory).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51ea3-121">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="51ea3-121">The samples may already be installed on your computer.</span></span> <span data-ttu-id="51ea3-122">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="51ea3-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="51ea3-123">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="51ea3-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="51ea3-124">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="51ea3-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ComplexTypeAjaxService`

## <a name="see-also"></a><span data-ttu-id="51ea3-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="51ea3-125">See also</span></span>

- [<span data-ttu-id="51ea3-126">Базовая служба AJAX</span><span class="sxs-lookup"><span data-stu-id="51ea3-126">Basic AJAX Service</span></span>](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
