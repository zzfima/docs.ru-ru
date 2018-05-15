---
title: Использование стандартных конечных точек
ms.date: 03/30/2017
ms.assetid: ecd6a62f-9619-4778-a497-6f888087a9ea
ms.openlocfilehash: 10f7280383a7fe381b36db76b72f7d67ba39eb40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="usage-of-standard-endpoints"></a><span data-ttu-id="15dc4-102">Использование стандартных конечных точек</span><span class="sxs-lookup"><span data-stu-id="15dc4-102">Usage of Standard Endpoints</span></span>
<span data-ttu-id="15dc4-103">Этот образец демонстрирует использование стандартных конечных точек в файлах конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="15dc4-103">This sample demonstrates how to use standard endpoints in service configuration files.</span></span> <span data-ttu-id="15dc4-104">Стандартная конечная точка позволяет пользователю упростить определения конечных точек за счет использования единого свойства, описывающего комбинацию адреса, привязки и контракта вместе с дополнительными свойствами.</span><span class="sxs-lookup"><span data-stu-id="15dc4-104">A standard endpoint allows the user to simplify endpoint definitions by using a single property to describe an address, binding and contract combination with additional properties associated to it.</span></span> <span data-ttu-id="15dc4-105">Данный образец демонстрирует определение и реализацию пользовательской стандартной конечной точки, а также определение конкретных свойств в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="15dc4-105">This sample demonstrates how to define and implement a custom standard endpoint and how to define specific properties in the endpoint.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="15dc4-106">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="15dc4-106">Sample Details</span></span>  
 <span data-ttu-id="15dc4-107">Конечные точки службы могут быть заданы с использованием трех параметров: адреса, привязки и контракта.</span><span class="sxs-lookup"><span data-stu-id="15dc4-107">Service endpoints can be specified by supplying three parameters: address, binding and contract.</span></span> <span data-ttu-id="15dc4-108">Кроме того, можно задать и другие параметры - конфигурацию поведения, заголовки, URI прослушивания и т. д.</span><span class="sxs-lookup"><span data-stu-id="15dc4-108">Other parameters that can be supplied include behavior configuration, headers, listen URI, and so on.</span></span> <span data-ttu-id="15dc4-109">В некоторых случаях значения адресов, привязок или контрактов не могут меняться.</span><span class="sxs-lookup"><span data-stu-id="15dc4-109">In some cases, any or all of addresses, bindings and contracts have values that cannot change.</span></span> <span data-ttu-id="15dc4-110">В такой ситуации можно воспользоваться стандартными конечными точками.</span><span class="sxs-lookup"><span data-stu-id="15dc4-110">For this reason, it is possible to use standard endpoints.</span></span> <span data-ttu-id="15dc4-111">Среди примеров таких конечных точек - конечные точки обмена метаданными и конечные точки обнаружения.</span><span class="sxs-lookup"><span data-stu-id="15dc4-111">Some examples of such endpoints include metadata exchange endpoints and discovery endpoints.</span></span> <span data-ttu-id="15dc4-112">Стандартные конечные точки также повышают удобство использования, позволяя конфигурировать конечные точки службы, не предоставляя сведений фиксированного характера и не создавая для них собственных стандартных конечных точек. Это дает возможность, например, повысить удобство использования, предоставляя разумный набор значений по умолчанию и тем самым сокращая количество строк в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="15dc4-112">Standard endpoints also improve usability by allowing configuration of service endpoints without having to provide information of a fixed nature or to create their own standard endpoints, for example to improve usability by supplying a reasonable set of default values and thus reducing the verbosity of configuration files.</span></span>  
  
 <span data-ttu-id="15dc4-113">Данный образец состоит из двух проектов - службы, которая определяет две стандартных конечных точки, и клиента, который обращается к службе.</span><span class="sxs-lookup"><span data-stu-id="15dc4-113">This sample consists of two projects: the service that defines two standard endpoints and the client that communicates with the service.</span></span> <span data-ttu-id="15dc4-114">Метод определения стандартных конечных точек для этой службы в файле конфигурации показан в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="15dc4-114">The way the standard endpoints are defined for the service in the configuration file is show in the following example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <extensions>  
      <endpointExtensions>  
        <add name="customEndpoint" type="Microsoft.Samples.StandardEndpoints.CustomEndpointCollectionElement, service" />  
      </endpointExtensions>  
    </extensions>  
    <services>  
      <service name="Microsoft.Samples.StandardEndpoints.CalculatorService">  
        <endpoint address="http://localhost:8000/Samples/Service.svc/customEndpoint" contract="Microsoft.Samples.StandardEndpoints.ICalculator" kind="customEndpoint" />  
        <endpoint kind="mexEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <standardEndpoints>  
      <customEndpoint>  
        <standardEndpoint property="True" />  
      </customEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="15dc4-115">Первая конечная точка, определенная для службы, имеет тип `customEndpoint`, ее определение можно увидеть в разделе `<standardEndpoints>`, в котором свойству `property` задано значение `true`.</span><span class="sxs-lookup"><span data-stu-id="15dc4-115">The first endpoint defined for the service is of kind `customEndpoint`, whose definition can be seen in the `<standardEndpoints>` section, in which the property `property` is given the value `true`.</span></span> <span data-ttu-id="15dc4-116">Это пример конечной точки, дополненной новым свойством.</span><span class="sxs-lookup"><span data-stu-id="15dc4-116">This is the case of an endpoint customized with a new property.</span></span> <span data-ttu-id="15dc4-117">Вторая конечная точка соответствует конечной точке метаданных, и значения адреса, привязки и контракта в ней фиксированы.</span><span class="sxs-lookup"><span data-stu-id="15dc4-117">The second endpoint corresponds to a metadata endpoint, in which the values for address, binding and contract are fixed.</span></span>  
  
 <span data-ttu-id="15dc4-118">Для определения элемента стандартной конечной точки необходимо создать класс, производный от класса `StandardEndpointElement`.</span><span class="sxs-lookup"><span data-stu-id="15dc4-118">To define the standard endpoint element, a class that derives from `StandardEndpointElement` must be created.</span></span> <span data-ttu-id="15dc4-119">В нашем образце класс `CustomEndpointElement` определен, как показано в следующем фрагменте кода.</span><span class="sxs-lookup"><span data-stu-id="15dc4-119">In the case of this sample, the `CustomEndpointElement` class has been defined as shown in the following example.</span></span>  
  
