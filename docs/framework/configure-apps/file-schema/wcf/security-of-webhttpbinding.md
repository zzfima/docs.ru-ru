---
title: <security> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 2f0bc97e10fcd72f2f33cc20730320cbbfc42dd8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399765"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="4f805-102">\<> безопасности > \<WebHttpBinding</span><span class="sxs-lookup"><span data-stu-id="4f805-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="4f805-103">Указывает требования к безопасности для конечной точки, [ \<](webhttpbinding.md)настроенной с помощью > WebHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="4f805-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
<span data-ttu-id="4f805-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4f805-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4f805-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4f805-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4f805-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4f805-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4f805-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<webHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4f805-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="4f805-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="4f805-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4f805-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**</span><span class="sxs-lookup"><span data-stu-id="4f805-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f805-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f805-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f805-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4f805-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4f805-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4f805-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f805-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4f805-113">Attributes</span></span>  
  
|<span data-ttu-id="4f805-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4f805-114">Attribute</span></span>|<span data-ttu-id="4f805-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4f805-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f805-116">режим</span><span class="sxs-lookup"><span data-stu-id="4f805-116">mode</span></span>|<span data-ttu-id="4f805-117">Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется.</span><span class="sxs-lookup"><span data-stu-id="4f805-117">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="4f805-118">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="4f805-118">The default is `None`.</span></span> <span data-ttu-id="4f805-119">Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="4f805-119">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4f805-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="4f805-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="4f805-121">Значение</span><span class="sxs-lookup"><span data-stu-id="4f805-121">Value</span></span>|<span data-ttu-id="4f805-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4f805-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4f805-123">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="4f805-123">None</span></span>|<span data-ttu-id="4f805-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="4f805-124">Security is disabled.</span></span>|  
|<span data-ttu-id="4f805-125">Transport</span><span class="sxs-lookup"><span data-stu-id="4f805-125">Transport</span></span>|<span data-ttu-id="4f805-126">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4f805-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="4f805-127">Необходимо настроить службу с использованием SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="4f805-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="4f805-128">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="4f805-128">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="4f805-129">Проверка подлинности клиента контролируется `ClientCredentialType` с помощью атрибута [ \<транспортного >](transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4f805-129">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="4f805-130">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="4f805-130">TransportCredentialOnly</span></span>|<span data-ttu-id="4f805-131">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="4f805-131">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="4f805-132">Он обеспечивает проверку подлинности клиента на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="4f805-132">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="4f805-133">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="4f805-133">This mode should be used with caution.</span></span> <span data-ttu-id="4f805-134">Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="4f805-134">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f805-135">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4f805-135">Child Elements</span></span>  
  
|<span data-ttu-id="4f805-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f805-136">Element</span></span>|<span data-ttu-id="4f805-137">Описание</span><span class="sxs-lookup"><span data-stu-id="4f805-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f805-138">\<> транспорта</span><span class="sxs-lookup"><span data-stu-id="4f805-138">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="4f805-139">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="4f805-139">Defines the transport security settings.</span></span> <span data-ttu-id="4f805-140">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="4f805-140">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4f805-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4f805-141">Parent Elements</span></span>  
  
|<span data-ttu-id="4f805-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="4f805-142">Element</span></span>|<span data-ttu-id="4f805-143">Описание</span><span class="sxs-lookup"><span data-stu-id="4f805-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f805-144">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4f805-144">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="4f805-145">Элемент Binding, который используется для настройки конечных точек для веб-служб Windows Communication Foundation (WCF), которые реагируют на запросы HTTP, а не сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="4f805-145">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f805-146">См. также</span><span class="sxs-lookup"><span data-stu-id="4f805-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="4f805-147">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4f805-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4f805-148">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="4f805-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="4f805-149">Привязки</span><span class="sxs-lookup"><span data-stu-id="4f805-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4f805-150">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="4f805-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4f805-151">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4f805-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4f805-152">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4f805-152">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="4f805-153">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="4f805-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
