---
title: "&lt;issuerMetadata&gt; для &lt;issuedTokenParameters&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ccd0417aeebbaf08d28457dd94a4d1698882c79e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="258ba-102">&lt;issuerMetadata&gt; для &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="258ba-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="258ba-103">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="258ba-103">\<system.serviceModel></span></span>  
<span data-ttu-id="258ba-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="258ba-104">\<bindings></span></span>  
<span data-ttu-id="258ba-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="258ba-105">\<customBinding></span></span>  
<span data-ttu-id="258ba-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="258ba-106">\<binding></span></span>  
<span data-ttu-id="258ba-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="258ba-107">\<security></span></span>  
<span data-ttu-id="258ba-108">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="258ba-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="258ba-109">\<issuerMetadata ></span><span class="sxs-lookup"><span data-stu-id="258ba-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="258ba-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="258ba-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="258ba-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="258ba-111">Attributes and Elements</span></span>  
 <span data-ttu-id="258ba-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="258ba-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="258ba-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="258ba-113">Attributes</span></span>  
  
|<span data-ttu-id="258ba-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="258ba-114">Attribute</span></span>|<span data-ttu-id="258ba-115">Описание</span><span class="sxs-lookup"><span data-stu-id="258ba-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="258ba-116">address</span><span class="sxs-lookup"><span data-stu-id="258ba-116">address</span></span>|<span data-ttu-id="258ba-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="258ba-117">Required.</span></span> <span data-ttu-id="258ba-118">Строка, задающая адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="258ba-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="258ba-119">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="258ba-119">The address must be an absolute URI.</span></span> <span data-ttu-id="258ba-120">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="258ba-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="258ba-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="258ba-121">Child Elements</span></span>  
  
|<span data-ttu-id="258ba-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="258ba-122">Element</span></span>|<span data-ttu-id="258ba-123">Описание</span><span class="sxs-lookup"><span data-stu-id="258ba-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="258ba-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="258ba-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="258ba-125">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="258ba-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="258ba-126">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="258ba-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="258ba-127">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="258ba-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="258ba-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="258ba-128">Parent Elements</span></span>  
  
|<span data-ttu-id="258ba-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="258ba-129">Element</span></span>|<span data-ttu-id="258ba-130">Описание</span><span class="sxs-lookup"><span data-stu-id="258ba-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="258ba-131">\<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="258ba-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="258ba-132">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="258ba-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="258ba-133">См. также</span><span class="sxs-lookup"><span data-stu-id="258ba-133">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="258ba-134">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="258ba-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="258ba-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="258ba-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="258ba-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="258ba-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="258ba-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="258ba-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="258ba-138">Привязки</span><span class="sxs-lookup"><span data-stu-id="258ba-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="258ba-139">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="258ba-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="258ba-140">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="258ba-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="258ba-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="258ba-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="258ba-142">Как: Создание пользовательской привязки, с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="258ba-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="258ba-143">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="258ba-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
