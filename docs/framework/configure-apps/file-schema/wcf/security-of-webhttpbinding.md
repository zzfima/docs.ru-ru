---
title: <security> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738635"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="f5789-102">\<> безопасности \<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f5789-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="f5789-103">Указывает требования к безопасности для конечной точки, настроенной с помощью [\<webHttpBinding >](webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f5789-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
<span data-ttu-id="f5789-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5789-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f5789-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f5789-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f5789-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="f5789-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="f5789-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="f5789-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="f5789-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="f5789-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="f5789-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<security >**</span><span class="sxs-lookup"><span data-stu-id="f5789-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5789-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f5789-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5789-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f5789-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f5789-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f5789-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5789-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f5789-113">Attributes</span></span>  
  
|<span data-ttu-id="f5789-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f5789-114">Attribute</span></span>|<span data-ttu-id="f5789-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f5789-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5789-116">режим</span><span class="sxs-lookup"><span data-stu-id="f5789-116">mode</span></span>|<span data-ttu-id="f5789-117">Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется.</span><span class="sxs-lookup"><span data-stu-id="f5789-117">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="f5789-118">Значение по умолчанию: `None`.</span><span class="sxs-lookup"><span data-stu-id="f5789-118">The default is `None`.</span></span> <span data-ttu-id="f5789-119">Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="f5789-119">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="f5789-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="f5789-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="f5789-121">значения</span><span class="sxs-lookup"><span data-stu-id="f5789-121">Value</span></span>|<span data-ttu-id="f5789-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f5789-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f5789-123">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f5789-123">None</span></span>|<span data-ttu-id="f5789-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="f5789-124">Security is disabled.</span></span>|  
|<span data-ttu-id="f5789-125">Transport</span><span class="sxs-lookup"><span data-stu-id="f5789-125">Transport</span></span>|<span data-ttu-id="f5789-126">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f5789-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="f5789-127">Необходимо настроить службу с использованием SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="f5789-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="f5789-128">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="f5789-128">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="f5789-129">Проверка подлинности клиента контролируется с помощью атрибута `ClientCredentialType` [> транспорта\<](transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f5789-129">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="f5789-130">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="f5789-130">TransportCredentialOnly</span></span>|<span data-ttu-id="f5789-131">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="f5789-131">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="f5789-132">Он обеспечивает проверку подлинности клиента на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="f5789-132">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="f5789-133">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="f5789-133">This mode should be used with caution.</span></span> <span data-ttu-id="f5789-134">Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="f5789-134">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5789-135">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f5789-135">Child Elements</span></span>  
  
|<span data-ttu-id="f5789-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="f5789-136">Element</span></span>|<span data-ttu-id="f5789-137">Описание</span><span class="sxs-lookup"><span data-stu-id="f5789-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5789-138">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="f5789-138">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="f5789-139">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="f5789-139">Defines the transport security settings.</span></span> <span data-ttu-id="f5789-140">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="f5789-140">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f5789-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f5789-141">Parent Elements</span></span>  
  
|<span data-ttu-id="f5789-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="f5789-142">Element</span></span>|<span data-ttu-id="f5789-143">Описание</span><span class="sxs-lookup"><span data-stu-id="f5789-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f5789-144">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="f5789-144">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="f5789-145">Элемент Binding, который используется для настройки конечных точек для веб-служб Windows Communication Foundation (WCF), которые реагируют на запросы HTTP, а не сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="f5789-145">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5789-146">См. также</span><span class="sxs-lookup"><span data-stu-id="f5789-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="f5789-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f5789-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f5789-148">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="f5789-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="f5789-149">Привязки</span><span class="sxs-lookup"><span data-stu-id="f5789-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f5789-150">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f5789-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="f5789-151">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f5789-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="f5789-152">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="f5789-152">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="f5789-153">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="f5789-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
