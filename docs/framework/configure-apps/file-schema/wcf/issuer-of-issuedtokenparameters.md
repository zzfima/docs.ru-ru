---
title: <issuer> из <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: bdd5ad45984fae7b39defe82c4af75845dfda1b6
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397945"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="80ce7-102">\<> издателя для \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="80ce7-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="80ce7-103">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="80ce7-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
<span data-ttu-id="80ce7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="80ce7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="80ce7-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="80ce7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="80ce7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="80ce7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="80ce7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="80ce7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="80ce7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="80ce7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="80ce7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="80ce7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="80ce7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="80ce7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="80ce7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> издателя**</span><span class="sxs-lookup"><span data-stu-id="80ce7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuer>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80ce7-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80ce7-112">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80ce7-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="80ce7-113">Attributes and Elements</span></span>  
 <span data-ttu-id="80ce7-114">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="80ce7-114">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80ce7-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="80ce7-115">Attributes</span></span>  
  
|<span data-ttu-id="80ce7-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="80ce7-116">Attribute</span></span>|<span data-ttu-id="80ce7-117">Описание</span><span class="sxs-lookup"><span data-stu-id="80ce7-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="80ce7-118">адрес</span><span class="sxs-lookup"><span data-stu-id="80ce7-118">address</span></span>|<span data-ttu-id="80ce7-119">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="80ce7-119">Required string.</span></span> <span data-ttu-id="80ce7-120">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="80ce7-120">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80ce7-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="80ce7-121">Child Elements</span></span>  
  
|<span data-ttu-id="80ce7-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="80ce7-122">Element</span></span>|<span data-ttu-id="80ce7-123">Описание</span><span class="sxs-lookup"><span data-stu-id="80ce7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80ce7-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="80ce7-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="80ce7-125">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="80ce7-125">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="80ce7-126">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="80ce7-126">\<identity></span></span>](identity.md)|<span data-ttu-id="80ce7-127">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="80ce7-127">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="80ce7-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="80ce7-128">Parent Elements</span></span>  
  
|<span data-ttu-id="80ce7-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="80ce7-129">Element</span></span>|<span data-ttu-id="80ce7-130">Описание</span><span class="sxs-lookup"><span data-stu-id="80ce7-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80ce7-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="80ce7-131">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="80ce7-132">Определяет текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="80ce7-132">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="80ce7-133">См. также</span><span class="sxs-lookup"><span data-stu-id="80ce7-133">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="80ce7-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="80ce7-134">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="80ce7-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="80ce7-135">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="80ce7-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="80ce7-136">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="80ce7-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="80ce7-137">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="80ce7-138">Привязки</span><span class="sxs-lookup"><span data-stu-id="80ce7-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="80ce7-139">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="80ce7-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="80ce7-140">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="80ce7-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="80ce7-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="80ce7-141">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="80ce7-142">Практическое руководство. Создание пользовательской привязки с помощью SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="80ce7-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="80ce7-143">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="80ce7-143">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
