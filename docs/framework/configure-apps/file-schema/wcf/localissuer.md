---
title: '&lt;localIssuer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c7e5c28325326d838da851ff4add12f8ae612c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltlocalissuergt"></a><span data-ttu-id="aff85-102">&lt;localIssuer&gt;</span><span class="sxs-lookup"><span data-stu-id="aff85-102">&lt;localIssuer&gt;</span></span>
<span data-ttu-id="aff85-103">Указывает адрес и привязку локального издателя, используемого для получения маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="aff85-103">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
 <span data-ttu-id="aff85-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="aff85-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="aff85-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="aff85-105">\<behaviors></span></span>  
<span data-ttu-id="aff85-106">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="aff85-106">endpointBehaviors section</span></span>  
<span data-ttu-id="aff85-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="aff85-107">\<behavior></span></span>  
<span data-ttu-id="aff85-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="aff85-108">\<clientCredentials></span></span>  
<span data-ttu-id="aff85-109">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="aff85-109">\<issuedToken></span></span>  
<span data-ttu-id="aff85-110">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="aff85-110">\<localIssuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aff85-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aff85-111">Syntax</span></span>  
  
```xml  
<localIssuer address="string"  
      binding="string"  
      bindingConfiguration="string" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aff85-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aff85-112">Attributes and Elements</span></span>  
 <span data-ttu-id="aff85-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aff85-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aff85-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aff85-114">Attributes</span></span>  
  
|<span data-ttu-id="aff85-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aff85-115">Attribute</span></span>|<span data-ttu-id="aff85-116">Описание</span><span class="sxs-lookup"><span data-stu-id="aff85-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aff85-117">address</span><span class="sxs-lookup"><span data-stu-id="aff85-117">address</span></span>|<span data-ttu-id="aff85-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="aff85-118">Required string.</span></span> <span data-ttu-id="aff85-119">Указывает универсальный код ресурса (URI) локального издателя.</span><span class="sxs-lookup"><span data-stu-id="aff85-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="aff85-120">привязка</span><span class="sxs-lookup"><span data-stu-id="aff85-120">binding</span></span>|<span data-ttu-id="aff85-121">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="aff85-121">Optional string.</span></span> <span data-ttu-id="aff85-122">Одна из привязок, предоставляемых системой.</span><span class="sxs-lookup"><span data-stu-id="aff85-122">One of the system-provided bindings.</span></span> <span data-ttu-id="aff85-123">Список см. в разделе [привязка, предоставляемая системой](../../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="aff85-123">For a list, see [System-Provided Bindings](../../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="aff85-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="aff85-124">bindingConfiguration</span></span>|<span data-ttu-id="aff85-125">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="aff85-125">Optional string.</span></span> <span data-ttu-id="aff85-126">Указывает конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="aff85-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aff85-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aff85-127">Child Elements</span></span>  
  
|<span data-ttu-id="aff85-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="aff85-128">Element</span></span>|<span data-ttu-id="aff85-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="aff85-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aff85-130">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="aff85-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="aff85-131">Указывает идентификационные данные для локального издателя.</span><span class="sxs-lookup"><span data-stu-id="aff85-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="aff85-132">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="aff85-132">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="aff85-133">Коллекция заголовков адреса, требуемых для правильного обращения к локальному издателю.</span><span class="sxs-lookup"><span data-stu-id="aff85-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="aff85-134">Заголовок в эту коллекцию можно добавить с помощью ключевого слова `add`.</span><span class="sxs-lookup"><span data-stu-id="aff85-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aff85-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aff85-135">Parent Elements</span></span>  
  
|<span data-ttu-id="aff85-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="aff85-136">Element</span></span>|<span data-ttu-id="aff85-137">Описание:</span><span class="sxs-lookup"><span data-stu-id="aff85-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aff85-138">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="aff85-138">\<issuedToken></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|<span data-ttu-id="aff85-139">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="aff85-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aff85-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="aff85-140">Remarks</span></span>  
 <span data-ttu-id="aff85-141">При получении маркера от службы маркеров безопасности (STS) в клиентском приложении должны быть заданы адрес и привязка для установления соединения с STS.</span><span class="sxs-lookup"><span data-stu-id="aff85-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="aff85-142">Если <xref:System.ServiceModel.WSFederationHttpBinding> не предоставляет URL-адрес для службы маркеров безопасности или адрес издателя федеративной привязки - http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous или `null`, канал [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] клиента использует для обмена данными с STS и получения маркера значения, указанные параметрами `address` и `binding`.</span><span class="sxs-lookup"><span data-stu-id="aff85-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous or `null`, the client's [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="aff85-143">Дополнительные сведения о настройке локального издателя см. в разделе [как: Настройка локального издателя](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="aff85-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="aff85-144">Пример</span><span class="sxs-lookup"><span data-stu-id="aff85-144">Example</span></span>  
 <span data-ttu-id="aff85-145">В следующем примере устанавливаются атрибуты `address`, `binding` и `bindingConfiguration` элемента `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="aff85-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="aff85-146">См. также</span><span class="sxs-lookup"><span data-stu-id="aff85-146">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
 [<span data-ttu-id="aff85-147">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="aff85-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="aff85-148">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="aff85-148">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 [<span data-ttu-id="aff85-149">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="aff85-149">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="aff85-150">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="aff85-150">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="aff85-151">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="aff85-151">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="aff85-152">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="aff85-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="aff85-153">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="aff85-153">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)  
 [<span data-ttu-id="aff85-154">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="aff85-154">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="aff85-155">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="aff85-155">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
