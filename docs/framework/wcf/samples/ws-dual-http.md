---
title: WS Dual Http
ms.date: 03/30/2017
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
ms.openlocfilehash: 1f1592598c0ed148f06c0a99ccdb8a8347175d8f
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716788"
---
# <a name="ws-dual-http"></a><span data-ttu-id="c8b07-102">WS Dual Http</span><span class="sxs-lookup"><span data-stu-id="c8b07-102">WS Dual Http</span></span>

<span data-ttu-id="c8b07-103">В образце двустороннего HTTP-взаимодействия показано, как настроить привязку `WSDualHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="c8b07-103">The Dual Http sample demonstrates how to configure the `WSDualHttpBinding` binding.</span></span> <span data-ttu-id="c8b07-104">Этот образец содержит консольную программу клиента (EXE) и библиотеку службы (DLL), размещаемую в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="c8b07-104">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="c8b07-105">Служба реализует дуплексный контракт.</span><span class="sxs-lookup"><span data-stu-id="c8b07-105">The service implements a duplex contract.</span></span> <span data-ttu-id="c8b07-106">Контракт определяется интерфейсом `ICalculatorDuplex`, который предоставляет математические операции (добавить, вычесть, умножить и разделить).</span><span class="sxs-lookup"><span data-stu-id="c8b07-106">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="c8b07-107">В этом образце интерфейс `ICalculatorDuplex` позволяет клиенту выполнять математические операции, вычисляя результат выполнения в сеансе.</span><span class="sxs-lookup"><span data-stu-id="c8b07-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over the session.</span></span> <span data-ttu-id="c8b07-108">Независимо от этого служба возвращает результаты в интерфейсе `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="c8b07-108">Independently, the service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="c8b07-109">Для дуплексного контракта требуется сеанс, поскольку необходимо установить контекст для корреляции набора сообщений, обмен которыми осуществляется между клиентом и службой.</span><span class="sxs-lookup"><span data-stu-id="c8b07-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between client and service.</span></span> <span data-ttu-id="c8b07-110">Привязка `WSDualHttpBinding` поддерживает дуплексное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="c8b07-110">The `WSDualHttpBinding` binding supports duplex communication.</span></span>

> [!NOTE]
> <span data-ttu-id="c8b07-111">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="c8b07-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8b07-112">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c8b07-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c8b07-113">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="c8b07-113">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="c8b07-114">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="c8b07-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c8b07-115">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="c8b07-115">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`

<span data-ttu-id="c8b07-116">Чтобы настроить конечную точку службы с привязкой `WSDualHttpBinding`, укажите привязку в конфигурации конечной точки, как показано в примере.</span><span class="sxs-lookup"><span data-stu-id="c8b07-116">To configure a service endpoint with the `WSDualHttpBinding`, specify the binding in the endpoint configuration as shown.</span></span>

```xml
<endpoint address=""
         binding="wsDualHttpBinding"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
```

<span data-ttu-id="c8b07-117">На стороне клиента необходимо настроить адрес, который будет использоваться сервером для подключения к клиенту, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c8b07-117">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>

```xml
<system.serviceModel>
  <client>
    <endpoint address=
         "http://localhost/servicemodelsamples/service.svc"
         binding="wsDualHttpBinding"
         bindingConfiguration="Binding1"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
  </client>

  <bindings>
    <!-- Configure a WSDualHttpBinding that supports duplex -->
    <!-- communication. -->
    <wsDualHttpBinding>
      <binding name="Binding1"
               clientBaseAddress="http://localhost:8000/myClient/"
               useDefaultWebProxy="true"
               bypassProxyOnLocal="false">
      </binding>
    </wsDualHttpBinding>
  </bindings>
</system.serviceModel>
```

<span data-ttu-id="c8b07-118">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="c8b07-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c8b07-119">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="c8b07-119">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate client once the output is displayed.

Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

<span data-ttu-id="c8b07-120">При выполнении образца видны отправляемые службой сообщения, возвращаемые клиенту в интерфейсе обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="c8b07-120">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="c8b07-121">Отображается каждый промежуточный результат с последующим отображением всей формулы после завершения всех операций.</span><span class="sxs-lookup"><span data-stu-id="c8b07-121">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="c8b07-122">Чтобы закрыть клиент, нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c8b07-122">Press ENTER to shut down the client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c8b07-123">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="c8b07-123">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="c8b07-124">Установите ASP.NET 4,0 с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="c8b07-124">Install ASP.NET 4.0 using the following command.</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="c8b07-125">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c8b07-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="c8b07-126">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c8b07-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

4. <span data-ttu-id="c8b07-127">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c8b07-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c8b07-128">При запуске клиента в конфигурации с несколькими компьютерами не забудьте заменить localhost в атрибуте `address` [конечной точки\<> \<клиентского >](../../configure-apps/file-schema/wcf/endpoint-of-client.md) и атрибут `clientBaseAddress`\<[binding](../../configure-apps/file-schema/wcf/bindings.md) > элемента [\<WSDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) с именем соответствующего компьютера, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="c8b07-128">When running the client in a cross-machine configuration, be sure to replace localhost in both the `address` attribute of the [\<endpoint> of \<client>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element and the `clientBaseAddress` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element of the [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown:</span></span>

    ```xml
    <client>
        <endpoint name = ""
          address=
         "http://service_machine_name/servicemodelsamples/service.svc"
        />
    </client>
    ...
    <wsDualHttpBinding>
        <binding name="DuplexBinding" clientBaseAddress=
            "http://client_machine_name:8000/myClient/">
        </binding>
    </wsDualHttpBinding>
    ```
