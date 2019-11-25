---
title: Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX
ms.date: 03/30/2017
ms.assetid: 7cd0099e-dc3a-47e4-a38c-6e10f997f6ea
ms.openlocfilehash: 3ccfb34614707c17885da3ed37f545bbab808869
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978264"
---
# <a name="how-to-use-configuration-to-add-an-aspnet-ajax-endpoint"></a><span data-ttu-id="a840c-102">Практическое руководство. Использование конфигурации для добавления конечной точки ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="a840c-102">How to: Use Configuration to Add an ASP.NET AJAX Endpoint</span></span>
<span data-ttu-id="a840c-103">Windows Communication Foundation (WCF) позволяет создать службу, которая делает доступной конечную точку ASP.NET с поддержкой AJAX, которую можно вызывать из JavaScript на веб-сайте клиента.</span><span class="sxs-lookup"><span data-stu-id="a840c-103">Windows Communication Foundation (WCF) allows you to create a service that makes an ASP.NET AJAX-enabled endpoint available that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="a840c-104">Чтобы создать такую конечную точку, можно использовать файл конфигурации, как и для всех остальных конечных точек Windows Communication Foundation (WCF), или использовать метод, который не требует каких-либо элементов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a840c-104">To create such an endpoint, you can either use a configuration file, as with all other Windows Communication Foundation (WCF) endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="a840c-105">В этом разделе показано выполнение этой задачи с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a840c-105">This topic demonstrates the configuration approach.</span></span>  
  
 <span data-ttu-id="a840c-106">Часть процедуры, включающая конечную точку службы, ASP.NET с поддержкой AJAX, состоит в настройке конечной точки для использования <xref:System.ServiceModel.WebHttpBinding> и добавлении [\<ного](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведения конечной точки >.</span><span class="sxs-lookup"><span data-stu-id="a840c-106">The part of the procedure that enables the service endpoint to become ASP.NET AJAX-enabled consists of configuring the endpoint to use the <xref:System.ServiceModel.WebHttpBinding> and to add the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) endpoint behavior.</span></span> <span data-ttu-id="a840c-107">После настройки конечной точки действия по внедрению и размещению службы похожи на те, которые используются любой службой WCF.</span><span class="sxs-lookup"><span data-stu-id="a840c-107">After configuring the endpoint, the steps to implement and host the service are similar to those used by any WCF service.</span></span> <span data-ttu-id="a840c-108">Рабочий пример см. в разделе [Служба AJAX, использующая HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="a840c-108">For a working example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
 <span data-ttu-id="a840c-109">Дополнительные сведения о настройке конечной точки ASP.NET AJAX без использования конфигурации см. [в разделе инструкции. Добавление конечной точки ASP.NET AJAX без использования конфигурации](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a840c-109">For more information about how to configure an ASP.NET AJAX endpoint without using configuration, see [How to: Add an ASP.NET AJAX Endpoint Without Using Configuration](../../../../docs/framework/wcf/feature-details/how-to-add-an-aspnet-ajax-endpoint-without-using-configuration.md).</span></span>  
  
## <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="a840c-110">Создание базовой службы WCF</span><span class="sxs-lookup"><span data-stu-id="a840c-110">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="a840c-111">Определите базовый контракт службы WCF с интерфейсом, помеченным атрибутом <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a840c-111">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="a840c-112">Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a840c-112">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="a840c-113">Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="a840c-113">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```csharp
    [ServiceContract(Namespace = "MyService")]  
    public interface ICalculator  
    {  
        [OperationContract]  
         // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="a840c-114">Реализуйте контракт службы `ICalculator` с помощью класса `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="a840c-114">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }
        // Other operations omitted…
    }
    ```  
  
3. <span data-ttu-id="a840c-115">Определите пространство имен для реализаций `ICalculator` и `CalculatorService`, заключив их в блок пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a840c-115">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp
    namespace Microsoft.Ajax.Samples
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
## <a name="to-create-an-aspnet-ajax-endpoint-for-the-service"></a><span data-ttu-id="a840c-116">Создание конечной точки ASP.NET AJAX для службы</span><span class="sxs-lookup"><span data-stu-id="a840c-116">To create an ASP.NET AJAX endpoint for the service</span></span>  
  
1. <span data-ttu-id="a840c-117">Создайте конфигурацию поведения и укажите [\<енаблевебскрипт >](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведением для конечных точек службы ASP.NET с поддержкой AJAX.</span><span class="sxs-lookup"><span data-stu-id="a840c-117">Create a behavior configuration and specify the [\<enableWebScript>](../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) behavior for ASP.NET AJAX-enabled endpoints of the service.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="AspNetAjaxBehavior">  
                    <enableWebScript />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
    </system.serviceModel>  
    ```  
  
2. <span data-ttu-id="a840c-118">Создайте конечную точку для службы, использующую <xref:System.ServiceModel.WebHttpBinding> и поведение ASP.NET AJAX, определенное на предыдущем шаге.</span><span class="sxs-lookup"><span data-stu-id="a840c-118">Create an endpoint for the service that uses the <xref:System.ServiceModel.WebHttpBinding> and the ASP.NET AJAX behavior defined in the previous step.</span></span>  
  
    ```xml  
    <system.serviceModel>  
        <services>  
            <service name="Microsoft.Ajax.Samples.CalculatorService">  
                <endpoint address=""  
                    behaviorConfiguration="AspNetAjaxBehavior"   
                    binding="webHttpBinding"  
                    contract="Microsoft.Ajax.Samples.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>   
    ```  
  
## <a name="to-host-the-service-in-iis"></a><span data-ttu-id="a840c-119">Размещение службы в IIS</span><span class="sxs-lookup"><span data-stu-id="a840c-119">To host the service in IIS</span></span>  
  
1. <span data-ttu-id="a840c-120">Чтобы разместить службу в IIS, создайте в приложении файл с именем, соответствующем имени службы, и с расширением SVC.</span><span class="sxs-lookup"><span data-stu-id="a840c-120">To host the service in IIS, create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="a840c-121">Измените этот файл, добавив соответствующие сведения об директиве [ServiceHost\@](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) для службы.</span><span class="sxs-lookup"><span data-stu-id="a840c-121">Edit this file by adding the appropriate [\@ServiceHost](../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="a840c-122">Например, файл службы для нашего примера `CalculatorService` содержит следующую информацию.</span><span class="sxs-lookup"><span data-stu-id="a840c-122">For example, the content in the service file for the `CalculatorService` sample contains the following information.</span></span>  
  
    ```
    <%@ServiceHost   
    language=c#   
    Debug="true"   
    Service="Microsoft.Ajax.Samples.CalculatorService"  
    %>  
    ```  
  
2. <span data-ttu-id="a840c-123">Дополнительные сведения о размещении в службах IIS см. в разделе [как разместить службу WCF в IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="a840c-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
## <a name="to-call-the-service"></a><span data-ttu-id="a840c-124">Вызов службы</span><span class="sxs-lookup"><span data-stu-id="a840c-124">To call the service</span></span>  
  
1. <span data-ttu-id="a840c-125">Конечная точка настраивается по пустому адресу относительно SVC-файла, поэтому служба доступна и может быть вызвана при отправке запросов к службе. svc/\<операции > (например, Service. svc/Add для `Add` операции).</span><span class="sxs-lookup"><span data-stu-id="a840c-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="a840c-126">Для этого укажите URL-адрес конечной точки в коллекции "Скрипты" в диспетчере скриптов ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="a840c-126">You can use it by entering the endpoint URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="a840c-127">Пример см. в разделе [Служба AJAX, использующая HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span><span class="sxs-lookup"><span data-stu-id="a840c-127">For an example, see the [AJAX Service Using HTTP POST](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a840c-128">См. также</span><span class="sxs-lookup"><span data-stu-id="a840c-128">See also</span></span>

- [<span data-ttu-id="a840c-129">Создание служб WCF для ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="a840c-129">Creating WCF Services for ASP.NET AJAX</span></span>](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="a840c-130">Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="a840c-130">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
