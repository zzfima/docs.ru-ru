---
title: '&lt;XmlElement&gt;'
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 70ff9b93bcd59331c5fa5e66bb51dc4cd1e043ff
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767652"
---
# <a name="ltxmlelementgt"></a><span data-ttu-id="4877b-102">&lt;XmlElement&gt;</span><span class="sxs-lookup"><span data-stu-id="4877b-102">&lt;xmlElement&gt;</span></span>
<span data-ttu-id="4877b-103">Указывает элемент XML, отправляемый в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="4877b-103">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="4877b-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4877b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4877b-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="4877b-105">\<bindings></span></span>  
<span data-ttu-id="4877b-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="4877b-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="4877b-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4877b-107">\<binding></span></span>  
<span data-ttu-id="4877b-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="4877b-108">\<security></span></span>  
<span data-ttu-id="4877b-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="4877b-109">\<message></span></span>  
<span data-ttu-id="4877b-110">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="4877b-110">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4877b-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4877b-111">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>  
      <xmlElement xmlElement="String" />  
</tokenRequestParameters>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4877b-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4877b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4877b-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4877b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4877b-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4877b-114">Attributes</span></span>  
  
|<span data-ttu-id="4877b-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4877b-115">Attribute</span></span>|<span data-ttu-id="4877b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4877b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4877b-117">xmlElement</span><span class="sxs-lookup"><span data-stu-id="4877b-117">xmlElement</span></span>|<span data-ttu-id="4877b-118">Строка, указывающая элемент XML, который отправляется в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="4877b-118">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4877b-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4877b-119">Child Elements</span></span>  
 <span data-ttu-id="4877b-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4877b-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4877b-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4877b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4877b-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="4877b-122">Element</span></span>|<span data-ttu-id="4877b-123">Описание</span><span class="sxs-lookup"><span data-stu-id="4877b-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4877b-124">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="4877b-124">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="4877b-125">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="4877b-125">A collection of token request parameters.</span></span> <span data-ttu-id="4877b-126">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="4877b-126">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4877b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4877b-127">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>  
 [<span data-ttu-id="4877b-128">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="4877b-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="4877b-129">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="4877b-129">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="4877b-130">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="4877b-130">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="4877b-131">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="4877b-131">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="4877b-132">Привязки</span><span class="sxs-lookup"><span data-stu-id="4877b-132">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
