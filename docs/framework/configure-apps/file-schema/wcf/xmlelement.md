---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 648147a7e3977648ac3c26c9dfc469629f3b70c3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278295"
---
# <a name="xmlelement"></a><span data-ttu-id="ce8cb-101">\<xmlElement ></span><span class="sxs-lookup"><span data-stu-id="ce8cb-101">\<xmlElement></span></span>
<span data-ttu-id="ce8cb-102">Указывает элемент XML, отправляемый в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="ce8cb-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="ce8cb-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ce8cb-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ce8cb-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ce8cb-104">\<bindings></span></span>  
<span data-ttu-id="ce8cb-105">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="ce8cb-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="ce8cb-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ce8cb-106">\<binding></span></span>  
<span data-ttu-id="ce8cb-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="ce8cb-107">\<security></span></span>  
<span data-ttu-id="ce8cb-108">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="ce8cb-108">\<message></span></span>  
<span data-ttu-id="ce8cb-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="ce8cb-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce8cb-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce8cb-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce8cb-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ce8cb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ce8cb-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ce8cb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce8cb-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ce8cb-113">Attributes</span></span>  
  
|<span data-ttu-id="ce8cb-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ce8cb-114">Attribute</span></span>|<span data-ttu-id="ce8cb-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ce8cb-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ce8cb-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="ce8cb-116">xmlElement</span></span>|<span data-ttu-id="ce8cb-117">Строка, указывающая элемент XML, который отправляется в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="ce8cb-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce8cb-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ce8cb-118">Child Elements</span></span>  
 <span data-ttu-id="ce8cb-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ce8cb-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce8cb-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ce8cb-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ce8cb-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="ce8cb-121">Element</span></span>|<span data-ttu-id="ce8cb-122">Описание</span><span class="sxs-lookup"><span data-stu-id="ce8cb-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce8cb-123">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="ce8cb-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="ce8cb-124">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="ce8cb-124">A collection of token request parameters.</span></span> <span data-ttu-id="ce8cb-125">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="ce8cb-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ce8cb-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ce8cb-126">See also</span></span>
- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="ce8cb-127">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="ce8cb-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ce8cb-128">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="ce8cb-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ce8cb-129">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="ce8cb-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="ce8cb-130">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="ce8cb-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ce8cb-131">Привязки</span><span class="sxs-lookup"><span data-stu-id="ce8cb-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
