---
title: <security> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 806cf8524ed1a1439ca85a4b918e8e486e5dc94b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936586"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="2206b-102">\<> безопасности > \<WebHttpBinding</span><span class="sxs-lookup"><span data-stu-id="2206b-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="2206b-103">Указывает требования к безопасности для конечной точки, [ \<](webhttpbinding.md)настроенной с помощью > WebHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="2206b-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
 <span data-ttu-id="2206b-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2206b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2206b-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="2206b-105">\<bindings></span></span>  
<span data-ttu-id="2206b-106">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="2206b-106">\<webHttpBinding></span></span>  
<span data-ttu-id="2206b-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2206b-107">\<binding></span></span>  
<span data-ttu-id="2206b-108">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="2206b-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2206b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2206b-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2206b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2206b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2206b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2206b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2206b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2206b-112">Attributes</span></span>  
  
|<span data-ttu-id="2206b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2206b-113">Attribute</span></span>|<span data-ttu-id="2206b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2206b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2206b-115">режим</span><span class="sxs-lookup"><span data-stu-id="2206b-115">mode</span></span>|<span data-ttu-id="2206b-116">Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется.</span><span class="sxs-lookup"><span data-stu-id="2206b-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="2206b-117">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="2206b-117">The default is `None`.</span></span> <span data-ttu-id="2206b-118">Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2206b-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="2206b-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="2206b-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="2206b-120">Значение</span><span class="sxs-lookup"><span data-stu-id="2206b-120">Value</span></span>|<span data-ttu-id="2206b-121">Описание</span><span class="sxs-lookup"><span data-stu-id="2206b-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2206b-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="2206b-122">None</span></span>|<span data-ttu-id="2206b-123">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="2206b-123">Security is disabled.</span></span>|  
|<span data-ttu-id="2206b-124">Transport</span><span class="sxs-lookup"><span data-stu-id="2206b-124">Transport</span></span>|<span data-ttu-id="2206b-125">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2206b-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="2206b-126">Необходимо настроить службу с использованием SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="2206b-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="2206b-127">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="2206b-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="2206b-128">Проверка подлинности клиента контролируется `ClientCredentialType` с помощью атрибута [ \<транспортного >](transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="2206b-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="2206b-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="2206b-129">TransportCredentialOnly</span></span>|<span data-ttu-id="2206b-130">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="2206b-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="2206b-131">Он обеспечивает проверку подлинности клиента на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="2206b-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="2206b-132">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="2206b-132">This mode should be used with caution.</span></span> <span data-ttu-id="2206b-133">Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="2206b-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2206b-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2206b-134">Child Elements</span></span>  
  
|<span data-ttu-id="2206b-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="2206b-135">Element</span></span>|<span data-ttu-id="2206b-136">Описание</span><span class="sxs-lookup"><span data-stu-id="2206b-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2206b-137">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="2206b-137">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="2206b-138">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="2206b-138">Defines the transport security settings.</span></span> <span data-ttu-id="2206b-139">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="2206b-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2206b-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2206b-140">Parent Elements</span></span>  
  
|<span data-ttu-id="2206b-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="2206b-141">Element</span></span>|<span data-ttu-id="2206b-142">Описание</span><span class="sxs-lookup"><span data-stu-id="2206b-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2206b-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="2206b-143">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="2206b-144">Элемент Binding, который используется для настройки конечных точек для веб-служб Windows Communication Foundation (WCF), которые реагируют на запросы HTTP, а не сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="2206b-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2206b-145">См. также</span><span class="sxs-lookup"><span data-stu-id="2206b-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="2206b-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2206b-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2206b-147">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="2206b-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2206b-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="2206b-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2206b-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="2206b-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2206b-150">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2206b-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2206b-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="2206b-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="2206b-152">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="2206b-152">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