```csharp  
public class CustomEndpointElement : StandardEndpointElement  
{  
    public bool Property  
    {  
        get { return (bool)base["property"]; }  
        set { base["property"] = value; }  
    }  
  
    protected override ConfigurationPropertyCollection Properties  
    {  
        get  
        {  
            ConfigurationPropertyCollection properties = base.Properties;  
            properties.Add(new ConfigurationProperty("property", typeof(bool), false, ConfigurationPropertyOptions.None));  
            return properties;  
        }  
    }  
  
    protected override Type EndpointType  
    {  
        get { return typeof(CustomEndpoint); }  
    }  
  
    protected override ServiceEndpoint CreateServiceEndpoint(ContractDescription contract)  
    {  
        return new CustomEndpoint();  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ServiceEndpointElement serviceEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnApplyConfiguration(ServiceEndpoint endpoint, ChannelEndpointElement channelEndpointElement)  
    {  
        CustomEndpoint customEndpoint = (CustomEndpoint)endpoint;  
        customEndpoint.Property = this.Property;  
    }  
  
    protected override void OnInitializeAndValidate(ServiceEndpointElement serviceEndpointElement)  
    {  
    }  
  
    protected override void OnInitializeAndValidate(ChannelEndpointElement channelEndpointElement)  
    {  
    }  
}  
```  
  
 <span data-ttu-id="15dc4-120">В функции `CreateServiceEndpoint` создается объект `CustomEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="15dc4-120">In the `CreateServiceEndpoint` function, a `CustomEndpoint` object is created.</span></span> <span data-ttu-id="15dc4-121">Его определение показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="15dc4-121">Its definition is shown in the following example.</span></span>  
  
```  
public class CustomEndpoint : ServiceEndpoint  
    {  
        public CustomEndpoint()  
            : this(string.Empty)  
        {  
        }  
  
        public CustomEndpoint(string address)  
            : this(address, ContractDescription.GetContract(typeof(ICalculator)))  
        {  
        }  
  
        public CustomEndpoint(string address, ContractDescription contract)  
            : base(contract)  
        {  
            this.Binding = new BasicHttpBinding();  
            this.IsSystemEndpoint = false;  
        }  
  
        public bool Property  
        {  
            get;  
            set;  
        }  
    }  
