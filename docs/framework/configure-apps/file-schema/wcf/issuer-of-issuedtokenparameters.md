---
title: '&lt;issuer&gt; для &lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 459f2f43d3ef9426fbce7e0a0dd067250eb2cc4b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748576"
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="10d08-102">&lt;issuer&gt; для &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="10d08-102">&lt;issuer&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="10d08-103">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="10d08-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="10d08-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="10d08-104">\<system.serviceModel></span></span>  
<span data-ttu-id="10d08-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="10d08-105">\<bindings></span></span>  
<span data-ttu-id="10d08-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="10d08-106">\<customBinding></span></span>  
<span data-ttu-id="10d08-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="10d08-107">\<binding></span></span>  
<span data-ttu-id="10d08-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="10d08-108">\<security></span></span>  
<span data-ttu-id="10d08-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="10d08-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="10d08-110">\<издатель ></span><span class="sxs-lookup"><span data-stu-id="10d08-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10d08-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="10d08-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10d08-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="10d08-112">Attributes and Elements</span></span>  
 <span data-ttu-id="10d08-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="10d08-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10d08-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="10d08-114">Attributes</span></span>  
  
|<span data-ttu-id="10d08-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="10d08-115">Attribute</span></span>|<span data-ttu-id="10d08-116">Описание</span><span class="sxs-lookup"><span data-stu-id="10d08-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10d08-117">address</span><span class="sxs-lookup"><span data-stu-id="10d08-117">address</span></span>|<span data-ttu-id="10d08-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="10d08-118">Required string.</span></span> <span data-ttu-id="10d08-119">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="10d08-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10d08-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="10d08-120">Child Elements</span></span>  
  
|<span data-ttu-id="10d08-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="10d08-121">Element</span></span>|<span data-ttu-id="10d08-122">Описание</span><span class="sxs-lookup"><span data-stu-id="10d08-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10d08-123">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="10d08-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="10d08-124">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="10d08-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="10d08-125">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="10d08-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="10d08-126">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="10d08-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="10d08-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="10d08-127">Parent Elements</span></span>  
  
|<span data-ttu-id="10d08-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="10d08-128">Element</span></span>|<span data-ttu-id="10d08-129">Описание</span><span class="sxs-lookup"><span data-stu-id="10d08-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10d08-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="10d08-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="10d08-131">Определяет текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="10d08-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10d08-132">См. также</span><span class="sxs-lookup"><span data-stu-id="10d08-132">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="10d08-133">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="10d08-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="10d08-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="10d08-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="10d08-135">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="10d08-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="10d08-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="10d08-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="10d08-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="10d08-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="10d08-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="10d08-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="10d08-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="10d08-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="10d08-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="10d08-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="10d08-141">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="10d08-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="10d08-142">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="10d08-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
