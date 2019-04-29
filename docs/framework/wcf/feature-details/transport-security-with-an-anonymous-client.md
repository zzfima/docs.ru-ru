---
title: Безопасность транспорта с анонимным клиентом - WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 20d7e59ba2b4b9dedc0b0daff1c1aa9c5210e61b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61932966"
---
# <a name="transport-security-with-an-anonymous-client"></a><span data-ttu-id="948bc-102">Безопасность транспорта с анонимным клиентом</span><span class="sxs-lookup"><span data-stu-id="948bc-102">Transport security with an anonymous client</span></span>

<span data-ttu-id="948bc-103">Этот сценарий Windows Communication Foundation (WCF) использует безопасность транспорта (HTTPS) для обеспечения конфиденциальности и целостности.</span><span class="sxs-lookup"><span data-stu-id="948bc-103">This Windows Communication Foundation (WCF) scenario uses transport security (HTTPS) to ensure confidentiality and integrity.</span></span> <span data-ttu-id="948bc-104">Сервер должен пройти проверку подлинности с использованием сертификата SSL, и клиенты должны доверять сертификату сервера.</span><span class="sxs-lookup"><span data-stu-id="948bc-104">The server must be authenticated with a Secure Sockets Layer (SSL) certificate, and the clients must trust the server's certificate.</span></span> <span data-ttu-id="948bc-105">Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.</span><span class="sxs-lookup"><span data-stu-id="948bc-105">The client is not authenticated by any mechanism and is, therefore, anonymous.</span></span>

