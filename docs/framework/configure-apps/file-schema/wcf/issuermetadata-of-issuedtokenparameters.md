---
title: <issuerMetadata> из <issuedTokenParameters>
ms.date: 03/30/2017
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
ms.openlocfilehash: fcdd66ecd162dff5be86a1d4ab1b196f50dbd445
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400344"
---
# <a name="issuermetadata-of-issuedtokenparameters"></a><span data-ttu-id="e252c-102">\<issuerMetadata > \<issuedTokenParameters ></span><span class="sxs-lookup"><span data-stu-id="e252c-102">\<issuerMetadata> of \<issuedTokenParameters></span></span>

<span data-ttu-id="e252c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e252c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e252c-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e252c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e252c-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e252c-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="e252c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="e252c-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="e252c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="e252c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="e252c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="e252c-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="e252c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<issuedTokenParameters >** ](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="e252c-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="e252c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerMetadata >**</span><span class="sxs-lookup"><span data-stu-id="e252c-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerMetadata>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e252c-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e252c-111">Syntax</span></span>  
  
```xml  
<issuerMetaData address="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e252c-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e252c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e252c-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e252c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e252c-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e252c-114">Attributes</span></span>  
  
|<span data-ttu-id="e252c-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e252c-115">Attribute</span></span>|<span data-ttu-id="e252c-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e252c-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e252c-117">адрес</span><span class="sxs-lookup"><span data-stu-id="e252c-117">address</span></span>|<span data-ttu-id="e252c-118">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e252c-118">Required.</span></span> <span data-ttu-id="e252c-119">Строка, задающая адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e252c-119">A string that specifies the address of the endpoint.</span></span> <span data-ttu-id="e252c-120">Адрес должен быть абсолютным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="e252c-120">The address must be an absolute URI.</span></span> <span data-ttu-id="e252c-121">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="e252c-121">The default value is an empty string.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e252c-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e252c-122">Child Elements</span></span>  
  
|<span data-ttu-id="e252c-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e252c-123">Element</span></span>|<span data-ttu-id="e252c-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e252c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e252c-125">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="e252c-125">\<headers></span></span>](headers-element.md)|<span data-ttu-id="e252c-126">Коллекция заголовков адреса.</span><span class="sxs-lookup"><span data-stu-id="e252c-126">A collection of address headers.</span></span>|  
|[<span data-ttu-id="e252c-127">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="e252c-127">\<identity></span></span>](identity.md)|<span data-ttu-id="e252c-128">Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e252c-128">An identity that enables the authentication of an endpoint by other endpoints exchanging messages with it.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e252c-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e252c-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e252c-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="e252c-130">Element</span></span>|<span data-ttu-id="e252c-131">Описание</span><span class="sxs-lookup"><span data-stu-id="e252c-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e252c-132">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="e252c-132">\<issuedTokenParameters></span></span>](issuedtokenparameters.md)|<span data-ttu-id="e252c-133">Задает параметры маркера безопасности, выданного в федеративном сценарии безопасности.</span><span class="sxs-lookup"><span data-stu-id="e252c-133">Specifies the parameters for an security token issued in a Federated security scenario.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e252c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="e252c-134">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e252c-135">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="e252c-135">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e252c-136">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="e252c-136">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e252c-137">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="e252c-137">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="e252c-138">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="e252c-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="e252c-139">Привязки</span><span class="sxs-lookup"><span data-stu-id="e252c-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e252c-140">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e252c-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e252c-141">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="e252c-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e252c-142">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="e252c-142">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="e252c-143">Практическое руководство. Создание пользовательской привязки с помощью SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="e252c-143">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="e252c-144">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="e252c-144">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
