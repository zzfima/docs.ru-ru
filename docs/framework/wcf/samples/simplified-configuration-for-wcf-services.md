---
title: Упрощенная конфигурация служб WCF
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: a1188ad9ed56ebb24754785546b6a5b54cd2b840
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715434"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="cba07-102">Упрощенная конфигурация служб WCF</span><span class="sxs-lookup"><span data-stu-id="cba07-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="cba07-103">В этом примере показано, как реализовать и настроить типичную службу и клиент с помощью Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cba07-103">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="cba07-104">Этот образец является основой для всех остальных базовых образцов технологий.</span><span class="sxs-lookup"><span data-stu-id="cba07-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="cba07-105">Эта служба, которая предоставляет конечную точку для взаимодействия со службой, использует упрощенную конфигурацию в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="cba07-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4.</span></span> <span data-ttu-id="cba07-106">До .NET Framework 4 конечная точка обычно определяется в файле конфигурации (Web. config), как показано в следующем примере кода конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cba07-106">Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
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
  
 <span data-ttu-id="cba07-107">В .NET Framework 4 элемент `<service>` является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cba07-107">In .NET Framework 4, the `<service>` element is optional.</span></span> <span data-ttu-id="cba07-108">Если конечные точки не заданы в службе, то к службе добавляется конечная точка для каждого базового адреса и реализованного контракта.</span><span class="sxs-lookup"><span data-stu-id="cba07-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="cba07-109">Базовый адрес добавляется к имени контракта для определения конечной точки, и привязка определяется с помощью схемы адреса.</span><span class="sxs-lookup"><span data-stu-id="cba07-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="cba07-110">В следующем примере кода показан файл упрощенной конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cba07-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="cba07-111">Как настроено, доступ к службе можно получить на `http://localhost/servicemodelsamples/service.svc` клиентом на том же компьютере.</span><span class="sxs-lookup"><span data-stu-id="cba07-111">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="cba07-112">Чтобы к службе могли получить доступ клиенты на удаленных компьютерах, вместо имени localhost необходимо указать полное имя домена.</span><span class="sxs-lookup"><span data-stu-id="cba07-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="cba07-113">По умолчанию служба не предоставляет метаданных.</span><span class="sxs-lookup"><span data-stu-id="cba07-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="cba07-114">При этом служба включает поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.</span><span class="sxs-lookup"><span data-stu-id="cba07-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
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
  
### <a name="to-use-this-sample"></a><span data-ttu-id="cba07-115">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="cba07-115">To use this sample</span></span>  
  
1. <span data-ttu-id="cba07-116">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cba07-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="cba07-117">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cba07-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="cba07-118">Запустите образец, выполнив следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="cba07-118">Run the sample by following these steps:</span></span>  
  
    1. <span data-ttu-id="cba07-119">Щелкните правой кнопкой мыши проект **службы** и выберите **Назначить запускаемым проектом**, а затем нажмите клавиши **CTRL + F5**.</span><span class="sxs-lookup"><span data-stu-id="cba07-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2. <span data-ttu-id="cba07-120">Дождитесь вывода данных на консоли, подтверждающих запуск и выполнение службы.</span><span class="sxs-lookup"><span data-stu-id="cba07-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3. <span data-ttu-id="cba07-121">Щелкните правой кнопкой мыши проект **клиента** и выберите **Назначить запускаемым проектом**, а затем нажмите клавиши **CTRL + F5**.</span><span class="sxs-lookup"><span data-stu-id="cba07-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="cba07-122">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cba07-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="cba07-123">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cba07-123">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="cba07-124">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="cba07-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cba07-125">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="cba07-125">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="cba07-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="cba07-126">See also</span></span>

- [<span data-ttu-id="cba07-127">Примеры управления AppFabric</span><span class="sxs-lookup"><span data-stu-id="cba07-127">AppFabric Management Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193960)
- [<span data-ttu-id="cba07-128">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="cba07-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
