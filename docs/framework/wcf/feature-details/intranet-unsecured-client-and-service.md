---
title: Незащищенные интранет-клиент и служба
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: e44b7af6581e6c5abdcb2f82b02d152dd22d0b3b
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44131355"
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="f66b6-102">Незащищенные интранет-клиент и служба</span><span class="sxs-lookup"><span data-stu-id="f66b6-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="f66b6-103">На следующем рисунке показана простая служба Windows Communication Foundation (WCF) разработан для предоставления информации о защищенной частной сети для приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="f66b6-103">The following illustration depicts a simple Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span> <span data-ttu-id="f66b6-104">Безопасность не является обязательным, так как данные имеют низкий уровень важности, должен быть в своей основе является защищенной сети или безопасность обеспечивается на уровне ниже инфраструктура WCF.</span><span class="sxs-lookup"><span data-stu-id="f66b6-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the WCF infrastructure.</span></span>  
  
 <span data-ttu-id="f66b6-105">![Незащищенные интранет-клиент и служба сценария](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span><span class="sxs-lookup"><span data-stu-id="f66b6-105">![Intranet unsecured client and service scenario](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span></span>  
  
|<span data-ttu-id="f66b6-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="f66b6-106">Characteristic</span></span>|<span data-ttu-id="f66b6-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f66b6-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f66b6-108">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="f66b6-108">Security Mode</span></span>|<span data-ttu-id="f66b6-109">Нет</span><span class="sxs-lookup"><span data-stu-id="f66b6-109">None</span></span>|  
|<span data-ttu-id="f66b6-110">Transport</span><span class="sxs-lookup"><span data-stu-id="f66b6-110">Transport</span></span>|<span data-ttu-id="f66b6-111">TCP</span><span class="sxs-lookup"><span data-stu-id="f66b6-111">TCP</span></span>|  
|<span data-ttu-id="f66b6-112">Привязка</span><span class="sxs-lookup"><span data-stu-id="f66b6-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="f66b6-113">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="f66b6-113">Interoperability</span></span>|<span data-ttu-id="f66b6-114">Только WCF</span><span class="sxs-lookup"><span data-stu-id="f66b6-114">WCF only</span></span>|  
|<span data-ttu-id="f66b6-115">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f66b6-115">Authentication</span></span>|<span data-ttu-id="f66b6-116">Нет</span><span class="sxs-lookup"><span data-stu-id="f66b6-116">None</span></span>|  
|<span data-ttu-id="f66b6-117">Целостность</span><span class="sxs-lookup"><span data-stu-id="f66b6-117">Integrity</span></span>|<span data-ttu-id="f66b6-118">Нет</span><span class="sxs-lookup"><span data-stu-id="f66b6-118">None</span></span>|  
|<span data-ttu-id="f66b6-119">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="f66b6-119">Confidentiality</span></span>|<span data-ttu-id="f66b6-120">Нет</span><span class="sxs-lookup"><span data-stu-id="f66b6-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="f66b6-121">Служба</span><span class="sxs-lookup"><span data-stu-id="f66b6-121">Service</span></span>  
 <span data-ttu-id="f66b6-122">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="f66b6-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f66b6-123">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="f66b6-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f66b6-124">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f66b6-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="f66b6-125">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="f66b6-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f66b6-126">Код</span><span class="sxs-lookup"><span data-stu-id="f66b6-126">Code</span></span>  
 <span data-ttu-id="f66b6-127">В следующем коде показано создание конечной точки без обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f66b6-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="f66b6-128">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="f66b6-128">Configuration</span></span>  
 <span data-ttu-id="f66b6-129">В следующем коде настраивается та же конечная точка с использованием конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f66b6-129">The following code sets up the same endpoint using configuration:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration=""   
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"   
                  binding="netTcpBinding"  
                  bindingConfiguration="tcp_Unsecured"   
                  name="netTcp_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="tcp_Unsecured">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="f66b6-130">Клиент</span><span class="sxs-lookup"><span data-stu-id="f66b6-130">Client</span></span>  
 <span data-ttu-id="f66b6-131">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="f66b6-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f66b6-132">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="f66b6-132">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f66b6-133">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="f66b6-133">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="f66b6-134">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f66b6-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="f66b6-135">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f66b6-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="f66b6-136">Например:</span><span class="sxs-lookup"><span data-stu-id="f66b6-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="f66b6-137">Код</span><span class="sxs-lookup"><span data-stu-id="f66b6-137">Code</span></span>  
 <span data-ttu-id="f66b6-138">В следующем коде показано базового клиента WCF, который обращается к незащищенной конечной точке по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="f66b6-138">The following code shows a basic WCF client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="f66b6-139">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="f66b6-139">Configuration</span></span>  
 <span data-ttu-id="f66b6-140">Следующий код конфигурации применяется к клиенту.</span><span class="sxs-lookup"><span data-stu-id="f66b6-140">The following configuration code applies to the client:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
          <security mode="None">  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator "  
                binding="netTcpBinding"   
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"   
                name="NetTcpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f66b6-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f66b6-141">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 [<span data-ttu-id="f66b6-142">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="f66b6-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="f66b6-143">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="f66b6-143">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
