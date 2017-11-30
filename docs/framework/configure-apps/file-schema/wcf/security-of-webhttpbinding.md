---
title: "&lt;security&gt; для &lt;webHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b3d5d00dcc79a746818975a6a8b125d3dc33933b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="90666-102">&lt;security&gt; для &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="90666-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="90666-103">Задает требования безопасности для конечной точки, настроенной с [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="90666-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="90666-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="90666-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="90666-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="90666-105">\<bindings></span></span>  
<span data-ttu-id="90666-106">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="90666-106">\<webHttpBinding></span></span>  
<span data-ttu-id="90666-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="90666-107">\<binding></span></span>  
<span data-ttu-id="90666-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="90666-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90666-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="90666-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
    <bindings>  
        <webHttpBinding>  
            <binding name = "string">  
              <security mode="None/Transport/TransportCredentialOnly">  
                                    <transport clientCredentialType =   
                                     "Basic/Certificate/Digest/None/Ntlm/Windows"  
                                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                                     realm="string" />  
              </security>  
        </webHttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90666-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="90666-110">Attributes and Elements</span></span>  
 <span data-ttu-id="90666-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="90666-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90666-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="90666-112">Attributes</span></span>  
  
|<span data-ttu-id="90666-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="90666-113">Attribute</span></span>|<span data-ttu-id="90666-114">Описание</span><span class="sxs-lookup"><span data-stu-id="90666-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90666-115">режим</span><span class="sxs-lookup"><span data-stu-id="90666-115">mode</span></span>|<span data-ttu-id="90666-116">Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется.</span><span class="sxs-lookup"><span data-stu-id="90666-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="90666-117">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="90666-117">The default is `None`.</span></span> <span data-ttu-id="90666-118">Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="90666-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="90666-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="90666-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="90666-120">Значение</span><span class="sxs-lookup"><span data-stu-id="90666-120">Value</span></span>|<span data-ttu-id="90666-121">Описание</span><span class="sxs-lookup"><span data-stu-id="90666-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="90666-122">Нет</span><span class="sxs-lookup"><span data-stu-id="90666-122">None</span></span>|<span data-ttu-id="90666-123">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="90666-123">Security is disabled.</span></span>|  
|<span data-ttu-id="90666-124">Transport</span><span class="sxs-lookup"><span data-stu-id="90666-124">Transport</span></span>|<span data-ttu-id="90666-125">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="90666-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="90666-126">Необходимо настроить службу с использованием сертификата SSL.</span><span class="sxs-lookup"><span data-stu-id="90666-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="90666-127">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="90666-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="90666-128">Проверка подлинности клиента осуществляется с помощью `ClientCredentialType` атрибут [ \<транспорта >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="90666-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="90666-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="90666-129">TransportCredentialOnly</span></span>|<span data-ttu-id="90666-130">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="90666-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="90666-131">Он обеспечивает проверку подлинности клиента на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="90666-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="90666-132">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="90666-132">This mode should be used with caution.</span></span> <span data-ttu-id="90666-133">Он должен использоваться в тех средах, где безопасность транспорта обеспечивается другими средствами (например, IPSec), а инфраструктура [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] обеспечивает только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="90666-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90666-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="90666-134">Child Elements</span></span>  
  
|<span data-ttu-id="90666-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="90666-135">Element</span></span>|<span data-ttu-id="90666-136">Описание</span><span class="sxs-lookup"><span data-stu-id="90666-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90666-137">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="90666-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="90666-138">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="90666-138">Defines the transport security settings.</span></span> <span data-ttu-id="90666-139">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="90666-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="90666-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="90666-140">Parent Elements</span></span>  
  
|<span data-ttu-id="90666-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="90666-141">Element</span></span>|<span data-ttu-id="90666-142">Описание</span><span class="sxs-lookup"><span data-stu-id="90666-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90666-143">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="90666-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="90666-144">Элемент привязки, который используется при настройке конечных точек для веб-служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], которые отвечают на запросы HTTP вместо сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="90666-144">A binding element that is used to configure endpoints for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90666-145">См. также</span><span class="sxs-lookup"><span data-stu-id="90666-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="90666-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="90666-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="90666-147">При выборе типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="90666-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="90666-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="90666-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="90666-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="90666-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="90666-150">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="90666-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="90666-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="90666-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="90666-152">Модель программирования WCF Web HTTP</span><span class="sxs-lookup"><span data-stu-id="90666-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
