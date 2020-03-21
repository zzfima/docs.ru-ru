---
title: Незащищенные интранет-клиент и служба
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
ms.openlocfilehash: 2fa13a12a377cc16a95318367605d8b5d92769a7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184684"
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="36ec7-102">Незащищенные интранет-клиент и служба</span><span class="sxs-lookup"><span data-stu-id="36ec7-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="36ec7-103">На следующей иллюстрации показан ажурный сервис Windows Communication Foundation (WCF), разработанный для предоставления информации о защищенной частной сети для приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="36ec7-103">The following illustration depicts a simple Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span> <span data-ttu-id="36ec7-104">Безопасность не требуется, поскольку данные имеют малое значение, сеть, как ожидается, будет по своей сути безопасной, или безопасность обеспечивается слоем ниже инфраструктуры WCF.</span><span class="sxs-lookup"><span data-stu-id="36ec7-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the WCF infrastructure.</span></span>  
  
 ![Сценарий необеспеченного клиента и обслуживания Intranet.](./media/intranet-unsecured-client-and-service/unsecured-web-client-service.gif)  
  
|<span data-ttu-id="36ec7-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="36ec7-106">Characteristic</span></span>|<span data-ttu-id="36ec7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="36ec7-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="36ec7-108">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="36ec7-108">Security Mode</span></span>|<span data-ttu-id="36ec7-109">None</span><span class="sxs-lookup"><span data-stu-id="36ec7-109">None</span></span>|  
|<span data-ttu-id="36ec7-110">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="36ec7-110">Transport</span></span>|<span data-ttu-id="36ec7-111">TCP</span><span class="sxs-lookup"><span data-stu-id="36ec7-111">TCP</span></span>|  
|<span data-ttu-id="36ec7-112">Привязка</span><span class="sxs-lookup"><span data-stu-id="36ec7-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="36ec7-113">Совместимость</span><span class="sxs-lookup"><span data-stu-id="36ec7-113">Interoperability</span></span>|<span data-ttu-id="36ec7-114">Только WCF</span><span class="sxs-lookup"><span data-stu-id="36ec7-114">WCF only</span></span>|  
|<span data-ttu-id="36ec7-115">Аутентификация</span><span class="sxs-lookup"><span data-stu-id="36ec7-115">Authentication</span></span>|<span data-ttu-id="36ec7-116">None</span><span class="sxs-lookup"><span data-stu-id="36ec7-116">None</span></span>|  
|<span data-ttu-id="36ec7-117">Целостность</span><span class="sxs-lookup"><span data-stu-id="36ec7-117">Integrity</span></span>|<span data-ttu-id="36ec7-118">None</span><span class="sxs-lookup"><span data-stu-id="36ec7-118">None</span></span>|  
|<span data-ttu-id="36ec7-119">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="36ec7-119">Confidentiality</span></span>|<span data-ttu-id="36ec7-120">None</span><span class="sxs-lookup"><span data-stu-id="36ec7-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="36ec7-121">Служба</span><span class="sxs-lookup"><span data-stu-id="36ec7-121">Service</span></span>  
 <span data-ttu-id="36ec7-122">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="36ec7-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="36ec7-123">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="36ec7-123">Do one of the following:</span></span>  
  
- <span data-ttu-id="36ec7-124">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="36ec7-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="36ec7-125">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="36ec7-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="36ec7-126">Код</span><span class="sxs-lookup"><span data-stu-id="36ec7-126">Code</span></span>  
 <span data-ttu-id="36ec7-127">В следующем коде показано создание конечной точки без обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="36ec7-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="36ec7-128">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="36ec7-128">Configuration</span></span>  
 <span data-ttu-id="36ec7-129">В следующем коде настраивается та же конечная точка с использованием конфигурации.</span><span class="sxs-lookup"><span data-stu-id="36ec7-129">The following code sets up the same endpoint using configuration:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="36ec7-130">клиент</span><span class="sxs-lookup"><span data-stu-id="36ec7-130">Client</span></span>  
 <span data-ttu-id="36ec7-131">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="36ec7-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="36ec7-132">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="36ec7-132">Do one of the following:</span></span>  
  
- <span data-ttu-id="36ec7-133">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="36ec7-133">Create a stand-alone client using the code (and client code).</span></span>  
  
- <span data-ttu-id="36ec7-134">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="36ec7-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="36ec7-135">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="36ec7-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="36ec7-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="36ec7-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="36ec7-137">Код</span><span class="sxs-lookup"><span data-stu-id="36ec7-137">Code</span></span>  
 <span data-ttu-id="36ec7-138">Следующий код показывает основного клиента WCF, который получает доступ к незащищенной конечной точке с помощью протокола TCP.</span><span class="sxs-lookup"><span data-stu-id="36ec7-138">The following code shows a basic WCF client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="36ec7-139">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="36ec7-139">Configuration</span></span>  
 <span data-ttu-id="36ec7-140">Следующий код конфигурации применяется к клиенту.</span><span class="sxs-lookup"><span data-stu-id="36ec7-140">The following configuration code applies to the client:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="36ec7-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="36ec7-141">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- [<span data-ttu-id="36ec7-142">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="36ec7-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="36ec7-143">[Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="36ec7-143">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
