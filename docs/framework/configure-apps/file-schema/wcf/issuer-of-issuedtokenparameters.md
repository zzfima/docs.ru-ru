---
title: <issuer> из <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: 77ed9534ce872e805a6a6ea2c21a38710e6bc0fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925263"
---
# <a name="issuer-of-issuedtokenparameters"></a><span data-ttu-id="dcc4c-102">\<> издателя для \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="dcc4c-102">\<issuer> of \<issuedTokenParameters></span></span>
<span data-ttu-id="dcc4c-103">Задает службу маркеров безопасности, выдающую маркеры безопасности.</span><span class="sxs-lookup"><span data-stu-id="dcc4c-103">Specifies the Security Token Service (STS) that issues security tokens.</span></span>  
  
 <span data-ttu-id="dcc4c-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="dcc4c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="dcc4c-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="dcc4c-105">\<bindings></span></span>  
<span data-ttu-id="dcc4c-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="dcc4c-106">\<customBinding></span></span>  
<span data-ttu-id="dcc4c-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="dcc4c-107">\<binding></span></span>  
<span data-ttu-id="dcc4c-108">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="dcc4c-108">\<security></span></span>  
<span data-ttu-id="dcc4c-109">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="dcc4c-109">\<issuedTokenParameters></span></span>  
<span data-ttu-id="dcc4c-110">\<> издателя</span><span class="sxs-lookup"><span data-stu-id="dcc4c-110">\<issuer></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcc4c-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dcc4c-111">Syntax</span></span>  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dcc4c-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dcc4c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dcc4c-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dcc4c-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dcc4c-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dcc4c-114">Attributes</span></span>  
  
|<span data-ttu-id="dcc4c-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dcc4c-115">Attribute</span></span>|<span data-ttu-id="dcc4c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="dcc4c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dcc4c-117">адрес</span><span class="sxs-lookup"><span data-stu-id="dcc4c-117">address</span></span>|<span data-ttu-id="dcc4c-118">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="dcc4c-118">Required string.</span></span> <span data-ttu-id="dcc4c-119">URL-адрес для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="dcc4c-119">The URL of the STS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dcc4c-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dcc4c-120">Child Elements</span></span>  
  
|<span data-ttu-id="dcc4c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="dcc4c-121">Element</span></span>|<span data-ttu-id="dcc4c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="dcc4c-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcc4c-123">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="dcc4c-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="dcc4c-124">Коллекция заголовков адресов для конечных точек, которые может создать конструктор.</span><span class="sxs-lookup"><span data-stu-id="dcc4c-124">A collection of address headers for the endpoints that the builder can create.</span></span>|  
|[<span data-ttu-id="dcc4c-125">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="dcc4c-125">\<identity></span></span>](identity.md)|<span data-ttu-id="dcc4c-126">При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="dcc4c-126">When using an issued token, specifies settings that enable the client to authenticate the server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dcc4c-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dcc4c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="dcc4c-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="dcc4c-128">Element</span></span>|<span data-ttu-id="dcc4c-129">Описание</span><span class="sxs-lookup"><span data-stu-id="dcc4c-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dcc4c-130">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="dcc4c-130">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="dcc4c-131">Определяет текущий выданный маркер.</span><span class="sxs-lookup"><span data-stu-id="dcc4c-131">Specifies the current issued token.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dcc4c-132">См. также</span><span class="sxs-lookup"><span data-stu-id="dcc4c-132">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="dcc4c-133">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="dcc4c-133">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="dcc4c-134">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="dcc4c-134">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="dcc4c-135">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="dcc4c-135">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="dcc4c-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="dcc4c-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="dcc4c-137">Привязки</span><span class="sxs-lookup"><span data-stu-id="dcc4c-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dcc4c-138">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="dcc4c-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="dcc4c-139">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="dcc4c-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="dcc4c-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="dcc4c-140">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="dcc4c-141">Практическое руководство. Создание пользовательской привязки с помощью SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dcc4c-141">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="dcc4c-142">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="dcc4c-142">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
