---
title: <security> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: b6375a64ea157df01f903901e0414a2989287aee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670460"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="9ab6f-102">\<Безопасность > из \<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9ab6f-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="9ab6f-103">Задает требования к безопасности для конечной точки, настроенной с [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9ab6f-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="9ab6f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="9ab6f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ab6f-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="9ab6f-105">\<bindings></span></span>  
<span data-ttu-id="9ab6f-106">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="9ab6f-106">\<webHttpBinding></span></span>  
<span data-ttu-id="9ab6f-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="9ab6f-107">\<binding></span></span>  
<span data-ttu-id="9ab6f-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="9ab6f-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ab6f-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ab6f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ab6f-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9ab6f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9ab6f-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ab6f-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ab6f-112">Attributes</span></span>  
  
|<span data-ttu-id="9ab6f-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9ab6f-113">Attribute</span></span>|<span data-ttu-id="9ab6f-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab6f-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ab6f-115">режим</span><span class="sxs-lookup"><span data-stu-id="9ab6f-115">mode</span></span>|<span data-ttu-id="9ab6f-116">Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="9ab6f-117">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-117">The default is `None`.</span></span> <span data-ttu-id="9ab6f-118">Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="9ab6f-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="9ab6f-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="9ab6f-120">Значение</span><span class="sxs-lookup"><span data-stu-id="9ab6f-120">Value</span></span>|<span data-ttu-id="9ab6f-121">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab6f-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ab6f-122">Нет</span><span class="sxs-lookup"><span data-stu-id="9ab6f-122">None</span></span>|<span data-ttu-id="9ab6f-123">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-123">Security is disabled.</span></span>|  
|<span data-ttu-id="9ab6f-124">Transport</span><span class="sxs-lookup"><span data-stu-id="9ab6f-124">Transport</span></span>|<span data-ttu-id="9ab6f-125">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="9ab6f-126">Необходимо настроить службу с использованием SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="9ab6f-127">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="9ab6f-128">Проверка подлинности клиента контролируется посредством `ClientCredentialType` атрибут [ \<транспорта >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="9ab6f-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="9ab6f-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="9ab6f-129">TransportCredentialOnly</span></span>|<span data-ttu-id="9ab6f-130">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="9ab6f-131">Он обеспечивает проверку подлинности клиента на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="9ab6f-132">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-132">This mode should be used with caution.</span></span> <span data-ttu-id="9ab6f-133">Он должен использоваться в средах, где безопасность транспорта обеспечивается другими средствами (например, IPSec), а только проверку подлинности клиента с помощью инфраструктуры WCF.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ab6f-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ab6f-134">Child Elements</span></span>  
  
|<span data-ttu-id="9ab6f-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ab6f-135">Element</span></span>|<span data-ttu-id="9ab6f-136">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab6f-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ab6f-137">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="9ab6f-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="9ab6f-138">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-138">Defines the transport security settings.</span></span> <span data-ttu-id="9ab6f-139">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ab6f-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ab6f-140">Parent Elements</span></span>  
  
|<span data-ttu-id="9ab6f-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ab6f-141">Element</span></span>|<span data-ttu-id="9ab6f-142">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab6f-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ab6f-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="9ab6f-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="9ab6f-144">Элемент привязки, который используется для настройки конечных точек для Windows Communication Foundation (WCF) веб-служб, которые отвечают на запросы HTTP вместо сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="9ab6f-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ab6f-145">См. также</span><span class="sxs-lookup"><span data-stu-id="9ab6f-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="9ab6f-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="9ab6f-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="9ab6f-147">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="9ab6f-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="9ab6f-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="9ab6f-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9ab6f-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="9ab6f-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="9ab6f-150">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="9ab6f-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="9ab6f-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="9ab6f-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="9ab6f-152">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="9ab6f-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
