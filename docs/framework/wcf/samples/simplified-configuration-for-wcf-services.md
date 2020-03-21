---
title: Упрощенная конфигурация служб WCF
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: f3c4df5ae3fe5426c8b26142807f16b60db001c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183355"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="4642e-102">Упрощенная конфигурация служб WCF</span><span class="sxs-lookup"><span data-stu-id="4642e-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="4642e-103">В этом примере показано, как реализовать и настроить типичную службу и клиента с помощью Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4642e-103">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="4642e-104">Этот образец является основой для всех остальных базовых образцов технологий.</span><span class="sxs-lookup"><span data-stu-id="4642e-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="4642e-105">Эта служба, которая предоставляет конечную точку для связи с службой, использует упрощенную конфигурацию в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="4642e-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4.</span></span> <span data-ttu-id="4642e-106">До .NET Framework 4 конечная точка обычно определяется в файле конфигурации (Web.config), как показано в следующем примере кода конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4642e-106">Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="4642e-107">В .NET Framework `<service>` 4 элемент не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="4642e-107">In .NET Framework 4, the `<service>` element is optional.</span></span> <span data-ttu-id="4642e-108">Если конечные точки не заданы в службе, то к службе добавляется конечная точка для каждого базового адреса и реализованного контракта.</span><span class="sxs-lookup"><span data-stu-id="4642e-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="4642e-109">Базовый адрес добавляется к имени контракта для определения конечной точки, и привязка определяется с помощью схемы адреса.</span><span class="sxs-lookup"><span data-stu-id="4642e-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="4642e-110">В следующем примере кода показан файл упрощенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4642e-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="4642e-111">В настройке к службе может `http://localhost/servicemodelsamples/service.svc` быть доступна клиент на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="4642e-111">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="4642e-112">Чтобы к службе могли получить доступ клиенты на удаленных компьютерах, вместо имени localhost необходимо указать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="4642e-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="4642e-113">По умолчанию служба не предоставляет метаданных.</span><span class="sxs-lookup"><span data-stu-id="4642e-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="4642e-114">При этом служба включает поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="4642e-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="4642e-115">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="4642e-115">To use this sample</span></span>  
  
1. <span data-ttu-id="4642e-116">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="4642e-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="4642e-117">Чтобы создать решение, следуйте инструкциям по [созданию образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="4642e-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="4642e-118">Запустите образец, выполнив следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="4642e-118">Run the sample by following these steps:</span></span>  
  
    1. <span data-ttu-id="4642e-119">Нажмите право на проект **Службы** и выберите **Set как проект StartUp,** затем нажмите **на Ctrl-F5.**</span><span class="sxs-lookup"><span data-stu-id="4642e-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2. <span data-ttu-id="4642e-120">Дождитесь вывода данных на консоли, подтверждающих запуск и выполнение службы.</span><span class="sxs-lookup"><span data-stu-id="4642e-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3. <span data-ttu-id="4642e-121">Нажмите право на проект **Клиента** и выберите **Set как проект StartUp,** затем нажмите **на Ctrl-F5.**</span><span class="sxs-lookup"><span data-stu-id="4642e-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4642e-122">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4642e-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4642e-123">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4642e-123">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="4642e-124">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="4642e-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4642e-125">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4642e-125">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="4642e-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4642e-126">See also</span></span>

- <span data-ttu-id="4642e-127">[Образцы управления AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383405(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="4642e-127">[AppFabric Management Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383405(v=azure.10))</span></span>
- [<span data-ttu-id="4642e-128">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="4642e-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
