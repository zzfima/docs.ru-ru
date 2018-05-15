---
title: Привязка NetTcpBinding по умолчанию
ms.date: 03/30/2017
helpviewer_keywords:
- Net profile TCP
ms.assetid: e8475fe6-0ecd-407a-8e7e-45860561bb74
ms.openlocfilehash: b51178c8ba84740598db62b9011fa33da318ca8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="default-nettcpbinding"></a><span data-ttu-id="9f65d-102">Привязка NetTcpBinding по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9f65d-102">Default NetTcpBinding</span></span>
<span data-ttu-id="9f65d-103">В этом образце демонстрируется использование привязки <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="9f65d-103">This sample demonstrates the use of the <xref:System.ServiceModel.NetTcpBinding> binding.</span></span> <span data-ttu-id="9f65d-104">Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="9f65d-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="9f65d-105">В этом образце служба является резидентной.</span><span class="sxs-lookup"><span data-stu-id="9f65d-105">In this sample, the service is self-hosted.</span></span> <span data-ttu-id="9f65d-106">И клиент, и служба являются консольными приложениями.</span><span class="sxs-lookup"><span data-stu-id="9f65d-106">Both the client and service are console applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f65d-107">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="9f65d-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9f65d-108">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="9f65d-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9f65d-109">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="9f65d-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9f65d-110">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="9f65d-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9f65d-111">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="9f65d-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\Default`  
  
 <span data-ttu-id="9f65d-112">Привязка задается в файлах конфигурации для клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="9f65d-112">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="9f65d-113">Тип привязки указывается в `binding` атрибут [ \<endpoint >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) элемента, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9f65d-113">The binding type is specified in the `binding` attribute of the [\<endpoint>](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) element as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="9f65d-114">В предыдущем примере показано, как настроить конечную точку для использования привязки `netTcpBinding` с параметрами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9f65d-114">The previous sample shows how to configure an endpoint to use the `netTcpBinding` binding with the default settings.</span></span> <span data-ttu-id="9f65d-115">Если необходимо настроить привязку `netTcpBinding` и изменить некоторые из ее параметров, необходимо определить конфигурацию привязки.</span><span class="sxs-lookup"><span data-stu-id="9f65d-115">If you want to configure the `netTcpBinding` binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="9f65d-116">Конечная точка должна ссылаться на конфигурацию привязки по имени с атрибутом `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="9f65d-116">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="9f65d-117">В этом образце конфигурация привязки называется `Binding1` и определена, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9f65d-117">In this sample, the binding configuration is named `Binding1` and is defined as shown in the following sample configuration.</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    ...  
    <endpoint address=""  
              binding="netTcpBinding"  
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
  
<bindings>  
  <netTcpBinding>  
    <binding name="Binding1"   
             closeTimeout="00:01:00"  
             openTimeout="00:01:00"   
             receiveTimeout="00:10:00"   
             sendTimeout="00:01:00"  
             transactionFlow="false"   
             transferMode="Buffered"   
             transactionProtocol="OleTransactions"  
             hostNameComparisonMode="StrongWildcard"   
             listenBacklog="10"  
             maxBufferPoolSize="524288"   
             maxBufferSize="65536"   
             maxConnections="10"  
             maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32"   
                    maxStringContentLength="8192"   
                    maxArrayLength="16384"  
                    maxBytesPerRead="4096"   
                    maxNameTableCharCount="16384" />  
      <reliableSession ordered="true"   
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="9f65d-118">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="9f65d-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="9f65d-119">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="9f65d-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press ENTER to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9f65d-120">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="9f65d-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9f65d-121">Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.</span><span class="sxs-lookup"><span data-stu-id="9f65d-121">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="9f65d-122">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9f65d-122">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="9f65d-123">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9f65d-123">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="9f65d-124">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9f65d-124">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9f65d-125">Поскольку сервер является резидентным, чтобы выполнить образец на нескольких компьютерах, необходимо указать удостоверение в файле App.config клиента.</span><span class="sxs-lookup"><span data-stu-id="9f65d-125">Because the server is self-hosted, you must specify an identity in the client's App.config file to run the sample in a cross-machine configuration.</span></span>  
  
    ```xml  
    <client>  
      <endpoint name=""  
          address="net.tcp://servername:9000/servicemodelsamples/service"   
          binding="netTcpBinding"   
          contract="Microsoft.ServiceModel.Samples.ICalculator">  
            <identity>  
              <userPrincipalName value = "user_name@service_domain"/>  
            </identity>  
      </endpoint>  
    </client>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9f65d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="9f65d-126">See Also</span></span>
