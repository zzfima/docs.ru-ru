---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: a70c694509cd35e9bff7d56ae278da93b9b2b9ce
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273037"
---
# <a name="issuedtoken"></a><span data-ttu-id="17372-101">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="17372-101">\<issuedToken></span></span>
<span data-ttu-id="17372-102">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="17372-102">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
 <span data-ttu-id="17372-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="17372-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="17372-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="17372-104">\<behaviors></span></span>  
<span data-ttu-id="17372-105">раздел endpointBehaviors</span><span class="sxs-lookup"><span data-stu-id="17372-105">endpointBehaviors section</span></span>  
<span data-ttu-id="17372-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="17372-106">\<behavior></span></span>  
<span data-ttu-id="17372-107">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="17372-107">\<clientCredentials></span></span>  
<span data-ttu-id="17372-108">\<issuedToken></span><span class="sxs-lookup"><span data-stu-id="17372-108">\<issuedToken></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17372-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="17372-109">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17372-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="17372-110">Attributes and Elements</span></span>  
 <span data-ttu-id="17372-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="17372-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17372-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="17372-112">Attributes</span></span>  
  
|<span data-ttu-id="17372-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="17372-113">Attribute</span></span>|<span data-ttu-id="17372-114">Описание</span><span class="sxs-lookup"><span data-stu-id="17372-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="17372-115">Дополнительный логический атрибут, указывающий, выполняется ли кэширование маркеров.</span><span class="sxs-lookup"><span data-stu-id="17372-115">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="17372-116">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="17372-116">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="17372-117">Дополнительный строковый атрибут, указывающий, какие случайные значения (показатели энтропии) используются для операций «рукопожатия».</span><span class="sxs-lookup"><span data-stu-id="17372-117">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="17372-118">Допустимы следующие значения: `ClientEntropy`, `ServerEntropy` и `CombinedEntropy`. Значение по умолчанию - `CombinedEntropy`.</span><span class="sxs-lookup"><span data-stu-id="17372-118">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="17372-119">Это атрибут типа <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span><span class="sxs-lookup"><span data-stu-id="17372-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="17372-120">Дополнительный целочисленный атрибут, задающий время в процентах от срока действия (предоставляемого издателем маркера), которое может пройти до обновления маркера.</span><span class="sxs-lookup"><span data-stu-id="17372-120">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="17372-121">Диапазон значений: 0–100.</span><span class="sxs-lookup"><span data-stu-id="17372-121">Values are from 0 to 100.</span></span> <span data-ttu-id="17372-122">Значение по умолчанию, равное 60, указывает, что попытка возобновления предпринимается по истечении 60% времени.</span><span class="sxs-lookup"><span data-stu-id="17372-122">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="17372-123">Дополнительный атрибут, определяющий поведения канала во время связи с издателем.</span><span class="sxs-lookup"><span data-stu-id="17372-123">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="17372-124">Дополнительный атрибут, определяющий поведения канала во время связи с локальным издателем.</span><span class="sxs-lookup"><span data-stu-id="17372-124">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="17372-125">Дополнительный атрибут Timespan, задающий промежуток времени, в течение которого выданные маркеры сохраняются в кэше, если время не указывается издателем маркера (службой маркеров безопасности).</span><span class="sxs-lookup"><span data-stu-id="17372-125">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="17372-126">Значение по умолчанию — «10675199.02:48:05.4775807.»</span><span class="sxs-lookup"><span data-stu-id="17372-126">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17372-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="17372-127">Child Elements</span></span>  
  
|<span data-ttu-id="17372-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="17372-128">Element</span></span>|<span data-ttu-id="17372-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="17372-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17372-130">\<localIssuer ></span><span class="sxs-lookup"><span data-stu-id="17372-130">\<localIssuer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|<span data-ttu-id="17372-131">Определяет адрес локального издателя маркера и привязку, используемую для взаимодействия с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="17372-131">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[<span data-ttu-id="17372-132">\<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="17372-132">\<issuerChannelBehaviors></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|<span data-ttu-id="17372-133">Задает поведения конечной точки, используемое при связи с локальным издателем.</span><span class="sxs-lookup"><span data-stu-id="17372-133">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="17372-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="17372-134">Parent Elements</span></span>  
  
|<span data-ttu-id="17372-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="17372-135">Element</span></span>|<span data-ttu-id="17372-136">Описание:</span><span class="sxs-lookup"><span data-stu-id="17372-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17372-137">\<clientCredentials></span><span class="sxs-lookup"><span data-stu-id="17372-137">\<clientCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|<span data-ttu-id="17372-138">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="17372-138">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17372-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="17372-139">Remarks</span></span>  
 <span data-ttu-id="17372-140">Выданный маркер представляет собой пользовательские учетные данные, используемые, например, при проверке подлинности с помощью службы маркеров безопасности при федеративном доступе.</span><span class="sxs-lookup"><span data-stu-id="17372-140">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="17372-141">По умолчанию используется маркер SAML.</span><span class="sxs-lookup"><span data-stu-id="17372-141">By default, the token is a SAML token.</span></span> <span data-ttu-id="17372-142">Дополнительные сведения см. в разделе [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="17372-142">For more information, see [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span> <span data-ttu-id="17372-143">и [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="17372-143">and [Federation and Issued Tokens](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="17372-144">Этот раздел содержит элементы, используемые для настройки локального издателя маркеров, или поведения, используемые при работе со службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="17372-144">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="17372-145">Инструкции по настройке клиента для использования локального издателя, см. в разделе [как: Настройка локального издателя](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="17372-145">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17372-146">См. также</span><span class="sxs-lookup"><span data-stu-id="17372-146">See also</span></span>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="17372-147">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="17372-147">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="17372-148">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="17372-148">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="17372-149">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="17372-149">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="17372-150">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="17372-150">Securing Clients</span></span>](../../../../../docs/framework/wcf/securing-clients.md)
- [<span data-ttu-id="17372-151">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="17372-151">How to: Create a Federated Client</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="17372-152">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="17372-152">How to: Configure a Local Issuer</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="17372-153">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="17372-153">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
