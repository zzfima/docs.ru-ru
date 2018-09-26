---
title: Безопасность транспорта с анонимным клиентом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
author: BrucePerlerMS
ms.openlocfilehash: d09d2a2ad4e48e67f2d3930517a2ed3f8cc4403d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216086"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="c8e7c-102">Безопасность транспорта с анонимным клиентом</span><span class="sxs-lookup"><span data-stu-id="c8e7c-102">Transport Security with an Anonymous Client</span></span>
<span data-ttu-id="c8e7c-103">Этот сценарий Windows Communication Foundation (WCF) использует безопасность транспорта (HTTPS) для обеспечения конфиденциальности и целостности.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="c8e7c-104">Сервер должен пройти проверку подлинности с использованием сертификата SSL, и клиенты должны доверять сертификату сервера.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="c8e7c-105">Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>  
  
 <span data-ttu-id="c8e7c-106">Образец приложения, см. в разделе [безопасность транспорта WS](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="c8e7c-106">For a sample application, see [WS Transport Security](../../../../docs/framework/wcf/samples/ws-transport-security.md).</span></span> <span data-ttu-id="c8e7c-107">Дополнительные сведения о безопасности транспорта см. в разделе [Общие сведения о безопасности транспорта](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c8e7c-107">For more information about transport security, see [Transport Security Overview](../../../../docs/framework/wcf/feature-details/transport-security-overview.md).</span></span>  
  
 <span data-ttu-id="c8e7c-108">Дополнительные сведения об использовании сертификата со службой, см. в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) и [как: Настройка порта SSL-сертификат](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="c8e7c-108">For more information about using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 <span data-ttu-id="c8e7c-109">![Использование безопасности транспорта с анонимным клиентом](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span><span class="sxs-lookup"><span data-stu-id="c8e7c-109">![Using transport security with an anonymous client](../../../../docs/framework/wcf/feature-details/media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif "8fa2e931-0cfb-4aaa-9272-91d652b85d8d")</span></span>  
  
|<span data-ttu-id="c8e7c-110">Характеристика</span><span class="sxs-lookup"><span data-stu-id="c8e7c-110">Characteristic</span></span>|<span data-ttu-id="c8e7c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="c8e7c-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="c8e7c-112">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="c8e7c-112">Security Mode</span></span>|<span data-ttu-id="c8e7c-113">Transport</span><span class="sxs-lookup"><span data-stu-id="c8e7c-113">Transport</span></span>|  
|<span data-ttu-id="c8e7c-114">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="c8e7c-114">Interoperability</span></span>|<span data-ttu-id="c8e7c-115">С существующими веб-службами и клиентами</span><span class="sxs-lookup"><span data-stu-id="c8e7c-115">With existing Web services and clients</span></span>|  
|<span data-ttu-id="c8e7c-116">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="c8e7c-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="c8e7c-117">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="c8e7c-117">Authentication (Client)</span></span>|<span data-ttu-id="c8e7c-118">Да</span><span class="sxs-lookup"><span data-stu-id="c8e7c-118">Yes</span></span><br /><br /> <span data-ttu-id="c8e7c-119">Уровень приложения (без поддержки WCF)</span><span class="sxs-lookup"><span data-stu-id="c8e7c-119">Application level (no WCF support)</span></span>|  
|<span data-ttu-id="c8e7c-120">Целостность</span><span class="sxs-lookup"><span data-stu-id="c8e7c-120">Integrity</span></span>|<span data-ttu-id="c8e7c-121">Да</span><span class="sxs-lookup"><span data-stu-id="c8e7c-121">Yes</span></span>|  
|<span data-ttu-id="c8e7c-122">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="c8e7c-122">Confidentiality</span></span>|<span data-ttu-id="c8e7c-123">Да</span><span class="sxs-lookup"><span data-stu-id="c8e7c-123">Yes</span></span>|  
|<span data-ttu-id="c8e7c-124">Transport</span><span class="sxs-lookup"><span data-stu-id="c8e7c-124">Transport</span></span>|<span data-ttu-id="c8e7c-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="c8e7c-125">HTTPS</span></span>|  
|<span data-ttu-id="c8e7c-126">Привязка</span><span class="sxs-lookup"><span data-stu-id="c8e7c-126">Binding</span></span>|<span data-ttu-id="c8e7c-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="c8e7c-127"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>|  
  
## <a name="service"></a><span data-ttu-id="c8e7c-128">Служба</span><span class="sxs-lookup"><span data-stu-id="c8e7c-128">Service</span></span>  
 <span data-ttu-id="c8e7c-129">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-129">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="c8e7c-130">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-130">Do one of the following:</span></span>  
  
-   <span data-ttu-id="c8e7c-131">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-131">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="c8e7c-132">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-132">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c8e7c-133">Код</span><span class="sxs-lookup"><span data-stu-id="c8e7c-133">Code</span></span>  
 <span data-ttu-id="c8e7c-134">В следующем коде показано создание конечной точки с использованием безопасности транспорта:</span><span class="sxs-lookup"><span data-stu-id="c8e7c-134">The following code shows how to create an endpoint using transport security:</span></span>  
  
 [!code-csharp[c_SecurityScenarios#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
 [!code-vb[c_SecurityScenarios#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]  
  
### <a name="configuration"></a><span data-ttu-id="c8e7c-135">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="c8e7c-135">Configuration</span></span>  
 <span data-ttu-id="c8e7c-136">В следующем коде настраивается та же конечная точка с использованием конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-136">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="c8e7c-137">Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-137">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="SecuredByTransportEndpoint"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="c8e7c-138">"Клиент";</span><span class="sxs-lookup"><span data-stu-id="c8e7c-138">Client</span></span>  
 <span data-ttu-id="c8e7c-139">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-139">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="c8e7c-140">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-140">Do one of the following:</span></span>  
  
-   <span data-ttu-id="c8e7c-141">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="c8e7c-141">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="c8e7c-142">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-142">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="c8e7c-143">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-143">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="c8e7c-144">Например:</span><span class="sxs-lookup"><span data-stu-id="c8e7c-144">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="c8e7c-145">Код</span><span class="sxs-lookup"><span data-stu-id="c8e7c-145">Code</span></span>  
 [!code-csharp[c_SecurityScenarios#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
 [!code-vb[c_SecurityScenarios#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]  
  
### <a name="configuration"></a><span data-ttu-id="c8e7c-146">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="c8e7c-146">Configuration</span></span>  
 <span data-ttu-id="c8e7c-147">Вместо кода для настройки службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="c8e7c-147">The following configuration can be used instead of the code to set up the service.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8e7c-148">См. также</span><span class="sxs-lookup"><span data-stu-id="c8e7c-148">See Also</span></span>  
 [<span data-ttu-id="c8e7c-149">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="c8e7c-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="c8e7c-150">Безопасность транспорта WS</span><span class="sxs-lookup"><span data-stu-id="c8e7c-150">WS Transport Security</span></span>](../../../../docs/framework/wcf/samples/ws-transport-security.md)  
 [<span data-ttu-id="c8e7c-151">Общие сведения о безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="c8e7c-151">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 [<span data-ttu-id="c8e7c-152">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="c8e7c-152">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
