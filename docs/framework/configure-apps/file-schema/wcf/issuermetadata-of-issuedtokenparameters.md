---
title: '&lt;issuerMetadata&gt; для &lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: 74f5c1275eb7ef6a89d355b5ea279363ae6b8026
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546206"
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a><span data-ttu-id="32449-102">&lt;issuerMetadata&gt; для &lt;issuedTokenParameters&gt;</span><span class="sxs-lookup"><span data-stu-id="32449-102">&lt;issuerMetadata&gt; of &lt;issuedTokenParameters&gt;</span></span>
<span data-ttu-id="32449-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="32449-103">\<system.serviceModel></span></span>  
<span data-ttu-id="32449-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="32449-104">\<bindings></span></span>  
<span data-ttu-id="32449-105">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="32449-105">\<customBinding></span></span>  
<span data-ttu-id="32449-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="32449-106">\<binding></span></span>  
<span data-ttu-id="32449-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="32449-107">\<security></span></span>  
<span data-ttu-id="32449-108">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="32449-108">\<issuedTokenParameters></span></span>  
<span data-ttu-id="32449-109">\<issuerMetadata></span><span class="sxs-lookup"><span data-stu-id="32449-109">\<issuerMetadata></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32449-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32449-110">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32449-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="32449-111">Attributes and Elements</span></span>  
 <span data-ttu-id="32449-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="32449-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32449-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="32449-113">Attributes</span></span>  
  
|<span data-ttu-id="32449-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="32449-114">Attribute</span></span>|<span data-ttu-id="32449-115">Описание</span><span class="sxs-lookup"><span data-stu-id="32449-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32449-116">address</span><span class="sxs-lookup"><span data-stu-id="32449-116">address</span></span>|<span data-ttu-id="32449-117">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="32449-117">Required.</span></span> <span data-ttu-id="32449-118">Строка, задающая адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="32449-118">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="32449-119">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="32449-119">The address must be an absolute URI.</span></span> <span data-ttu-id="32449-120">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="32449-120">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32449-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="32449-121">Child Elements</span></span>  
  
|<span data-ttu-id="32449-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="32449-122">Element</span></span>|<span data-ttu-id="32449-123">Описание</span><span class="sxs-lookup"><span data-stu-id="32449-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32449-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="32449-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="32449-125">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="32449-125">A collection of address headers.</span></span>|  
|[<span data-ttu-id="32449-126">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="32449-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="32449-127">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="32449-127">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="32449-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="32449-128">Parent Elements</span></span>  
  
|<span data-ttu-id="32449-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="32449-129">Element</span></span>|<span data-ttu-id="32449-130">Описание:</span><span class="sxs-lookup"><span data-stu-id="32449-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32449-131">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="32449-131">\<issuedTokenParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|<span data-ttu-id="32449-132">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="32449-132">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32449-133">См. также</span><span class="sxs-lookup"><span data-stu-id="32449-133">See also</span></span>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="32449-134">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="32449-134">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="32449-135">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="32449-135">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="32449-136">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="32449-136">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="32449-137">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="32449-137">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="32449-138">Привязки</span><span class="sxs-lookup"><span data-stu-id="32449-138">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="32449-139">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="32449-139">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="32449-140">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="32449-140">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="32449-141">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="32449-141">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="32449-142">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="32449-142">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="32449-143">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="32449-143">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
