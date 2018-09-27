---
title: '&lt;security&gt; для &lt;wsDualHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
ms.openlocfilehash: c817ea6faf5229a8d372a06b866c75e0f40af3b3
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399863"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="1deac-102">&lt;security&gt; для &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1deac-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="1deac-103">Определяет возможности безопасности [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1deac-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="1deac-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="1deac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1deac-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="1deac-105">\<bindings></span></span>  
<span data-ttu-id="1deac-106">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="1deac-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="1deac-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1deac-107">\<binding></span></span>  
<span data-ttu-id="1deac-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="1deac-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1deac-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1deac-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1deac-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1deac-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1deac-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1deac-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1deac-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1deac-112">Attributes</span></span>  
  
|<span data-ttu-id="1deac-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1deac-113">Attribute</span></span>|<span data-ttu-id="1deac-114">Описание</span><span class="sxs-lookup"><span data-stu-id="1deac-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1deac-115">режим</span><span class="sxs-lookup"><span data-stu-id="1deac-115">mode</span></span>|<span data-ttu-id="1deac-116">-Необязательно.</span><span class="sxs-lookup"><span data-stu-id="1deac-116">-   Optional.</span></span> <span data-ttu-id="1deac-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="1deac-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="1deac-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="1deac-118">The default value is `Message`.</span></span> <span data-ttu-id="1deac-119">Это атрибут типа <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="1deac-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="1deac-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="1deac-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="1deac-121">Значение</span><span class="sxs-lookup"><span data-stu-id="1deac-121">Value</span></span>|<span data-ttu-id="1deac-122">Описание</span><span class="sxs-lookup"><span data-stu-id="1deac-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1deac-123">Нет</span><span class="sxs-lookup"><span data-stu-id="1deac-123">None</span></span>|<span data-ttu-id="1deac-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="1deac-124">Security is disabled.</span></span>|  
|<span data-ttu-id="1deac-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="1deac-125">Message</span></span>|<span data-ttu-id="1deac-126">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="1deac-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1deac-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1deac-127">Child Elements</span></span>  
  
|<span data-ttu-id="1deac-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="1deac-128">Element</span></span>|<span data-ttu-id="1deac-129">Описание</span><span class="sxs-lookup"><span data-stu-id="1deac-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1deac-130">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="1deac-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="1deac-131">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="1deac-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="1deac-132">Это элемент типа <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="1deac-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1deac-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1deac-133">Parent Elements</span></span>  
  
|<span data-ttu-id="1deac-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="1deac-134">Element</span></span>|<span data-ttu-id="1deac-135">Описание</span><span class="sxs-lookup"><span data-stu-id="1deac-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1deac-136">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1deac-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="1deac-137">Определяет все возможности привязки [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="1deac-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1deac-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="1deac-138">Remarks</span></span>  
 <span data-ttu-id="1deac-139">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="1deac-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="1deac-140">Клиенту следует использовать механизм безопасности, чтобы гарантировать, что подключение выполняется только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="1deac-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1deac-141">См. также</span><span class="sxs-lookup"><span data-stu-id="1deac-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="1deac-142">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="1deac-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="1deac-143">Привязки</span><span class="sxs-lookup"><span data-stu-id="1deac-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="1deac-144">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="1deac-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="1deac-145">Использование привязок для настройки службы Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="1deac-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="1deac-146">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="1deac-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
