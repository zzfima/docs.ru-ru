---
title: "Незащищенные интранет-клиент и служба"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
caps.latest.revision: "20"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 0cfd98d401921c47bd85f8d4089e3efb437ca6b7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="f2996-102">Незащищенные интранет-клиент и служба</span><span class="sxs-lookup"><span data-stu-id="f2996-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="f2996-103">На следующем рисунке показана простая служба [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], разработанная для предоставления приложению [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сведений о защищенной частной сети.</span><span class="sxs-lookup"><span data-stu-id="f2996-103">The following illustration depicts a simple [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service developed to provide information on a secure private network to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application.</span></span> <span data-ttu-id="f2996-104">Безопасность не требуется, поскольку данные имеют низкий уровень важности, предполагается, что сеть в своей основе является защищенной, или безопасность обеспечивается уровнем, расположенным ниже инфраструктуры [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2996-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure.</span></span>  
  
 <span data-ttu-id="f2996-105">![Незащищенные интранет-клиент и служба сценария](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span><span class="sxs-lookup"><span data-stu-id="f2996-105">![Intranet unsecured client and service scenario](../../../../docs/framework/wcf/feature-details/media/unsecuredwebservice.gif "UnsecuredWebService")</span></span>  
  
|<span data-ttu-id="f2996-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="f2996-106">Characteristic</span></span>|<span data-ttu-id="f2996-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f2996-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="f2996-108">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="f2996-108">Security Mode</span></span>|<span data-ttu-id="f2996-109">Нет</span><span class="sxs-lookup"><span data-stu-id="f2996-109">None</span></span>|  
|<span data-ttu-id="f2996-110">Transport</span><span class="sxs-lookup"><span data-stu-id="f2996-110">Transport</span></span>|<span data-ttu-id="f2996-111">TCP</span><span class="sxs-lookup"><span data-stu-id="f2996-111">TCP</span></span>|  
|<span data-ttu-id="f2996-112">Привязка</span><span class="sxs-lookup"><span data-stu-id="f2996-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="f2996-113">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="f2996-113">Interoperability</span></span>|<span data-ttu-id="f2996-114">Только [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2996-114">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="f2996-115">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="f2996-115">Authentication</span></span>|<span data-ttu-id="f2996-116">Нет</span><span class="sxs-lookup"><span data-stu-id="f2996-116">None</span></span>|  
|<span data-ttu-id="f2996-117">Целостность</span><span class="sxs-lookup"><span data-stu-id="f2996-117">Integrity</span></span>|<span data-ttu-id="f2996-118">Нет</span><span class="sxs-lookup"><span data-stu-id="f2996-118">None</span></span>|  
|<span data-ttu-id="f2996-119">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="f2996-119">Confidentiality</span></span>|<span data-ttu-id="f2996-120">Нет</span><span class="sxs-lookup"><span data-stu-id="f2996-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="f2996-121">Служба</span><span class="sxs-lookup"><span data-stu-id="f2996-121">Service</span></span>  
 <span data-ttu-id="f2996-122">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="f2996-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f2996-123">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="f2996-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f2996-124">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f2996-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="f2996-125">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="f2996-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f2996-126">Код</span><span class="sxs-lookup"><span data-stu-id="f2996-126">Code</span></span>  
 <span data-ttu-id="f2996-127">В следующем коде показано создание конечной точки без обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f2996-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="f2996-128">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="f2996-128">Configuration</span></span>  
 <span data-ttu-id="f2996-129">В следующем коде настраивается та же конечная точка с использованием конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f2996-129">The following code sets up the same endpoint using configuration:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="f2996-130">Клиент</span><span class="sxs-lookup"><span data-stu-id="f2996-130">Client</span></span>  
 <span data-ttu-id="f2996-131">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="f2996-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="f2996-132">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="f2996-132">Do one of the following:</span></span>  
  
-   <span data-ttu-id="f2996-133">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="f2996-133">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="f2996-134">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f2996-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="f2996-135">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f2996-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="f2996-136">Например:</span><span class="sxs-lookup"><span data-stu-id="f2996-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="f2996-137">Код</span><span class="sxs-lookup"><span data-stu-id="f2996-137">Code</span></span>  
 <span data-ttu-id="f2996-138">В следующем коде показан основной клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], обращающийся к незащищенной конечной точке по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="f2996-138">The following code shows a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="f2996-139">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="f2996-139">Configuration</span></span>  
 <span data-ttu-id="f2996-140">Следующий код конфигурации применяется к клиенту.</span><span class="sxs-lookup"><span data-stu-id="f2996-140">The following configuration code applies to the client:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f2996-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f2996-141">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 [<span data-ttu-id="f2996-142">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="f2996-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="f2996-143">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="f2996-143">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
