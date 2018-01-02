---
title: "&lt;clear&gt; элемента &lt;claimTypeRequirements&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 71cc4516362691484408ae2f81dfee462bd560d9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcleargt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="5b726-102">&lt;clear&gt; элемента &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="5b726-102">&lt;clear&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="5b726-103">Указывает, что все типы утверждений в федеративных учетных данных должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="5b726-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="5b726-104">Это обеспечивает запуск пустой коллекции.</span><span class="sxs-lookup"><span data-stu-id="5b726-104">This ensures that the collection starts empty.</span></span>  
  
 <span data-ttu-id="5b726-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5b726-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5b726-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="5b726-106">\<bindings></span></span>  
<span data-ttu-id="5b726-107">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="5b726-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="5b726-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="5b726-108">\<binding></span></span>  
<span data-ttu-id="5b726-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="5b726-109">\<security></span></span>  
<span data-ttu-id="5b726-110">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="5b726-110">\<message></span></span>  
<span data-ttu-id="5b726-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="5b726-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b726-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b726-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <clear />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b726-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5b726-113">Attributes and Elements</span></span>  
 <span data-ttu-id="5b726-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5b726-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b726-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5b726-115">Attributes</span></span>  
 <span data-ttu-id="5b726-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5b726-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5b726-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5b726-117">Child Elements</span></span>  
 <span data-ttu-id="5b726-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5b726-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b726-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5b726-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5b726-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="5b726-120">Element</span></span>|<span data-ttu-id="5b726-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="5b726-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b726-122">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="5b726-122">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="5b726-123">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="5b726-123">Specifies a collection of required claim types.</span></span> <span data-ttu-id="5b726-124">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="5b726-124">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="5b726-125">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="5b726-125">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="5b726-126">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="5b726-126">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="5b726-127">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="5b726-127">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b726-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5b726-128">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
