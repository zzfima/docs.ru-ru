---
title: '&lt;xmlElement&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d1efe32121bc5744c305ff8ef8eefabd8a9d19e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="14b2e-102">&lt;xmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="14b2e-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="14b2e-103">Указывает элемент XML, отправляемый в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="14b2e-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="14b2e-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="14b2e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="14b2e-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="14b2e-105">\<bindings></span></span>  
<span data-ttu-id="14b2e-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="14b2e-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="14b2e-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="14b2e-107">\<binding></span></span>  
<span data-ttu-id="14b2e-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="14b2e-108">\<security></span></span>  
<span data-ttu-id="14b2e-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="14b2e-109">\<message></span></span>  
<span data-ttu-id="14b2e-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="14b2e-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14b2e-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14b2e-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14b2e-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="14b2e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="14b2e-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="14b2e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14b2e-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="14b2e-114">Attributes</span></span>  
  
|<span data-ttu-id="14b2e-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="14b2e-115">Attribute</span></span>|<span data-ttu-id="14b2e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="14b2e-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="14b2e-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="14b2e-117">xmlElement</span></span>|<span data-ttu-id="14b2e-118">Строка, указывающая элемент XML, который отправляется в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="14b2e-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14b2e-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="14b2e-119">Child Elements</span></span>  
 <span data-ttu-id="14b2e-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="14b2e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14b2e-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="14b2e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="14b2e-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="14b2e-122">Element</span></span>|<span data-ttu-id="14b2e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="14b2e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="14b2e-124">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="14b2e-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="14b2e-125">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="14b2e-125">A collection of token request parameters.</span></span> <span data-ttu-id="14b2e-126">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="14b2e-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="14b2e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="14b2e-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="14b2e-128">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="14b2e-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="14b2e-129">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="14b2e-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="14b2e-130">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="14b2e-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="14b2e-131">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="14b2e-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="14b2e-132">Привязки</span><span class="sxs-lookup"><span data-stu-id="14b2e-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
