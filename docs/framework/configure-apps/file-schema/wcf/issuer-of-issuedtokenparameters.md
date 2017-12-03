---
title: "&lt;issuer&gt; для &lt;issuedTokenParameters&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 82e73a571ce7179518d380c0c63c9161b2ad5c55
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="87815-102">&lt;issuer&gt; для &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="87815-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="87815-103">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="87815-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="87815-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="87815-104">\<system.serviceModel></span></span>  
<span data-ttu-id="87815-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="87815-105">\<bindings></span></span>  
<span data-ttu-id="87815-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="87815-106">\<customBinding></span></span>  
<span data-ttu-id="87815-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="87815-107">\<binding></span></span>  
<span data-ttu-id="87815-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="87815-108">\<security></span></span>  
<span data-ttu-id="87815-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="87815-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="87815-110">\<издатель ></span><span class="sxs-lookup"><span data-stu-id="87815-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87815-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="87815-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87815-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="87815-112">Attributes and Elements</span></span>  
 <span data-ttu-id="87815-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="87815-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87815-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="87815-114">Attributes</span></span>  
  
|<span data-ttu-id="87815-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="87815-115">Attribute</span></span>|<span data-ttu-id="87815-116">Описание</span><span class="sxs-lookup"><span data-stu-id="87815-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="87815-117">address</span><span class="sxs-lookup"><span data-stu-id="87815-117">address</span></span>|<span data-ttu-id="87815-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="87815-118">Required string.</span></span> <span data-ttu-id="87815-119">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="87815-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87815-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="87815-120">Child Elements</span></span>  
  
|<span data-ttu-id="87815-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="87815-121">Element</span></span>|<span data-ttu-id="87815-122">Описание</span><span class="sxs-lookup"><span data-stu-id="87815-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87815-123">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="87815-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="87815-124">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="87815-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="87815-125">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="87815-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="87815-126">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="87815-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87815-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="87815-127">Parent Elements</span></span>  
  
|<span data-ttu-id="87815-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="87815-128">Element</span></span>|<span data-ttu-id="87815-129">Описание</span><span class="sxs-lookup"><span data-stu-id="87815-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="87815-130">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="87815-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="87815-131">Определяет текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="87815-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="87815-132">См. также</span><span class="sxs-lookup"><span data-stu-id="87815-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="87815-133">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="87815-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="87815-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="87815-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="87815-135">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="87815-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="87815-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="87815-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="87815-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="87815-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="87815-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="87815-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="87815-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="87815-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="87815-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="87815-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="87815-141">Как: Создание пользовательской привязки, с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="87815-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="87815-142">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="87815-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
