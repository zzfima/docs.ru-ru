---
title: "&lt;security&gt; для &lt;wsDualHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 72d1c451efe267d098ef4d529194905ee14d6ae3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="f40ae-102">&lt;security&gt; для &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="f40ae-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="f40ae-103">Определяет возможности безопасности [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f40ae-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="f40ae-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="f40ae-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="f40ae-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="f40ae-105">\<bindings></span></span>  
<span data-ttu-id="f40ae-106">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="f40ae-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="f40ae-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f40ae-107">\<binding></span></span>  
<span data-ttu-id="f40ae-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="f40ae-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f40ae-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f40ae-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f40ae-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f40ae-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f40ae-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f40ae-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f40ae-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f40ae-112">Attributes</span></span>  
  
|<span data-ttu-id="f40ae-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f40ae-113">Attribute</span></span>|<span data-ttu-id="f40ae-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f40ae-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f40ae-115">режим</span><span class="sxs-lookup"><span data-stu-id="f40ae-115">mode</span></span>|<span data-ttu-id="f40ae-116">— Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="f40ae-116">-   Optional.</span></span> <span data-ttu-id="f40ae-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="f40ae-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="f40ae-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="f40ae-118">The default value is `Message`.</span></span> <span data-ttu-id="f40ae-119">Это атрибут типа <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="f40ae-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="f40ae-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="f40ae-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="f40ae-121">Значение</span><span class="sxs-lookup"><span data-stu-id="f40ae-121">Value</span></span>|<span data-ttu-id="f40ae-122">Описание</span><span class="sxs-lookup"><span data-stu-id="f40ae-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f40ae-123">Нет</span><span class="sxs-lookup"><span data-stu-id="f40ae-123">None</span></span>|<span data-ttu-id="f40ae-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="f40ae-124">Security is disabled.</span></span>|  
|<span data-ttu-id="f40ae-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="f40ae-125">Message</span></span>|<span data-ttu-id="f40ae-126">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="f40ae-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f40ae-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f40ae-127">Child Elements</span></span>  
  
|<span data-ttu-id="f40ae-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="f40ae-128">Element</span></span>|<span data-ttu-id="f40ae-129">Описание</span><span class="sxs-lookup"><span data-stu-id="f40ae-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f40ae-130">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="f40ae-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="f40ae-131">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="f40ae-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="f40ae-132">Это элемент типа <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="f40ae-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f40ae-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f40ae-133">Parent Elements</span></span>  
  
|<span data-ttu-id="f40ae-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="f40ae-134">Element</span></span>|<span data-ttu-id="f40ae-135">Описание</span><span class="sxs-lookup"><span data-stu-id="f40ae-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f40ae-136">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f40ae-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="f40ae-137">Определяет все возможности [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="f40ae-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f40ae-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="f40ae-138">Remarks</span></span>  
 <span data-ttu-id="f40ae-139">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="f40ae-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="f40ae-140">Клиенту следует использовать механизм безопасности, чтобы гарантировать, что подключение выполняется только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="f40ae-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f40ae-141">См. также</span><span class="sxs-lookup"><span data-stu-id="f40ae-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="f40ae-142">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f40ae-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="f40ae-143">Привязки</span><span class="sxs-lookup"><span data-stu-id="f40ae-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="f40ae-144">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="f40ae-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="f40ae-145">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="f40ae-145">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="f40ae-146">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f40ae-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
