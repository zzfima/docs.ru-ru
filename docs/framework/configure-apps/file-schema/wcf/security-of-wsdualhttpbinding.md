---
title: '&lt;security&gt; для &lt;wsDualHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 5759e8a3618cd959605b139577bae24c35490ea8
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150218"
---
# <a name="ltsecuritygt-of-ltwsdualhttpbindinggt"></a><span data-ttu-id="ef828-102">&lt;security&gt; для &lt;wsDualHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="ef828-102">&lt;security&gt; of &lt;wsDualHttpBinding&gt;</span></span>
<span data-ttu-id="ef828-103">Определяет возможности безопасности [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ef828-103">Defines the security capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="ef828-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="ef828-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ef828-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ef828-105">\<bindings></span></span>  
<span data-ttu-id="ef828-106">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="ef828-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="ef828-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ef828-107">\<binding></span></span>  
<span data-ttu-id="ef828-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="ef828-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef828-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ef828-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ef828-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ef828-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ef828-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ef828-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ef828-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ef828-112">Attributes</span></span>  
  
|<span data-ttu-id="ef828-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ef828-113">Attribute</span></span>|<span data-ttu-id="ef828-114">Описание</span><span class="sxs-lookup"><span data-stu-id="ef828-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ef828-115">режим</span><span class="sxs-lookup"><span data-stu-id="ef828-115">mode</span></span>|<span data-ttu-id="ef828-116">-Необязательно.</span><span class="sxs-lookup"><span data-stu-id="ef828-116">-   Optional.</span></span> <span data-ttu-id="ef828-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="ef828-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="ef828-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="ef828-118">The default value is `Message`.</span></span> <span data-ttu-id="ef828-119">Это атрибут типа <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="ef828-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ef828-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="ef828-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="ef828-121">Значение</span><span class="sxs-lookup"><span data-stu-id="ef828-121">Value</span></span>|<span data-ttu-id="ef828-122">Описание</span><span class="sxs-lookup"><span data-stu-id="ef828-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ef828-123">Нет</span><span class="sxs-lookup"><span data-stu-id="ef828-123">None</span></span>|<span data-ttu-id="ef828-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="ef828-124">Security is disabled.</span></span>|  
|<span data-ttu-id="ef828-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="ef828-125">Message</span></span>|<span data-ttu-id="ef828-126">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="ef828-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ef828-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ef828-127">Child Elements</span></span>  
  
|<span data-ttu-id="ef828-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef828-128">Element</span></span>|<span data-ttu-id="ef828-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="ef828-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef828-130">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="ef828-130">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wsdualhttpbinding.md)|<span data-ttu-id="ef828-131">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="ef828-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="ef828-132">Это элемент типа <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="ef828-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ef828-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ef828-133">Parent Elements</span></span>  
  
|<span data-ttu-id="ef828-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="ef828-134">Element</span></span>|<span data-ttu-id="ef828-135">Описание:</span><span class="sxs-lookup"><span data-stu-id="ef828-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ef828-136">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ef828-136">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ef828-137">Определяет все возможности привязки [ \<wsDualHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="ef828-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef828-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="ef828-138">Remarks</span></span>  
 <span data-ttu-id="ef828-139">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="ef828-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="ef828-140">Клиенту следует использовать механизм безопасности, чтобы гарантировать, что подключение выполняется только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="ef828-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef828-141">См. также</span><span class="sxs-lookup"><span data-stu-id="ef828-141">See Also</span></span>  
 <xref:System.ServiceModel.WSDualHttpSecurity>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="ef828-142">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ef828-142">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="ef828-143">Привязки</span><span class="sxs-lookup"><span data-stu-id="ef828-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ef828-144">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="ef828-144">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="ef828-145">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ef828-145">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="ef828-146">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ef828-146">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
