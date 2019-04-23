---
title: <issuer> из <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 690ab14ea33ba9bef29788b2eb35f86ed945ce2b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59113546"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="08788-102">\<издатель > из \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="08788-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="08788-103">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="08788-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="08788-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="08788-104">\<system.serviceModel></span></span>  
<span data-ttu-id="08788-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="08788-105">\<bindings></span></span>  
<span data-ttu-id="08788-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="08788-106">\<customBinding></span></span>  
<span data-ttu-id="08788-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="08788-107">\<binding></span></span>  
<span data-ttu-id="08788-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="08788-108">\<security></span></span>  
<span data-ttu-id="08788-109">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="08788-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="08788-110">\<issuer></span><span class="sxs-lookup"><span data-stu-id="08788-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08788-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08788-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="08788-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="08788-112">Attributes and Elements</span></span>  
 <span data-ttu-id="08788-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08788-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="08788-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08788-114">Attributes</span></span>  
  
|<span data-ttu-id="08788-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="08788-115">Attribute</span></span>|<span data-ttu-id="08788-116">Описание</span><span class="sxs-lookup"><span data-stu-id="08788-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="08788-117">адрес</span><span class="sxs-lookup"><span data-stu-id="08788-117">address</span></span>|<span data-ttu-id="08788-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="08788-118">Required string.</span></span> <span data-ttu-id="08788-119">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="08788-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="08788-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08788-120">Child Elements</span></span>  
  
|<span data-ttu-id="08788-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="08788-121">Element</span></span>|<span data-ttu-id="08788-122">Описание</span><span class="sxs-lookup"><span data-stu-id="08788-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08788-123">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="08788-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="08788-124">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="08788-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="08788-125">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="08788-125">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="08788-126">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="08788-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="08788-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08788-127">Parent Elements</span></span>  
  
|<span data-ttu-id="08788-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="08788-128">Element</span></span>|<span data-ttu-id="08788-129">Описание</span><span class="sxs-lookup"><span data-stu-id="08788-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="08788-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="08788-130">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="08788-131">Определяет текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="08788-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="08788-132">См. также</span><span class="sxs-lookup"><span data-stu-id="08788-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="08788-133">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="08788-133">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="08788-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="08788-134">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="08788-135">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="08788-135">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="08788-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="08788-136">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="08788-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="08788-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="08788-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="08788-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="08788-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="08788-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="08788-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="08788-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="08788-141">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="08788-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="08788-142">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="08788-142">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
