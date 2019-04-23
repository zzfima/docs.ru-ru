---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: a72641b438801cfd493c322297e7c384e83e687c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230503"
---
# <a name="xmlelement"></a><span data-ttu-id="32015-101">\<xmlElement ></span><span class="sxs-lookup"><span data-stu-id="32015-101">\<xmlElement></span></span>
<span data-ttu-id="32015-102">Указывает элемент XML, отправляемый в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="32015-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="32015-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="32015-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="32015-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="32015-104">\<bindings></span></span>  
<span data-ttu-id="32015-105">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="32015-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="32015-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="32015-106">\<binding></span></span>  
<span data-ttu-id="32015-107">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="32015-107">\<security></span></span>  
<span data-ttu-id="32015-108">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="32015-108">\<message></span></span>  
<span data-ttu-id="32015-109">\<tokenRequestParameters></span><span class="sxs-lookup"><span data-stu-id="32015-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32015-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32015-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32015-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="32015-111">Attributes and Elements</span></span>  
 <span data-ttu-id="32015-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="32015-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32015-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="32015-113">Attributes</span></span>  
  
|<span data-ttu-id="32015-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="32015-114">Attribute</span></span>|<span data-ttu-id="32015-115">Описание</span><span class="sxs-lookup"><span data-stu-id="32015-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32015-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="32015-116">xmlElement</span></span>|<span data-ttu-id="32015-117">Строка, указывающая элемент XML, который отправляется в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="32015-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32015-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="32015-118">Child Elements</span></span>  
 <span data-ttu-id="32015-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="32015-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32015-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="32015-120">Parent Elements</span></span>  
  
|<span data-ttu-id="32015-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="32015-121">Element</span></span>|<span data-ttu-id="32015-122">Описание</span><span class="sxs-lookup"><span data-stu-id="32015-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32015-123">\<tokenRequestParameters ></span><span class="sxs-lookup"><span data-stu-id="32015-123">\<tokenRequestParameters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/tokenrequestparameters.md)|<span data-ttu-id="32015-124">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="32015-124">A collection of token request parameters.</span></span> <span data-ttu-id="32015-125">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="32015-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="32015-126">См. также</span><span class="sxs-lookup"><span data-stu-id="32015-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="32015-127">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="32015-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="32015-128">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="32015-128">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="32015-129">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="32015-129">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="32015-130">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="32015-130">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="32015-131">Привязки</span><span class="sxs-lookup"><span data-stu-id="32015-131">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
