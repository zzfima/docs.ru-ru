---
title: <security> из <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738607"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="949b1-102">\<> безопасности \<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="949b1-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="949b1-103">Определяет возможности безопасности [\<wsDualHttpBinding >](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="949b1-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
<span data-ttu-id="949b1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="949b1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="949b1-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="949b1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="949b1-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="949b1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="949b1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsDualHttpBinding >** ](wsdualhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="949b1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)</span></span>\
<span data-ttu-id="949b1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="949b1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="949b1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<security >**</span><span class="sxs-lookup"><span data-stu-id="949b1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="949b1-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="949b1-110">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="949b1-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="949b1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="949b1-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="949b1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="949b1-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="949b1-113">Attributes</span></span>  
  
|<span data-ttu-id="949b1-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="949b1-114">Attribute</span></span>|<span data-ttu-id="949b1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="949b1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="949b1-116">режим</span><span class="sxs-lookup"><span data-stu-id="949b1-116">mode</span></span>|<span data-ttu-id="949b1-117">Используемых.</span><span class="sxs-lookup"><span data-stu-id="949b1-117">-   Optional.</span></span> <span data-ttu-id="949b1-118">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="949b1-118">Specifies the type of security that is applied.</span></span> <span data-ttu-id="949b1-119">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="949b1-119">The default value is `Message`.</span></span> <span data-ttu-id="949b1-120">Это атрибут типа <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="949b1-120">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="949b1-121">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="949b1-121">Mode Attribute</span></span>  
  
|<span data-ttu-id="949b1-122">значения</span><span class="sxs-lookup"><span data-stu-id="949b1-122">Value</span></span>|<span data-ttu-id="949b1-123">Описание</span><span class="sxs-lookup"><span data-stu-id="949b1-123">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="949b1-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="949b1-124">None</span></span>|<span data-ttu-id="949b1-125">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="949b1-125">Security is disabled.</span></span>|  
|<span data-ttu-id="949b1-126">Сообщение</span><span class="sxs-lookup"><span data-stu-id="949b1-126">Message</span></span>|<span data-ttu-id="949b1-127">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="949b1-127">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="949b1-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="949b1-128">Child Elements</span></span>  
  
|<span data-ttu-id="949b1-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="949b1-129">Element</span></span>|<span data-ttu-id="949b1-130">Описание</span><span class="sxs-lookup"><span data-stu-id="949b1-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="949b1-131">сообщение \<</span><span class="sxs-lookup"><span data-stu-id="949b1-131">\<message></span></span>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="949b1-132">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="949b1-132">Defines the settings for the message-level security.</span></span> <span data-ttu-id="949b1-133">Это элемент типа <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="949b1-133">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="949b1-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="949b1-134">Parent Elements</span></span>  
  
|<span data-ttu-id="949b1-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="949b1-135">Element</span></span>|<span data-ttu-id="949b1-136">Описание</span><span class="sxs-lookup"><span data-stu-id="949b1-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="949b1-137">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="949b1-137">\<binding></span></span>](bindings.md)|<span data-ttu-id="949b1-138">Определяет все возможности привязки [\<wsDualHttpBinding >](wsdualhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="949b1-138">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="949b1-139">Заметки</span><span class="sxs-lookup"><span data-stu-id="949b1-139">Remarks</span></span>  
 <span data-ttu-id="949b1-140">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="949b1-140">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="949b1-141">Клиенту следует использовать механизм безопасности, чтобы гарантировать, что подключение выполняется только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="949b1-141">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="949b1-142">См. также</span><span class="sxs-lookup"><span data-stu-id="949b1-142">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="949b1-143">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="949b1-143">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="949b1-144">Привязки</span><span class="sxs-lookup"><span data-stu-id="949b1-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="949b1-145">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="949b1-145">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="949b1-146">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="949b1-146">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="949b1-147">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="949b1-147">\<binding></span></span>](bindings.md)
