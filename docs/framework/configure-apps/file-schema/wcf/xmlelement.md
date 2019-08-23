---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: cc178dcc3684ab338282acc369e0ab5c789c15e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941434"
---
# <a name="xmlelement"></a><span data-ttu-id="22266-101">\<> xmlElement</span><span class="sxs-lookup"><span data-stu-id="22266-101">\<xmlElement></span></span>
<span data-ttu-id="22266-102">Указывает элемент XML, отправляемый в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="22266-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
 <span data-ttu-id="22266-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="22266-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="22266-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="22266-104">\<bindings></span></span>  
<span data-ttu-id="22266-105">\<Всфедератедбиндинг ></span><span class="sxs-lookup"><span data-stu-id="22266-105">\<wsFederatedBinding></span></span>  
<span data-ttu-id="22266-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="22266-106">\<binding></span></span>  
<span data-ttu-id="22266-107">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="22266-107">\<security></span></span>  
<span data-ttu-id="22266-108">\<> сообщения</span><span class="sxs-lookup"><span data-stu-id="22266-108">\<message></span></span>  
<span data-ttu-id="22266-109">\<Токенрекуестпараметерс ></span><span class="sxs-lookup"><span data-stu-id="22266-109">\<tokenRequestParameters></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22266-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22266-110">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22266-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="22266-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22266-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="22266-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22266-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="22266-113">Attributes</span></span>  
  
|<span data-ttu-id="22266-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="22266-114">Attribute</span></span>|<span data-ttu-id="22266-115">Описание</span><span class="sxs-lookup"><span data-stu-id="22266-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="22266-116">xmlElement</span><span class="sxs-lookup"><span data-stu-id="22266-116">xmlElement</span></span>|<span data-ttu-id="22266-117">Строка, указывающая элемент XML, который отправляется в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="22266-117">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22266-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="22266-118">Child Elements</span></span>  
 <span data-ttu-id="22266-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="22266-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22266-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="22266-120">Parent Elements</span></span>  
  
|<span data-ttu-id="22266-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="22266-121">Element</span></span>|<span data-ttu-id="22266-122">Описание</span><span class="sxs-lookup"><span data-stu-id="22266-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22266-123">\<Токенрекуестпараметерс ></span><span class="sxs-lookup"><span data-stu-id="22266-123">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="22266-124">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="22266-124">A collection of token request parameters.</span></span> <span data-ttu-id="22266-125">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="22266-125">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22266-126">См. также</span><span class="sxs-lookup"><span data-stu-id="22266-126">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="22266-127">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="22266-127">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="22266-128">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="22266-128">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="22266-129">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="22266-129">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="22266-130">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="22266-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="22266-131">Привязки</span><span class="sxs-lookup"><span data-stu-id="22266-131">Bindings</span></span>](../../../wcf/bindings.md)