```  
  
 <span data-ttu-id="15dc4-122">Чтобы осуществить сообщение между службой и клиентом, в клиенте, обращающемся к службе, создается ссылка на службу.</span><span class="sxs-lookup"><span data-stu-id="15dc4-122">To perform the communication between service and client, a service reference is created in the client to the service.</span></span> <span data-ttu-id="15dc4-123">Когда образец построен и запущен, запускается и служба, и клиент сообщается с ней.</span><span class="sxs-lookup"><span data-stu-id="15dc4-123">When the sample is built and executed, the service executes and the client communicates with it.</span></span> <span data-ttu-id="15dc4-124">Обратите внимание, что ссылку на службу следует обновлять при каждом изменении службы.</span><span class="sxs-lookup"><span data-stu-id="15dc4-124">Note that the service reference should be updated every time there is some change in the service.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="15dc4-125">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="15dc4-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="15dc4-126">Откройте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] файл StandardEndpoints.sln.</span><span class="sxs-lookup"><span data-stu-id="15dc4-126">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the StandardEndpoints.sln file.</span></span>  
  
2.  <span data-ttu-id="15dc4-127">Разрешите запуск нескольких проектов.</span><span class="sxs-lookup"><span data-stu-id="15dc4-127">Enable multiple projects to start up.</span></span>  
  
    1.  <span data-ttu-id="15dc4-128">В **обозревателе решений**, щелкните правой кнопкой мыши решение стандартные конечные точки, а затем выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="15dc4-128">In **Solution Explorer**, right-click the Standard Endpoints solution and then select **Properties**.</span></span>  
  
    2.  <span data-ttu-id="15dc4-129">В **общие свойства**выберите **запускаемый проект**, а затем нажмите кнопку **несколько запускаемых проектов**.</span><span class="sxs-lookup"><span data-stu-id="15dc4-129">In **Common Properties**, select **Startup Project**, and then click **Multiple Startup Projects**.</span></span>  
  
    3.  <span data-ttu-id="15dc4-130">Переместить в начало списка, в проект службы с **действия** значение **запустить**.</span><span class="sxs-lookup"><span data-stu-id="15dc4-130">Move the Service project to the beginning of the list, with the **Action** set to **Start**.</span></span>  
  
    4.  <span data-ttu-id="15dc4-131">Переместить клиентский проект после обновления проекта, также с **действия** значение **запустить**.</span><span class="sxs-lookup"><span data-stu-id="15dc4-131">Move the Client project after the Service project, also with the **Action** set to **Start**.</span></span>  
  
         <span data-ttu-id="15dc4-132">Это указывает, что проект «Client» выполняется после проекта «Service».</span><span class="sxs-lookup"><span data-stu-id="15dc4-132">This specifies that the Client project is executed after the Service project.</span></span>  
  
3.  <span data-ttu-id="15dc4-133">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="15dc4-133">To run the solution, press F5.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="15dc4-134">Если эти действия не дают результата, то проверьте правильность настройки среды, выполнив следующие действия.</span><span class="sxs-lookup"><span data-stu-id="15dc4-134">If these steps do not work, then make sure that your environment has been properly set up, using the following steps.</span></span>  
>   
>  1.  <span data-ttu-id="15dc4-135">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="15dc4-135">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
> 2.  <span data-ttu-id="15dc4-136">Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="15dc4-136">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
> 3.  <span data-ttu-id="15dc4-137">Запуск образца одного или нескольких конфигураций на компьютере, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="15dc4-137">To run the sample in a single or multiple computer configurations, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="15dc4-138">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="15dc4-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="15dc4-139">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="15dc4-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="15dc4-140">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="15dc4-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="15dc4-141">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="15dc4-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\StandardEndpoints`  
  
## <a name="see-also"></a><span data-ttu-id="15dc4-142">См. также</span><span class="sxs-lookup"><span data-stu-id="15dc4-142">See Also</span></span>
