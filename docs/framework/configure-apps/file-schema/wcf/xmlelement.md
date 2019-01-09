---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 6a197f7aa29645a08a581bcee103eb94c0e20179
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147022"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="9ceee-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="9ceee-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="9ceee-103">Указывает элемент XML, отправляемый в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="9ceee-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="9ceee-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9ceee-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ceee-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="9ceee-105">\<bindings></span></span>  
<span data-ttu-id="9ceee-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="9ceee-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="9ceee-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="9ceee-107">\<binding></span></span>  
<span data-ttu-id="9ceee-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="9ceee-108">\<security></span></span>  
<span data-ttu-id="9ceee-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="9ceee-109">\<message></span></span>  
<span data-ttu-id="9ceee-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="9ceee-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ceee-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ceee-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ceee-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9ceee-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9ceee-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9ceee-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ceee-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ceee-114">Attributes</span></span>  
  
|<span data-ttu-id="9ceee-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9ceee-115">Attribute</span></span>|<span data-ttu-id="9ceee-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9ceee-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ceee-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="9ceee-117">xmlElement</span></span>|<span data-ttu-id="9ceee-118">Строка, указывающая элемент XML, который отправляется в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="9ceee-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ceee-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ceee-119">Child Elements</span></span>  
 <span data-ttu-id="9ceee-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9ceee-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ceee-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ceee-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9ceee-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ceee-122">Element</span></span>|<span data-ttu-id="9ceee-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="9ceee-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ceee-124">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="9ceee-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="9ceee-125">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="9ceee-125">A collection of token request parameters.</span></span> <span data-ttu-id="9ceee-126">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="9ceee-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ceee-127">См. также</span><span class="sxs-lookup"><span data-stu-id="9ceee-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="9ceee-128">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="9ceee-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="9ceee-129">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="9ceee-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9ceee-130">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="9ceee-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="9ceee-131">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="9ceee-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="9ceee-132">Привязки</span><span class="sxs-lookup"><span data-stu-id="9ceee-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
