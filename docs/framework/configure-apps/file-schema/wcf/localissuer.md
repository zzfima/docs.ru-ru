---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: 055b7b49d1f775d49ac20de18c18ca0433716a23
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397867"
---
# <a name="localissuer"></a><span data-ttu-id="d31f9-101">\<Локалиссуер ></span><span class="sxs-lookup"><span data-stu-id="d31f9-101">\<localIssuer></span></span>
<span data-ttu-id="d31f9-102">Указывает адрес и привязку локального издателя, используемого для получения маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="d31f9-102">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
<span data-ttu-id="d31f9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d31f9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d31f9-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d31f9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="d31f9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d31f9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="d31f9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d31f9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="d31f9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d31f9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="d31f9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="d31f9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="d31f9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedToken >** ](issuedtoken.md)</span><span class="sxs-lookup"><span data-stu-id="d31f9-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)</span></span>\
<span data-ttu-id="d31f9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Локалиссуер >**</span><span class="sxs-lookup"><span data-stu-id="d31f9-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d31f9-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d31f9-111">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d31f9-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d31f9-112">Attributes and Elements</span></span>  
 <span data-ttu-id="d31f9-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d31f9-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d31f9-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d31f9-114">Attributes</span></span>  
  
|<span data-ttu-id="d31f9-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d31f9-115">Attribute</span></span>|<span data-ttu-id="d31f9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d31f9-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d31f9-117">адрес</span><span class="sxs-lookup"><span data-stu-id="d31f9-117">address</span></span>|<span data-ttu-id="d31f9-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="d31f9-118">Required string.</span></span> <span data-ttu-id="d31f9-119">Указывает универсальный код ресурса (URI) локального издателя.</span><span class="sxs-lookup"><span data-stu-id="d31f9-119">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="d31f9-120">привязка</span><span class="sxs-lookup"><span data-stu-id="d31f9-120">binding</span></span>|<span data-ttu-id="d31f9-121">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="d31f9-121">Optional string.</span></span> <span data-ttu-id="d31f9-122">Одна из привязок, предоставляемых системой.</span><span class="sxs-lookup"><span data-stu-id="d31f9-122">One of the system-provided bindings.</span></span> <span data-ttu-id="d31f9-123">Список см. в разделе [привязки, предоставляемые системой](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="d31f9-123">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="d31f9-124">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d31f9-124">bindingConfiguration</span></span>|<span data-ttu-id="d31f9-125">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="d31f9-125">Optional string.</span></span> <span data-ttu-id="d31f9-126">Указывает конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d31f9-126">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d31f9-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d31f9-127">Child Elements</span></span>  
  
|<span data-ttu-id="d31f9-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="d31f9-128">Element</span></span>|<span data-ttu-id="d31f9-129">Описание</span><span class="sxs-lookup"><span data-stu-id="d31f9-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d31f9-130">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="d31f9-130">\<identity></span></span>](identity.md)|<span data-ttu-id="d31f9-131">Указывает идентификационные данные для локального издателя.</span><span class="sxs-lookup"><span data-stu-id="d31f9-131">Specifies identity information for the local issuer.</span></span>|  
|[<span data-ttu-id="d31f9-132">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="d31f9-132">\<headers></span></span>](headers-element.md)|<span data-ttu-id="d31f9-133">Коллекция заголовков адреса, требуемых для правильного обращения к локальному издателю.</span><span class="sxs-lookup"><span data-stu-id="d31f9-133">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="d31f9-134">Заголовок в эту коллекцию можно добавить с помощью ключевого слова `add`.</span><span class="sxs-lookup"><span data-stu-id="d31f9-134">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d31f9-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d31f9-135">Parent Elements</span></span>  
  
|<span data-ttu-id="d31f9-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="d31f9-136">Element</span></span>|<span data-ttu-id="d31f9-137">Описание</span><span class="sxs-lookup"><span data-stu-id="d31f9-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d31f9-138">\<issuedToken ></span><span class="sxs-lookup"><span data-stu-id="d31f9-138">\<issuedToken></span></span>](issuedtoken.md)|<span data-ttu-id="d31f9-139">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="d31f9-139">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d31f9-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="d31f9-140">Remarks</span></span>  
 <span data-ttu-id="d31f9-141">При получении маркера от службы маркеров безопасности (STS) в клиентском приложении должны быть заданы адрес и привязка для установления соединения с STS.</span><span class="sxs-lookup"><span data-stu-id="d31f9-141">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="d31f9-142">Если компонент не предоставляет URL-адрес для службы маркеров безопасности или если адресом издателя Федеративной привязки является `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` или `null`, канал Windows Communication Foundation клиента (WCF) использует значения, заданные параметром <xref:System.ServiceModel.WSFederationHttpBinding> `address` и`binding` для взаимодействия с STS для получения выданного маркера.</span><span class="sxs-lookup"><span data-stu-id="d31f9-142">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="d31f9-143">Дополнительные сведения о настройке локального издателя см. в разделе [как Настройка локального издателя](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="d31f9-143">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d31f9-144">Пример</span><span class="sxs-lookup"><span data-stu-id="d31f9-144">Example</span></span>  
 <span data-ttu-id="d31f9-145">В следующем примере устанавливаются атрибуты `address`, `binding` и `bindingConfiguration` элемента `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="d31f9-145">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d31f9-146">См. также</span><span class="sxs-lookup"><span data-stu-id="d31f9-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="d31f9-147">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="d31f9-147">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d31f9-148">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="d31f9-148">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="d31f9-149">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="d31f9-149">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="d31f9-150">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="d31f9-150">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="d31f9-151">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="d31f9-151">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="d31f9-152">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d31f9-152">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="d31f9-153">Защита клиентов</span><span class="sxs-lookup"><span data-stu-id="d31f9-153">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="d31f9-154">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="d31f9-154">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="d31f9-155">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="d31f9-155">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
