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
ms.workload: dotnet
ms.openlocfilehash: 3afd67e7f2d42cec458db7919529e09e4607f1ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="d89f2-102">&lt;security&gt; для &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="d89f2-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="d89f2-103">Задает требования безопасности для конечной точки, настроенной с [ \<wsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d89f2-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="d89f2-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="d89f2-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d89f2-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d89f2-105">\<bindings></span></span>  
<span data-ttu-id="d89f2-106">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d89f2-106">\<webHttpBinding></span></span>  
<span data-ttu-id="d89f2-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d89f2-107">\<binding></span></span>  
<span data-ttu-id="d89f2-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="d89f2-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d89f2-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d89f2-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d89f2-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d89f2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d89f2-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d89f2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d89f2-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d89f2-112">Attributes</span></span>  
  
|<span data-ttu-id="d89f2-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d89f2-113">Attribute</span></span>|<span data-ttu-id="d89f2-114">Описание</span><span class="sxs-lookup"><span data-stu-id="d89f2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d89f2-115">режим</span><span class="sxs-lookup"><span data-stu-id="d89f2-115">mode</span></span>|<span data-ttu-id="d89f2-116">Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется.</span><span class="sxs-lookup"><span data-stu-id="d89f2-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="d89f2-117">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="d89f2-117">The default is `None`.</span></span> <span data-ttu-id="d89f2-118">Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="d89f2-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="d89f2-119">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="d89f2-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="d89f2-120">Значение</span><span class="sxs-lookup"><span data-stu-id="d89f2-120">Value</span></span>|<span data-ttu-id="d89f2-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d89f2-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d89f2-122">Нет</span><span class="sxs-lookup"><span data-stu-id="d89f2-122">None</span></span>|<span data-ttu-id="d89f2-123">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="d89f2-123">Security is disabled.</span></span>|  
|<span data-ttu-id="d89f2-124">Transport</span><span class="sxs-lookup"><span data-stu-id="d89f2-124">Transport</span></span>|<span data-ttu-id="d89f2-125">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d89f2-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="d89f2-126">Необходимо настроить службу с использованием сертификата SSL.</span><span class="sxs-lookup"><span data-stu-id="d89f2-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="d89f2-127">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="d89f2-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="d89f2-128">Проверка подлинности клиента осуществляется с помощью `ClientCredentialType` атрибут [ \<транспорта >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="d89f2-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="d89f2-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="d89f2-129">TransportCredentialOnly</span></span>|<span data-ttu-id="d89f2-130">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="d89f2-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="d89f2-131">Он обеспечивает проверку подлинности клиента на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="d89f2-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="d89f2-132">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="d89f2-132">This mode should be used with caution.</span></span> <span data-ttu-id="d89f2-133">Он должен использоваться в тех средах, где безопасность транспорта обеспечивается другими средствами (например, IPSec), а инфраструктура [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] обеспечивает только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="d89f2-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d89f2-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d89f2-134">Child Elements</span></span>  
  
|<span data-ttu-id="d89f2-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="d89f2-135">Element</span></span>|<span data-ttu-id="d89f2-136">Описание:</span><span class="sxs-lookup"><span data-stu-id="d89f2-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d89f2-137">\<Транспорт ></span><span class="sxs-lookup"><span data-stu-id="d89f2-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="d89f2-138">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="d89f2-138">Defines the transport security settings.</span></span> <span data-ttu-id="d89f2-139">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="d89f2-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d89f2-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d89f2-140">Parent Elements</span></span>  
  
|<span data-ttu-id="d89f2-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="d89f2-141">Element</span></span>|<span data-ttu-id="d89f2-142">Описание:</span><span class="sxs-lookup"><span data-stu-id="d89f2-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d89f2-143">\<webHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="d89f2-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="d89f2-144">Элемент привязки, который используется при настройке конечных точек для веб-служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], которые отвечают на запросы HTTP вместо сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="d89f2-144">A binding element that is used to configure endpoints for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d89f2-145">См. также</span><span class="sxs-lookup"><span data-stu-id="d89f2-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="d89f2-146">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="d89f2-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="d89f2-147">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="d89f2-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="d89f2-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="d89f2-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d89f2-149">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="d89f2-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="d89f2-150">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="d89f2-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="d89f2-151">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d89f2-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="d89f2-152">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="d89f2-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