<span data-ttu-id="948bc-106">Образец приложения, см. в разделе [безопасность транспорта WS](../samples/ws-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="948bc-106">For a sample application, see [WS Transport Security](../samples/ws-transport-security.md).</span></span> <span data-ttu-id="948bc-107">Дополнительные сведения о безопасности транспорта см. в разделе [Общие сведения о безопасности транспорта](transport-security-overview.md).</span><span class="sxs-lookup"><span data-stu-id="948bc-107">For more information about transport security, see [Transport Security Overview](transport-security-overview.md).</span></span>

<span data-ttu-id="948bc-108">Дополнительные сведения об использовании сертификата со службой, см. в разделе [работа с сертификатами](working-with-certificates.md) и [как: Настройка порта SSL-сертификат](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="948bc-108">For more information about using a certificate with a service, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>

![Использование безопасности транспорта с анонимным клиентом](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|<span data-ttu-id="948bc-110">Характеристика</span><span class="sxs-lookup"><span data-stu-id="948bc-110">Characteristic</span></span>|<span data-ttu-id="948bc-111">Описание</span><span class="sxs-lookup"><span data-stu-id="948bc-111">Description</span></span>|
|--------------------|-----------------|
|<span data-ttu-id="948bc-112">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="948bc-112">Security Mode</span></span>|<span data-ttu-id="948bc-113">Transport</span><span class="sxs-lookup"><span data-stu-id="948bc-113">Transport</span></span>|
|<span data-ttu-id="948bc-114">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="948bc-114">Interoperability</span></span>|<span data-ttu-id="948bc-115">С существующими веб-службами и клиентами</span><span class="sxs-lookup"><span data-stu-id="948bc-115">With existing Web services and clients</span></span>|
|<span data-ttu-id="948bc-116">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="948bc-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="948bc-117">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="948bc-117">Authentication (Client)</span></span>|<span data-ttu-id="948bc-118">Да</span><span class="sxs-lookup"><span data-stu-id="948bc-118">Yes</span></span><br /><br /> <span data-ttu-id="948bc-119">Уровень приложения (без поддержки WCF)</span><span class="sxs-lookup"><span data-stu-id="948bc-119">Application level (no WCF support)</span></span>|
|<span data-ttu-id="948bc-120">Целостность</span><span class="sxs-lookup"><span data-stu-id="948bc-120">Integrity</span></span>|<span data-ttu-id="948bc-121">Да</span><span class="sxs-lookup"><span data-stu-id="948bc-121">Yes</span></span>|
|<span data-ttu-id="948bc-122">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="948bc-122">Confidentiality</span></span>|<span data-ttu-id="948bc-123">Да</span><span class="sxs-lookup"><span data-stu-id="948bc-123">Yes</span></span>|
|<span data-ttu-id="948bc-124">Transport</span><span class="sxs-lookup"><span data-stu-id="948bc-124">Transport</span></span>|<span data-ttu-id="948bc-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="948bc-125">HTTPS</span></span>|
|<span data-ttu-id="948bc-126">Привязка</span><span class="sxs-lookup"><span data-stu-id="948bc-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a><span data-ttu-id="948bc-127">Служба</span><span class="sxs-lookup"><span data-stu-id="948bc-127">Service</span></span>

<span data-ttu-id="948bc-128">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="948bc-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="948bc-129">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="948bc-129">Do one of the following:</span></span>

- <span data-ttu-id="948bc-130">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="948bc-130">Create a stand-alone service using the code with no configuration.</span></span>

- <span data-ttu-id="948bc-131">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="948bc-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>

### <a name="code"></a><span data-ttu-id="948bc-132">Код</span><span class="sxs-lookup"><span data-stu-id="948bc-132">Code</span></span>

<span data-ttu-id="948bc-133">В следующем коде показано создание конечной точки с использованием безопасности транспорта:</span><span class="sxs-lookup"><span data-stu-id="948bc-133">The following code shows how to create an endpoint using transport security:</span></span>

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a><span data-ttu-id="948bc-134">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="948bc-134">Configuration</span></span>

<span data-ttu-id="948bc-135">В следующем коде настраивается та же конечная точка с использованием конфигурации.</span><span class="sxs-lookup"><span data-stu-id="948bc-135">The following code sets up the same endpoint using configuration.</span></span> <span data-ttu-id="948bc-136">Проверка подлинности клиента не выполняется никаким механизмом и, следовательно, клиент является анонимным.</span><span class="sxs-lookup"><span data-stu-id="948bc-136">The client is not authenticated by any mechanism, and is therefore anonymous.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
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

## <a name="client"></a><span data-ttu-id="948bc-137">"Клиент";</span><span class="sxs-lookup"><span data-stu-id="948bc-137">Client</span></span>

<span data-ttu-id="948bc-138">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="948bc-138">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="948bc-139">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="948bc-139">Do one of the following:</span></span>

- <span data-ttu-id="948bc-140">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="948bc-140">Create a stand-alone client using the code (and client code).</span></span>

- <span data-ttu-id="948bc-141">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="948bc-141">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="948bc-142">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="948bc-142">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="948bc-143">Пример:</span><span class="sxs-lookup"><span data-stu-id="948bc-143">For example:</span></span>

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a><span data-ttu-id="948bc-144">Код</span><span class="sxs-lookup"><span data-stu-id="948bc-144">Code</span></span>

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a><span data-ttu-id="948bc-145">Параметр Configuration</span><span class="sxs-lookup"><span data-stu-id="948bc-145">Configuration</span></span>

<span data-ttu-id="948bc-146">Вместо кода для настройки службы можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="948bc-146">The following configuration can be used instead of the code to set up the service.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="948bc-147">См. также</span><span class="sxs-lookup"><span data-stu-id="948bc-147">See also</span></span>

- [<span data-ttu-id="948bc-148">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="948bc-148">Security Overview</span></span>](security-overview.md)
- [<span data-ttu-id="948bc-149">Безопасность транспорта WS</span><span class="sxs-lookup"><span data-stu-id="948bc-149">WS Transport Security</span></span>](../samples/ws-transport-security.md)
- [<span data-ttu-id="948bc-150">Общие сведения о безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="948bc-150">Transport Security Overview</span></span>](transport-security-overview.md)
- <span data-ttu-id="948bc-151">[Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="948bc-151">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>