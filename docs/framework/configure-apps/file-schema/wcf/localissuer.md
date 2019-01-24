---
title: '&lt;localIssuer&gt;'
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 893ac2cb0e6c54beae68e2607c31564baafd95fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527553"
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="71912-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="71912-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="71912-103">Указывает адрес и привязку локального издателя, используемого для получения маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="71912-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="71912-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="71912-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="71912-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="71912-105">\<behaviors></span></span>  
<span data-ttu-id="71912-106">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="71912-106">endpointBehaviors section</span></span>  
<span data-ttu-id="71912-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="71912-107">\<behavior></span></span>  
<span data-ttu-id="71912-108">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="71912-108">\<clientCredentials></span></span>  
<span data-ttu-id="71912-109">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="71912-109">\<issuedToken></span></span>  
<span data-ttu-id="71912-110">\<localIssuer></span><span class="sxs-lookup"><span data-stu-id="71912-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71912-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="71912-111">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71912-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="71912-112">Attributes and Elements</span></span>  
 <span data-ttu-id="71912-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="71912-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71912-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="71912-114">Attributes</span></span>  
  
|<span data-ttu-id="71912-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="71912-115">Attribute</span></span>|<span data-ttu-id="71912-116">Описание</span><span class="sxs-lookup"><span data-stu-id="71912-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71912-117">address</span><span class="sxs-lookup"><span data-stu-id="71912-117">address</span></span>|<span data-ttu-id="71912-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="71912-118">Required string.</span></span> <span data-ttu-id="71912-119">Указывает универсальный код ресурса (URI) локального издателя.</span><span class="sxs-lookup"><span data-stu-id="71912-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="71912-120">привязка</span><span class="sxs-lookup"><span data-stu-id="71912-120">binding</span></span>|<span data-ttu-id="71912-121">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="71912-121">Optional string.</span></span> <span data-ttu-id="71912-122">Одна из привязок, предоставляемых системой.</span><span class="sxs-lookup"><span data-stu-id="71912-122">One of the system-provided bindings.</span></span> <span data-ttu-id="71912-123">Список, см. в разделе [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="71912-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="71912-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="71912-124">bindingConfiguration</span></span>|<span data-ttu-id="71912-125">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="71912-125">Optional string.</span></span> <span data-ttu-id="71912-126">Указывает конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="71912-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71912-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="71912-127">Child Elements</span></span>  
  
|<span data-ttu-id="71912-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="71912-128">Element</span></span>|<span data-ttu-id="71912-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="71912-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71912-130">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="71912-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="71912-131">Указывает идентификационные данные для локального издателя.</span><span class="sxs-lookup"><span data-stu-id="71912-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="71912-132">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="71912-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="71912-133">Коллекция заголовков адреса, требуемых для правильного обращения к локальному издателю.</span><span class="sxs-lookup"><span data-stu-id="71912-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="71912-134">Заголовок в эту коллекцию можно добавить с помощью ключевого слова `add`.</span><span class="sxs-lookup"><span data-stu-id="71912-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71912-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="71912-135">Parent Elements</span></span>  
  
|<span data-ttu-id="71912-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="71912-136">Element</span></span>|<span data-ttu-id="71912-137">Описание</span><span class="sxs-lookup"><span data-stu-id="71912-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71912-138">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="71912-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="71912-139">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="71912-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="71912-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="71912-140">Remarks</span></span>  
 <span data-ttu-id="71912-141">При получении маркера от службы маркеров безопасности (STS) в клиентском приложении должны быть заданы адрес и привязка для установления соединения с STS.</span><span class="sxs-lookup"><span data-stu-id="71912-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="71912-142">Когда <xref:System.ServiceModel.WSFederationHttpBinding> не поддерживает URL-адрес для службы маркеров безопасности, или если адрес издателя федеративной привязки имеет `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` или `null`, канал клиента Windows Communication Foundation (WCF) использует значения, указанные в `address`и `binding` для обмена данными с STS и получения выданного маркера.</span><span class="sxs-lookup"><span data-stu-id="71912-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="71912-143">Дополнительные сведения о настройке локального издателя см. в разделе [как: Настройка локального издателя](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="71912-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71912-144">Пример</span><span class="sxs-lookup"><span data-stu-id="71912-144">Example</span></span>  
 <span data-ttu-id="71912-145">В следующем примере устанавливаются атрибуты `address`, `binding` и `bindingConfiguration` элемента `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="71912-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="71912-146">См. также</span><span class="sxs-lookup"><span data-stu-id="71912-146">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="71912-147">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="71912-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="71912-148">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="71912-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="71912-149">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="71912-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="71912-150">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="71912-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="71912-151">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="71912-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="71912-152">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="71912-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="71912-153">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="71912-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="71912-154">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="71912-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="71912-155">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="71912-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
