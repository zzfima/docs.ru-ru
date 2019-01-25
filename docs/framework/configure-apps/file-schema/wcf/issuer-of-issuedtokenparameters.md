---
title: '&lt;issuer&gt; для &lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 58fdd93eb4f69e48783873df26bf1c35a2a849e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539159"
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="f9a36-102">&lt;issuer&gt; для &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="f9a36-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="f9a36-103">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9a36-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="f9a36-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="f9a36-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f9a36-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="f9a36-105">\<bindings></span></span>  
<span data-ttu-id="f9a36-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f9a36-106">\<customBinding></span></span>  
<span data-ttu-id="f9a36-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f9a36-107">\<binding></span></span>  
<span data-ttu-id="f9a36-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="f9a36-108">\<security></span></span>  
<span data-ttu-id="f9a36-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="f9a36-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="f9a36-110">\<issuer></span><span class="sxs-lookup"><span data-stu-id="f9a36-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9a36-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f9a36-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f9a36-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f9a36-112">Attributes and Elements</span></span>  
 <span data-ttu-id="f9a36-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f9a36-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f9a36-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f9a36-114">Attributes</span></span>  
  
|<span data-ttu-id="f9a36-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f9a36-115">Attribute</span></span>|<span data-ttu-id="f9a36-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f9a36-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f9a36-117">address</span><span class="sxs-lookup"><span data-stu-id="f9a36-117">address</span></span>|<span data-ttu-id="f9a36-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="f9a36-118">Required string.</span></span> <span data-ttu-id="f9a36-119">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="f9a36-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f9a36-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f9a36-120">Child Elements</span></span>  
  
|<span data-ttu-id="f9a36-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9a36-121">Element</span></span>|<span data-ttu-id="f9a36-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="f9a36-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9a36-123">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="f9a36-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="f9a36-124">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="f9a36-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="f9a36-125">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="f9a36-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f9a36-126">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="f9a36-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f9a36-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f9a36-127">Parent Elements</span></span>  
  
|<span data-ttu-id="f9a36-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="f9a36-128">Element</span></span>|<span data-ttu-id="f9a36-129">Описание</span><span class="sxs-lookup"><span data-stu-id="f9a36-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f9a36-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="f9a36-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="f9a36-131">Определяет текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="f9a36-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9a36-132">См. также</span><span class="sxs-lookup"><span data-stu-id="f9a36-132">See also</span></span>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f9a36-133">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="f9a36-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f9a36-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="f9a36-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f9a36-135">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="f9a36-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="f9a36-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="f9a36-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f9a36-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="f9a36-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="f9a36-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="f9a36-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f9a36-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="f9a36-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="f9a36-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="f9a36-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="f9a36-141">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="f9a36-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="f9a36-142">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="f9a36-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
