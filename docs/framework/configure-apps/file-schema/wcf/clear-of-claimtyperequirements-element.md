---
title: <clear> из <claimTypeRequirements> элемент
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 35d0391951204bd352918d3004f0cc4f9480b0e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090333"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="d0bf6-102">\<Очистить > из \<claimTypeRequirements > элемент</span><span class="sxs-lookup"><span data-stu-id="d0bf6-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="d0bf6-103">Указывает, что все типы утверждений в федеративных учетных данных должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="d0bf6-104">Это обеспечивает запуск пустой коллекции.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="d0bf6-105">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d0bf6-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="d0bf6-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="d0bf6-106">\<bindings></span></span>  
<span data-ttu-id="d0bf6-107">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="d0bf6-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="d0bf6-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="d0bf6-108">\<binding></span></span>  
<span data-ttu-id="d0bf6-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="d0bf6-109">\<security></span></span>  
<span data-ttu-id="d0bf6-110">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="d0bf6-110">\<message></span></span>  
<span data-ttu-id="d0bf6-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="d0bf6-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0bf6-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0bf6-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0bf6-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0bf6-113">Attributes and Elements</span></span>  
 <span data-ttu-id="d0bf6-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0bf6-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0bf6-115">Attributes</span></span>  
 <span data-ttu-id="d0bf6-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d0bf6-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0bf6-117">Child Elements</span></span>  
 <span data-ttu-id="d0bf6-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0bf6-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0bf6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d0bf6-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0bf6-120">Element</span></span>|<span data-ttu-id="d0bf6-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d0bf6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0bf6-122">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="d0bf6-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="d0bf6-123">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="d0bf6-124">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="d0bf6-125">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="d0bf6-126">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="d0bf6-127">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d0bf6-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0bf6-128">См. также</span><span class="sxs-lookup"><span data-stu-id="d0bf6-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
