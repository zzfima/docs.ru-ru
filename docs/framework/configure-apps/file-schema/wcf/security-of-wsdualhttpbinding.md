---
title: <security> из <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: bed7f4ce325e0d5e387e310ca15a3b72ac93f18e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936543"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="b84ed-102">\<> безопасности > \<WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="b84ed-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="b84ed-103">Определяет возможности [ \<безопасности > WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b84ed-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
 <span data-ttu-id="b84ed-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b84ed-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b84ed-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="b84ed-105">\<bindings></span></span>  
<span data-ttu-id="b84ed-106">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="b84ed-106">\<wsDualHttpBinding></span></span>  
<span data-ttu-id="b84ed-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b84ed-107">\<binding></span></span>  
<span data-ttu-id="b84ed-108">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="b84ed-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b84ed-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b84ed-109">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b84ed-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b84ed-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b84ed-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b84ed-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b84ed-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b84ed-112">Attributes</span></span>  
  
|<span data-ttu-id="b84ed-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b84ed-113">Attribute</span></span>|<span data-ttu-id="b84ed-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b84ed-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b84ed-115">режим</span><span class="sxs-lookup"><span data-stu-id="b84ed-115">mode</span></span>|<span data-ttu-id="b84ed-116">Используемых.</span><span class="sxs-lookup"><span data-stu-id="b84ed-116">-   Optional.</span></span> <span data-ttu-id="b84ed-117">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="b84ed-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="b84ed-118">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="b84ed-118">The default value is `Message`.</span></span> <span data-ttu-id="b84ed-119">Это атрибут типа <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="b84ed-119">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="b84ed-120">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="b84ed-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="b84ed-121">Значение</span><span class="sxs-lookup"><span data-stu-id="b84ed-121">Value</span></span>|<span data-ttu-id="b84ed-122">Описание</span><span class="sxs-lookup"><span data-stu-id="b84ed-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b84ed-123">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="b84ed-123">None</span></span>|<span data-ttu-id="b84ed-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="b84ed-124">Security is disabled.</span></span>|  
|<span data-ttu-id="b84ed-125">Сообщение</span><span class="sxs-lookup"><span data-stu-id="b84ed-125">Message</span></span>|<span data-ttu-id="b84ed-126">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="b84ed-126">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b84ed-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b84ed-127">Child Elements</span></span>  
  
|<span data-ttu-id="b84ed-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="b84ed-128">Element</span></span>|<span data-ttu-id="b84ed-129">Описание</span><span class="sxs-lookup"><span data-stu-id="b84ed-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b84ed-130">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="b84ed-130">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="b84ed-131">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="b84ed-131">Defines the settings for the message-level security.</span></span> <span data-ttu-id="b84ed-132">Это элемент типа <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="b84ed-132">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b84ed-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b84ed-133">Parent Elements</span></span>  
  
|<span data-ttu-id="b84ed-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="b84ed-134">Element</span></span>|<span data-ttu-id="b84ed-135">Описание</span><span class="sxs-lookup"><span data-stu-id="b84ed-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b84ed-136">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b84ed-136">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="b84ed-137">Определяет все возможности [ \<привязки > WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="b84ed-137">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b84ed-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="b84ed-138">Remarks</span></span>  
 <span data-ttu-id="b84ed-139">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="b84ed-139">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="b84ed-140">Клиенту следует использовать механизм безопасности, чтобы гарантировать, что подключение выполняется только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="b84ed-140">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b84ed-141">См. также</span><span class="sxs-lookup"><span data-stu-id="b84ed-141">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="b84ed-142">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b84ed-142">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="b84ed-143">Привязки</span><span class="sxs-lookup"><span data-stu-id="b84ed-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="b84ed-144">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="b84ed-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="b84ed-145">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="b84ed-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b84ed-146">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b84ed-146">\<binding></span></span>](../../../misc/binding.md)
