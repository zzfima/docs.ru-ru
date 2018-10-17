---
title: Проверка безопасности
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
author: BrucePerlerMS
ms.openlocfilehash: df056287c216b92fa0bcbab2bcbc9bedf799873c
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374460"
---
# <a name="security-validation"></a><span data-ttu-id="a880c-102">Проверка безопасности</span><span class="sxs-lookup"><span data-stu-id="a880c-102">Security Validation</span></span>
<span data-ttu-id="a880c-103">Этот образец показывает, как с помощью пользовательского поведения проверять службы на компьютере на соответствие определенным условиям.</span><span class="sxs-lookup"><span data-stu-id="a880c-103">This sample demonstrates how to use a custom behavior to validate services on a computer to ensure they meet specific criteria.</span></span> <span data-ttu-id="a880c-104">В этом образце службы проверяются с помощью пользовательского поведения путем сканирования каждой конечной точки службы и проверки, содержат ли они безопасные элементы привязки.</span><span class="sxs-lookup"><span data-stu-id="a880c-104">In this sample, services are validated by the custom behavior by scanning through each endpoint on the service and checking to see whether they contain secure binding elements.</span></span> <span data-ttu-id="a880c-105">Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="a880c-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a880c-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="a880c-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="endpoint-validation-custom-behavior"></a><span data-ttu-id="a880c-107">Пользовательское поведение проверки конечной точки</span><span class="sxs-lookup"><span data-stu-id="a880c-107">Endpoint Validation Custom Behavior</span></span>  
 <span data-ttu-id="a880c-108">Добавив код пользователя в метод `Validate`, содержащийся в интерфейсе <xref:System.ServiceModel.Description.IServiceBehavior>, для службы или конечной точки можно создать пользовательское поведение, позволяющее выполнять определенные пользователем действия.</span><span class="sxs-lookup"><span data-stu-id="a880c-108">By adding user code to the `Validate` method contained in the <xref:System.ServiceModel.Description.IServiceBehavior> interface, custom behavior can be given to a service or endpoint to perform user-defined actions.</span></span> <span data-ttu-id="a880c-109">Следующий код служит для перебора в цикле всех конечных точек, содержащихся в службе, и поиска безопасных привязок в коллекциях привязок конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a880c-109">The following code is used to loop through each endpoint contained in a service, which searches through their binding collections for secure bindings.</span></span>  
  
