---
title: Незащищенные интранет-клиент и служба
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f450f5d4-3547-47ec-9320-2809e6a12634
ms.openlocfilehash: 540c0fe5c4d06ea341b9cc8be9755cc67fe9bbc2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085185"
---
# <a name="intranet-unsecured-client-and-service"></a><span data-ttu-id="64d9b-102">Незащищенные интранет-клиент и служба</span><span class="sxs-lookup"><span data-stu-id="64d9b-102">Intranet Unsecured Client and Service</span></span>
<span data-ttu-id="64d9b-103">На следующем рисунке показана простая служба Windows Communication Foundation (WCF) разработан для предоставления информации о защищенной частной сети для приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="64d9b-103">The following illustration depicts a simple Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span> <span data-ttu-id="64d9b-104">Безопасность не является обязательным, так как данные имеют низкий уровень важности, должен быть в своей основе является защищенной сети или безопасность обеспечивается на уровне ниже инфраструктура WCF.</span><span class="sxs-lookup"><span data-stu-id="64d9b-104">Security is not required because the data is of low importance, the network is expected to be inherently secure, or security is provided by a layer below the WCF infrastructure.</span></span>  
  
 ![Незащищенные интранет-клиент и служба сценария.](./media/intranet-unsecured-client-and-service/unsecured-web-client-service.gif)  
  
|<span data-ttu-id="64d9b-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="64d9b-106">Characteristic</span></span>|<span data-ttu-id="64d9b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="64d9b-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="64d9b-108">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="64d9b-108">Security Mode</span></span>|<span data-ttu-id="64d9b-109">Нет</span><span class="sxs-lookup"><span data-stu-id="64d9b-109">None</span></span>|  
|<span data-ttu-id="64d9b-110">Transport</span><span class="sxs-lookup"><span data-stu-id="64d9b-110">Transport</span></span>|<span data-ttu-id="64d9b-111">TCP</span><span class="sxs-lookup"><span data-stu-id="64d9b-111">TCP</span></span>|  
|<span data-ttu-id="64d9b-112">Привязка</span><span class="sxs-lookup"><span data-stu-id="64d9b-112">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
|<span data-ttu-id="64d9b-113">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="64d9b-113">Interoperability</span></span>|<span data-ttu-id="64d9b-114">Только WCF</span><span class="sxs-lookup"><span data-stu-id="64d9b-114">WCF only</span></span>|  
|<span data-ttu-id="64d9b-115">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="64d9b-115">Authentication</span></span>|<span data-ttu-id="64d9b-116">Нет</span><span class="sxs-lookup"><span data-stu-id="64d9b-116">None</span></span>|  
|<span data-ttu-id="64d9b-117">Целостность</span><span class="sxs-lookup"><span data-stu-id="64d9b-117">Integrity</span></span>|<span data-ttu-id="64d9b-118">Нет</span><span class="sxs-lookup"><span data-stu-id="64d9b-118">None</span></span>|  
|<span data-ttu-id="64d9b-119">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="64d9b-119">Confidentiality</span></span>|<span data-ttu-id="64d9b-120">Нет</span><span class="sxs-lookup"><span data-stu-id="64d9b-120">None</span></span>|  
  
## <a name="service"></a><span data-ttu-id="64d9b-121">Служба</span><span class="sxs-lookup"><span data-stu-id="64d9b-121">Service</span></span>  
 <span data-ttu-id="64d9b-122">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="64d9b-122">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="64d9b-123">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="64d9b-123">Do one of the following:</span></span>  
  
-   <span data-ttu-id="64d9b-124">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="64d9b-124">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="64d9b-125">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="64d9b-125">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="64d9b-126">Код</span><span class="sxs-lookup"><span data-stu-id="64d9b-126">Code</span></span>  
 <span data-ttu-id="64d9b-127">В следующем коде показано создание конечной точки без обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="64d9b-127">The following code shows how to create an endpoint with no security:</span></span>  
  
 [!code-csharp[C_UnsecuredService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredservice/cs/source.cs#2)]
 [!code-vb[C_UnsecuredService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredservice/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="64d9b-128">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="64d9b-128">Configuration</span></span>  
 <span data-ttu-id="64d9b-129">В следующем коде настраивается та же конечная точка с использованием конфигурации.</span><span class="sxs-lookup"><span data-stu-id="64d9b-129">The following code sets up the same endpoint using configuration:</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="64d9b-130">"Клиент";</span><span class="sxs-lookup"><span data-stu-id="64d9b-130">Client</span></span>  
 <span data-ttu-id="64d9b-131">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="64d9b-131">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="64d9b-132">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="64d9b-132">Do one of the following:</span></span>  
  
-   <span data-ttu-id="64d9b-133">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="64d9b-133">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="64d9b-134">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="64d9b-134">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="64d9b-135">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="64d9b-135">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="64d9b-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="64d9b-136">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="64d9b-137">Код</span><span class="sxs-lookup"><span data-stu-id="64d9b-137">Code</span></span>  
 <span data-ttu-id="64d9b-138">В следующем коде показано базового клиента WCF, который обращается к незащищенной конечной точке по протоколу TCP.</span><span class="sxs-lookup"><span data-stu-id="64d9b-138">The following code shows a basic WCF client that accesses an unsecured endpoint using the TCP protocol.</span></span>  
  
 [!code-csharp[C_UnsecuredClient#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_unsecuredclient/cs/source.cs#2)]
 [!code-vb[C_UnsecuredClient#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_unsecuredclient/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="64d9b-139">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="64d9b-139">Configuration</span></span>  
 <span data-ttu-id="64d9b-140">Следующий код конфигурации применяется к клиенту.</span><span class="sxs-lookup"><span data-stu-id="64d9b-140">The following configuration code applies to the client:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64d9b-141">См. также</span><span class="sxs-lookup"><span data-stu-id="64d9b-141">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- [<span data-ttu-id="64d9b-142">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="64d9b-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="64d9b-143">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="64d9b-143">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
