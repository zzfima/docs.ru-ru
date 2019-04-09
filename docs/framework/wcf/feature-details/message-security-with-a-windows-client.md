---
title: Безопасность сообщений с клиентом Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
ms.openlocfilehash: 794a3d8e118cadd2a2752e1bbf85ef930deb2f27
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59138649"
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="c5f73-102">Безопасность сообщений с клиентом Windows</span><span class="sxs-lookup"><span data-stu-id="c5f73-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="c5f73-103">Этот сценарий показывает, Windows Communication Foundation (WCF) клиентом и сервером, защищенных с помощью режима безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="c5f73-103">This scenario shows a Windows Communication Foundation (WCF) client and server secured by message security mode.</span></span> <span data-ttu-id="c5f73-104">Клиент и служба проходят проверку подлинности с использованием учетных данных Windows.</span><span class="sxs-lookup"><span data-stu-id="c5f73-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="c5f73-105">![Безопасность с клиентом Windows сообщений](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="c5f73-105">![Message security with a Windows client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="c5f73-106">Характеристика</span><span class="sxs-lookup"><span data-stu-id="c5f73-106">Characteristic</span></span>|<span data-ttu-id="c5f73-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c5f73-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c5f73-108">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="c5f73-108">Security Mode</span></span>|<span data-ttu-id="c5f73-109">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c5f73-109">Message</span></span>|  
|<span data-ttu-id="c5f73-110">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="c5f73-110">Interoperability</span></span>|<span data-ttu-id="c5f73-111">Только WCF</span><span class="sxs-lookup"><span data-stu-id="c5f73-111">WCF Only</span></span>|  
|<span data-ttu-id="c5f73-112">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="c5f73-112">Authentication (Server)</span></span>|<span data-ttu-id="c5f73-113">Взаимная проверка подлинности сервера и клиента</span><span class="sxs-lookup"><span data-stu-id="c5f73-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="c5f73-114">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="c5f73-114">Authentication (Client)</span></span>|<span data-ttu-id="c5f73-115">Взаимная проверка подлинности сервера и клиента</span><span class="sxs-lookup"><span data-stu-id="c5f73-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="c5f73-116">Целостность</span><span class="sxs-lookup"><span data-stu-id="c5f73-116">Integrity</span></span>|<span data-ttu-id="c5f73-117">Да, используется общий контекст безопасности</span><span class="sxs-lookup"><span data-stu-id="c5f73-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="c5f73-118">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="c5f73-118">Confidentiality</span></span>|<span data-ttu-id="c5f73-119">Да, используется общий контекст безопасности</span><span class="sxs-lookup"><span data-stu-id="c5f73-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="c5f73-120">Transport</span><span class="sxs-lookup"><span data-stu-id="c5f73-120">Transport</span></span>|<span data-ttu-id="c5f73-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="c5f73-121">NET.TCP</span></span>|  
|<span data-ttu-id="c5f73-122">Привязка</span><span class="sxs-lookup"><span data-stu-id="c5f73-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="c5f73-123">Служба</span><span class="sxs-lookup"><span data-stu-id="c5f73-123">Service</span></span>  
 <span data-ttu-id="c5f73-124">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="c5f73-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="c5f73-125">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="c5f73-125">Do one of the following:</span></span>  
  
-   <span data-ttu-id="c5f73-126">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c5f73-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="c5f73-127">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="c5f73-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c5f73-128">Код</span><span class="sxs-lookup"><span data-stu-id="c5f73-128">Code</span></span>  
 <span data-ttu-id="c5f73-129">В следующем коде показано создание конечной точки службы, которая использует безопасность сообщений для установления защищенного контекста с компьютером Windows.</span><span class="sxs-lookup"><span data-stu-id="c5f73-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="c5f73-130">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="c5f73-130">Configuration</span></span>  
 <span data-ttu-id="c5f73-131">Вместо кода для настройки службы можно использовать следующую конфигурацию:</span><span class="sxs-lookup"><span data-stu-id="c5f73-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="c5f73-132">"Клиент";</span><span class="sxs-lookup"><span data-stu-id="c5f73-132">Client</span></span>  
 <span data-ttu-id="c5f73-133">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="c5f73-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="c5f73-134">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="c5f73-134">Do one of the following:</span></span>  
  
-   <span data-ttu-id="c5f73-135">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="c5f73-135">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="c5f73-136">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c5f73-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="c5f73-137">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c5f73-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="c5f73-138">Пример:</span><span class="sxs-lookup"><span data-stu-id="c5f73-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="c5f73-139">Код</span><span class="sxs-lookup"><span data-stu-id="c5f73-139">Code</span></span>  
 <span data-ttu-id="c5f73-140">Следующий код служит для создания клиента.</span><span class="sxs-lookup"><span data-stu-id="c5f73-140">The following code creates a client.</span></span> <span data-ttu-id="c5f73-141">Привязка осуществляется к безопасности режима сообщений, и типу учетных данных клиента присваивается значение `Windows`.</span><span class="sxs-lookup"><span data-stu-id="c5f73-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="c5f73-142">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="c5f73-142">Configuration</span></span>  
 <span data-ttu-id="c5f73-143">Следующая конфигурация используется для задания свойств клиента.</span><span class="sxs-lookup"><span data-stu-id="c5f73-143">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"   
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">          
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5f73-144">См. также</span><span class="sxs-lookup"><span data-stu-id="c5f73-144">See also</span></span>

- [<span data-ttu-id="c5f73-145">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="c5f73-145">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="c5f73-146">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="c5f73-146">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