```csharp
public void Validate(ServiceDescription serviceDescription,   
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually, gathering their    
    // binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =   
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any   
        // secure binding elements. Transport, Asymmetric, and Symmetric      
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 <span data-ttu-id="a880c-110">При добавлении приведенного ниже кода в файл Web.config добавляется расширение поведения `serviceValidate` для распознавания службой.</span><span class="sxs-lookup"><span data-stu-id="a880c-110">Adding the following code to Web.config file adds the `serviceValidate` behavior extension for the service to recognize.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>  
...  
```  
  
 <span data-ttu-id="a880c-111">После того как расширение поведения добавлено в службу, можно добавить поведение `endpointValidate` в список поведений в файле Web.config и, таким образом, в службу.</span><span class="sxs-lookup"><span data-stu-id="a880c-111">Once the behavior extension is added to the service, it is now possible to add the `endpointValidate` behavior to the list of behaviors in the Web.config file and thus, to the service.</span></span>  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="a880c-112">Поведения и их расширения, добавленные в файл Web.config, применяют поведение к отдельным службам, а при добавлении в файл Machine.config поведение применяется ко всем службам, работающим на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a880c-112">Behaviors and their extensions that are added to the Web.config file apply behavior to individual services, while when added to the Machine.config file apply behavior to every service active on the computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a880c-113">При добавлении поведения во все службы предлагается перед внесением каких-либо изменений в файл Machine.config создать резервную копию этого файла.</span><span class="sxs-lookup"><span data-stu-id="a880c-113">When adding behavior to all services, it is suggested to backup the Machine.config file before making any change.</span></span>  
  
 <span data-ttu-id="a880c-114">Теперь запустите клиент, содержащийся в каталоге client\bin данного образца.</span><span class="sxs-lookup"><span data-stu-id="a880c-114">Now run the client provided in the client\bin directory of this sample.</span></span> <span data-ttu-id="a880c-115">Исключение возникает следующее сообщение об ошибке: «Запрашиваемая служба "http://localhost/servicemodelsamples/service.svc" не удалось активировать.»</span><span class="sxs-lookup"><span data-stu-id="a880c-115">An exception has occurs with the following message: "The requested service, 'http://localhost/servicemodelsamples/service.svc' could not be activated."</span></span> <span data-ttu-id="a880c-116">Это ожидаемая ситуация, так как поведение проверки конечной точки считает конечную точку небезопасной и запрещает запуск службы.</span><span class="sxs-lookup"><span data-stu-id="a880c-116">This is expected because an endpoint is considered insecure by the endpoint validating behavior and prevents the service from being started.</span></span> <span data-ttu-id="a880c-117">Поведение также создает внутреннее исключение, которое описывает, какая конечная точка является небезопасной, и записывает сообщение в системную программу Просмотр событий, в раздел источника "System.ServiceModel 4.0.0.0", категория "WebHost".</span><span class="sxs-lookup"><span data-stu-id="a880c-117">The behavior also throws an internal exception that describes which endpoint is insecure and writes a message to the system Event Viewer under the "System.ServiceModel 4.0.0.0" source and the "WebHost" category.</span></span> <span data-ttu-id="a880c-118">В данном образце можно также включить трассировку в службе.</span><span class="sxs-lookup"><span data-stu-id="a880c-118">It is also possible to turn on tracing on the service in this sample.</span></span> <span data-ttu-id="a880c-119">Это позволит конечному пользователю просматривать исключения, созданные поведением проверки конечных точек, открыв трассировки службы с помощью программы Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="a880c-119">This allows the user to view the exceptions thrown by endpoint validating behavior by opening the resulting service traces using the Service Trace Viewer tool.</span></span>  
  
#### <a name="to-view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a><span data-ttu-id="a880c-120">Просмотр сообщений исключения сбоя проверки конечной точки в программе Просмотр событий</span><span class="sxs-lookup"><span data-stu-id="a880c-120">To view failed endpoint validation exception messages in the Event Viewer</span></span>  
  
1.  <span data-ttu-id="a880c-121">Нажмите кнопку **запустить** меню и выберите **запуска...** .</span><span class="sxs-lookup"><span data-stu-id="a880c-121">Click the **Start** menu and select **Run…**.</span></span>  
  
2.  <span data-ttu-id="a880c-122">Тип `eventvwr` и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a880c-122">Type `eventvwr` and click **OK**.</span></span>  
  
3.  <span data-ttu-id="a880c-123">В окне просмотра событий щелкните **приложения**.</span><span class="sxs-lookup"><span data-stu-id="a880c-123">In the Event Viewer window, click **Application**.</span></span>  
  
4.  <span data-ttu-id="a880c-124">Дважды щелкните событие недавно добавленных «System.ServiceModel 4.0.0.0» в категории «WebHost» в **приложения** окно, чтобы просмотреть сообщения о небезопасных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="a880c-124">Double-click the recently added "System.ServiceModel 4.0.0.0" event under the "WebHost" category in the **Application** window to view insecure endpoint messages.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a880c-125">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="a880c-125">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a880c-126">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a880c-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="a880c-127">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a880c-127">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="a880c-128">Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="a880c-128">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a880c-129">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="a880c-129">The samples may already be installed on your computer.</span></span> <span data-ttu-id="a880c-130">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="a880c-130">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a880c-131">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="a880c-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a880c-132">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="a880c-132">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a><span data-ttu-id="a880c-133">См. также</span><span class="sxs-lookup"><span data-stu-id="a880c-133">See Also</span></span>  
 [<span data-ttu-id="a880c-134">Образцы наблюдения за AppFabric</span><span class="sxs-lookup"><span data-stu-id="a880c-134">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
