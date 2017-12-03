---
title: "Практическое руководство. Создание конечной точки службы в конфигурации"
ms.custom: 
ms.date: 06/16/2016
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e60708ecf5ae7ed15b42e982b9ae40c00d72ecc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a><span data-ttu-id="46590-102">Практическое руководство. Создание конечной точки службы в конфигурации</span><span class="sxs-lookup"><span data-stu-id="46590-102">How to: Create a Service Endpoint in Configuration</span></span>
<span data-ttu-id="46590-103">Конечные точки предоставляют клиентам доступ к функциональным возможностям службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="46590-103">Endpoints provide clients with access to the functionality a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service offers.</span></span> <span data-ttu-id="46590-104">Можно определить одну или несколько конечных точек для службы, используя сочетание относительных и абсолютных адресов конечных точек. Если же не определять конечные точки службы, среда выполнения автоматически создаст несколько точек по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46590-104">You can define one or more endpoints for a service by using a combination of relative and absolute endpoint addresses, or if you do not define any service endpoints, the runtime provides some by default for you.</span></span> <span data-ttu-id="46590-105">В этом разделе показано, как добавить конечные точки, используя файл конфигурации, который содержит и относительные, и абсолютные адреса.</span><span class="sxs-lookup"><span data-stu-id="46590-105">This topic shows how to add endpoints using a configuration file that contain both relative and absolute addresses.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46590-106">Пример</span><span class="sxs-lookup"><span data-stu-id="46590-106">Example</span></span>  
 <span data-ttu-id="46590-107">Представленная ниже конфигурация службы задает базовый адрес и пять конечных точек.</span><span class="sxs-lookup"><span data-stu-id="46590-107">The following service configuration specifies a base address and five endpoints.</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced  
         in .NET Framework 4. -->  
      <service  
          name="Microsoft.ServiceModel.Samples.CalculatorService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="/test"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="http://localhost:8001/hello/servicemodelsamples"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
                  binding="netTcpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is another relative address exposed at   
             http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="46590-108">Пример</span><span class="sxs-lookup"><span data-stu-id="46590-108">Example</span></span>  
 <span data-ttu-id="46590-109">Базовый адрес задается с помощью элемента `add` в каталоге service/host/baseAddresses, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="46590-109">The base address is specified using the `add` element, under service/host/baseAddresses, as shown in the following sample.</span></span>  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a><span data-ttu-id="46590-110">Пример</span><span class="sxs-lookup"><span data-stu-id="46590-110">Example</span></span>  
 <span data-ttu-id="46590-111">В первом определении конечной точки, показанном в следующем образце, задается относительный адрес. Это означает, что адрес конечной точки представляет собой сочетание базового и относительного адресов, соответствующее правилам формирования универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="46590-111">The first endpoint definition shown in the following sample specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of Uniform Resource Identifier (URI) composition.</span></span> <span data-ttu-id="46590-112">Относительный адрес пустой (""), поэтому адрес конечной точки совпадает с базовым адресом.</span><span class="sxs-lookup"><span data-stu-id="46590-112">The relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="46590-113">Фактический адрес конечной точки - http://localhost:8000/servicemodelsamples/service.</span><span class="sxs-lookup"><span data-stu-id="46590-113">The actual endpoint address is http://localhost:8000/servicemodelsamples/service.</span></span>  
  
```xml  
<endpoint address=""   
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="46590-114">Пример</span><span class="sxs-lookup"><span data-stu-id="46590-114">Example</span></span>  
 <span data-ttu-id="46590-115">Во втором определении конечной точки также задается относительный адрес, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="46590-115">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span> <span data-ttu-id="46590-116">Относительный адрес, "test", присоединяется к базовому адресу.</span><span class="sxs-lookup"><span data-stu-id="46590-116">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="46590-117">Фактический адрес конечной точки - http://localhost:8000/servicemodelsamples/service/test.</span><span class="sxs-lookup"><span data-stu-id="46590-117">The actual endpoint address is http://localhost:8000/servicemodelsamples/service/test.</span></span>  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="46590-118">Пример</span><span class="sxs-lookup"><span data-stu-id="46590-118">Example</span></span>  
 <span data-ttu-id="46590-119">В третьем определении конечной точки задается абсолютный адрес, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="46590-119">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span> <span data-ttu-id="46590-120">Базовый адрес не играет никакой роли в этом адресе.</span><span class="sxs-lookup"><span data-stu-id="46590-120">The base address plays no role in the address.</span></span> <span data-ttu-id="46590-121">Фактический адрес конечной точки - http://localhost:8001/hello/servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="46590-121">The actual endpoint address is http://localhost:8001/hello/servicemodelsamples.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="46590-122">Пример</span><span class="sxs-lookup"><span data-stu-id="46590-122">Example</span></span>  
 <span data-ttu-id="46590-123">В четвертом определении конечной точки задаются абсолютный адрес и другой транспорт - TCP.</span><span class="sxs-lookup"><span data-stu-id="46590-123">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="46590-124">Базовый адрес не играет никакой роли в этом адресе.</span><span class="sxs-lookup"><span data-stu-id="46590-124">The base address plays no role in the address.</span></span> <span data-ttu-id="46590-125">Фактический адрес конечной точки — net.tcp://localhost:9000/servicemodelsamples/service.</span><span class="sxs-lookup"><span data-stu-id="46590-125">The actual endpoint address is net.tcp://localhost:9000/servicemodelsamples/service.</span></span>  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a><span data-ttu-id="46590-126">Пример</span><span class="sxs-lookup"><span data-stu-id="46590-126">Example</span></span>  
 <span data-ttu-id="46590-127">Чтобы использовать конечные точки по умолчанию, предоставляемые средой выполнения, не указывайте конечные точки службы ни в коде, ни в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="46590-127">To use the default endpoints provided by the runtime, do not specify any service endpoints in either the code or the configuration file.</span></span> <span data-ttu-id="46590-128">В этом примере среда выполнения при открытии службы создает конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="46590-128">In this example, the runtime creates the default endpoints when the service is opened.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="46590-129">см. по умолчанию конечные точки, привязки и поведения, [упрощенной конфигурации](../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="46590-129"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```
