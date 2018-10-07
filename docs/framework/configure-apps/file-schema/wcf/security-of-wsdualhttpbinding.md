---
title: '&lt;security&gt; для &lt;wsDualHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
author: BrucePerlerMS
ms.openlocfilehash: 761eb9d111630d64d0fe4450c7a8950a8181366d
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838292"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="a63bf-102">&lt;security&gt; для &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a63bf-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="a63bf-103">Определяет возможности безопасности [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a63bf-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="a63bf-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a63bf-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a63bf-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a63bf-105">\<bindings></span></span>  
<span data-ttu-id="a63bf-106">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a63bf-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="a63bf-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a63bf-107">\<binding></span></span>  
<span data-ttu-id="a63bf-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="a63bf-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a63bf-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a63bf-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">  
   <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"  
      negotiateServiceCredential="Boolean"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a63bf-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a63bf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a63bf-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a63bf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a63bf-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a63bf-112">Attributes</span></span>  
  
|<span data-ttu-id="a63bf-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a63bf-113">Attribute</span></span>|<span data-ttu-id="a63bf-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a63bf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a63bf-115">режим</span><span class="sxs-lookup"><span data-stu-id="a63bf-115">mode</span></span>|<span data-ttu-id="a63bf-116">-Необязательно.</span><span class="sxs-lookup"><span data-stu-id="a63bf-116">-   Optional.</span></span> <span data-ttu-id="a63bf-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="a63bf-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="a63bf-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="a63bf-118">The default value is `Message`.</span></span> <span data-ttu-id="a63bf-119">Это атрибут типа <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="a63bf-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="a63bf-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="a63bf-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="a63bf-121">Значение</span><span class="sxs-lookup"><span data-stu-id="a63bf-121">Value</span></span>|<span data-ttu-id="a63bf-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a63bf-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a63bf-123">Нет</span><span class="sxs-lookup"><span data-stu-id="a63bf-123">None</span></span>|<span data-ttu-id="a63bf-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="a63bf-124">Security is disabled.</span></span>|  
|<span data-ttu-id="a63bf-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="a63bf-125">Message</span></span>|<span data-ttu-id="a63bf-126">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="a63bf-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a63bf-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a63bf-127">Child Elements</span></span>  
  
|<span data-ttu-id="a63bf-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="a63bf-128">Element</span></span>|<span data-ttu-id="a63bf-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="a63bf-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a63bf-130">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="a63bf-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="a63bf-131">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="a63bf-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="a63bf-132">Это элемент типа <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="a63bf-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a63bf-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a63bf-133">Parent Elements</span></span>  
  
|<span data-ttu-id="a63bf-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="a63bf-134">Element</span></span>|<span data-ttu-id="a63bf-135">Описание:</span><span class="sxs-lookup"><span data-stu-id="a63bf-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a63bf-136">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a63bf-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a63bf-137">Определяет все возможности привязки [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a63bf-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a63bf-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="a63bf-138">Remarks</span></span>  
 <span data-ttu-id="a63bf-139">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="a63bf-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="a63bf-140">Клиенту следует использовать механизм безопасности, чтобы гарантировать, что подключение выполняется только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="a63bf-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a63bf-141">См. также</span><span class="sxs-lookup"><span data-stu-id="a63bf-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="a63bf-142">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a63bf-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a63bf-143">Привязки</span><span class="sxs-lookup"><span data-stu-id="a63bf-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a63bf-144">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a63bf-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a63bf-145">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a63bf-145">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="a63bf-146">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a63bf-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
