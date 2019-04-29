---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 9a51387cd75d57a6828ecde1dcd788b056f7e27a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766406"
---
# <a name="localissuer"></a><span data-ttu-id="b48a0-101">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="b48a0-101">\<localIssuer></span></span>
<span data-ttu-id="b48a0-102">Указывает адрес и привязку локального издателя, используемого для получения маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="b48a0-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="b48a0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b48a0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="b48a0-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="b48a0-104">\<behaviors></span></span>  
<span data-ttu-id="b48a0-105">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="b48a0-105">endpointBehaviors section</span></span>  
<span data-ttu-id="b48a0-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="b48a0-106">\<behavior></span></span>  
<span data-ttu-id="b48a0-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="b48a0-107">\<clientCredentials></span></span>  
<span data-ttu-id="b48a0-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="b48a0-108">\<issuedToken></span></span>  
<span data-ttu-id="b48a0-109">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="b48a0-109">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b48a0-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b48a0-110">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b48a0-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b48a0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b48a0-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b48a0-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b48a0-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b48a0-113">Attributes</span></span>  
  
|<span data-ttu-id="b48a0-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b48a0-114">Attribute</span></span>|<span data-ttu-id="b48a0-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b48a0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b48a0-116">адрес</span><span class="sxs-lookup"><span data-stu-id="b48a0-116">address</span></span>|<span data-ttu-id="b48a0-117">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="b48a0-117">Required string.</span></span> <span data-ttu-id="b48a0-118">Указывает универсальный код ресурса (URI) локального издателя.</span><span class="sxs-lookup"><span data-stu-id="b48a0-118">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="b48a0-119">привязка</span><span class="sxs-lookup"><span data-stu-id="b48a0-119">binding</span></span>|<span data-ttu-id="b48a0-120">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="b48a0-120">Optional string.</span></span> <span data-ttu-id="b48a0-121">Одна из привязок, предоставляемых системой.</span><span class="sxs-lookup"><span data-stu-id="b48a0-121">One of the system-provided bindings.</span></span> <span data-ttu-id="b48a0-122">Список, см. в разделе [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="b48a0-122">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="b48a0-123">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b48a0-123">bindingConfiguration</span></span>|<span data-ttu-id="b48a0-124">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="b48a0-124">Optional string.</span></span> <span data-ttu-id="b48a0-125">Указывает конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b48a0-125">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b48a0-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b48a0-126">Child Elements</span></span>  
  
|<span data-ttu-id="b48a0-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="b48a0-127">Element</span></span>|<span data-ttu-id="b48a0-128">Описание</span><span class="sxs-lookup"><span data-stu-id="b48a0-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b48a0-129">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="b48a0-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="b48a0-130">Указывает идентификационные данные для локального издателя.</span><span class="sxs-lookup"><span data-stu-id="b48a0-130">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="b48a0-131">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="b48a0-131">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="b48a0-132">Коллекция заголовков адреса, требуемых для правильного обращения к локальному издателю.</span><span class="sxs-lookup"><span data-stu-id="b48a0-132">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="b48a0-133">Заголовок в эту коллекцию можно добавить с помощью ключевого слова `add`.</span><span class="sxs-lookup"><span data-stu-id="b48a0-133">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b48a0-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b48a0-134">Parent Elements</span></span>  
  
|<span data-ttu-id="b48a0-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="b48a0-135">Element</span></span>|<span data-ttu-id="b48a0-136">Описание</span><span class="sxs-lookup"><span data-stu-id="b48a0-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b48a0-137">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="b48a0-137">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="b48a0-138">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="b48a0-138">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b48a0-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="b48a0-139">Remarks</span></span>  
 <span data-ttu-id="b48a0-140">При получении маркера от службы маркеров безопасности (STS) в клиентском приложении должны быть заданы адрес и привязка для установления соединения с STS.</span><span class="sxs-lookup"><span data-stu-id="b48a0-140">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="b48a0-141">Когда <xref:System.ServiceModel.WSFederationHttpBinding> не поддерживает URL-адрес для службы маркеров безопасности, или если адрес издателя федеративной привязки имеет `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` или `null`, канал клиента Windows Communication Foundation (WCF) использует значения, указанные в `address`и `binding` для обмена данными с STS и получения выданного маркера.</span><span class="sxs-lookup"><span data-stu-id="b48a0-141">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="b48a0-142">Дополнительные сведения о настройке локального издателя см. в разделе [как: Настройка локального издателя](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="b48a0-142">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b48a0-143">Пример</span><span class="sxs-lookup"><span data-stu-id="b48a0-143">Example</span></span>  
 <span data-ttu-id="b48a0-144">В следующем примере устанавливаются атрибуты `address`, `binding` и `bindingConfiguration` элемента `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="b48a0-144">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="MyEndpointBehavior">
        <clientCredentials>
          <issuedToken cacheIssuedTokens="false"
                       defaultKeyEntropyMode="ClientEntropy">
            <localIssuer address="net.tcp://cohowinery/tokens"
                         binding="netTcpBinding"
                         bindingConfiguration="myTcpBindingConfig" />
          </issuedToken>
        </clientCredentials>
      </behavior>
    </endpointBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="b48a0-145">См. также</span><span class="sxs-lookup"><span data-stu-id="b48a0-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="b48a0-146">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="b48a0-146">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b48a0-147">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="b48a0-147">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="b48a0-148">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="b48a0-148">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b48a0-149">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="b48a0-149">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="b48a0-150">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b48a0-150">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="b48a0-151">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b48a0-151">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b48a0-152">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="b48a0-152">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="b48a0-153">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="b48a0-153">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="b48a0-154">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b48a0-154">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
