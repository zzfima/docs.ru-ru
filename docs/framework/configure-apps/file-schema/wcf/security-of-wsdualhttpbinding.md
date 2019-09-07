---
title: <security> из <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: b6a1c952b1ae65c8fb6f17237b5c15f3a8d4844a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399750"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="38273-102">\<> безопасности > \<WSDualHttpBinding</span><span class="sxs-lookup"><span data-stu-id="38273-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="38273-103">Определяет возможности [ \<безопасности > WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="38273-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
<span data-ttu-id="38273-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="38273-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="38273-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="38273-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="38273-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="38273-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="38273-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsDualHttpBinding >** ](wsdualhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="38273-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)</span></span>\
<span data-ttu-id="38273-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="38273-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="38273-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> безопасности**</span><span class="sxs-lookup"><span data-stu-id="38273-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38273-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="38273-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38273-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="38273-111">Attributes and Elements</span></span>  
 <span data-ttu-id="38273-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="38273-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38273-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="38273-113">Attributes</span></span>  
  
|<span data-ttu-id="38273-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="38273-114">Attribute</span></span>|<span data-ttu-id="38273-115">Описание</span><span class="sxs-lookup"><span data-stu-id="38273-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38273-116">режим</span><span class="sxs-lookup"><span data-stu-id="38273-116">mode</span></span>|<span data-ttu-id="38273-117">Используемых.</span><span class="sxs-lookup"><span data-stu-id="38273-117">-   Optional.</span></span> <span data-ttu-id="38273-118">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="38273-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="38273-119">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="38273-119">The default value is `Message`.</span></span> <span data-ttu-id="38273-120">Это атрибут типа <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="38273-120">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="38273-121">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="38273-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="38273-122">Значение</span><span class="sxs-lookup"><span data-stu-id="38273-122">Value</span></span>|<span data-ttu-id="38273-123">Описание</span><span class="sxs-lookup"><span data-stu-id="38273-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="38273-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="38273-124">None</span></span>|<span data-ttu-id="38273-125">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="38273-125">Security is disabled.</span></span>|  
|<span data-ttu-id="38273-126">Сообщение</span><span class="sxs-lookup"><span data-stu-id="38273-126">Message</span></span>|<span data-ttu-id="38273-127">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="38273-127">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38273-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="38273-128">Child Elements</span></span>  
  
|<span data-ttu-id="38273-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="38273-129">Element</span></span>|<span data-ttu-id="38273-130">Описание</span><span class="sxs-lookup"><span data-stu-id="38273-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38273-131">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="38273-131">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="38273-132">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="38273-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="38273-133">Это элемент типа <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="38273-133">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="38273-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="38273-134">Parent Elements</span></span>  
  
|<span data-ttu-id="38273-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="38273-135">Element</span></span>|<span data-ttu-id="38273-136">Описание</span><span class="sxs-lookup"><span data-stu-id="38273-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="38273-137">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="38273-137">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="38273-138">Определяет все возможности [ \<привязки > WSDualHttpBinding](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="38273-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38273-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="38273-139">Remarks</span></span>  
 <span data-ttu-id="38273-140">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="38273-140">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="38273-141">Клиенту следует использовать механизм безопасности, чтобы гарантировать, что подключение выполняется только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="38273-141">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38273-142">См. также</span><span class="sxs-lookup"><span data-stu-id="38273-142">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="38273-143">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="38273-143">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="38273-144">Привязки</span><span class="sxs-lookup"><span data-stu-id="38273-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="38273-145">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="38273-145">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="38273-146">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="38273-146">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="38273-147">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="38273-147">\<binding></span></span>](../../../misc/binding.md)
