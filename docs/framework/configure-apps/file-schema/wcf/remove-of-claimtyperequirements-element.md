---
title: "&lt;remove&gt; элемента &lt;claimTypeRequirements&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 49009cb7e988c27ccc426e29c6ac973e553a0f73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="3be0d-102">&lt;remove&gt; элемента &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="3be0d-102">&lt;remove&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="3be0d-103">Указывает типы утверждений в федеративных учетных данных, которые должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="3be0d-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="3be0d-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="3be0d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="3be0d-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="3be0d-105">\<bindings></span></span>  
<span data-ttu-id="3be0d-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="3be0d-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="3be0d-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="3be0d-107">\<binding></span></span>  
<span data-ttu-id="3be0d-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="3be0d-108">\<security></span></span>  
<span data-ttu-id="3be0d-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="3be0d-109">\<message></span></span>  
<span data-ttu-id="3be0d-110">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="3be0d-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be0d-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3be0d-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>  
      <remove claimType="URI" />  
</claimTypeRequirements>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3be0d-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3be0d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="3be0d-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3be0d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3be0d-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3be0d-114">Attributes</span></span>  
  
|<span data-ttu-id="3be0d-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3be0d-115">Attribute</span></span>|<span data-ttu-id="3be0d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="3be0d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3be0d-117">claimType</span><span class="sxs-lookup"><span data-stu-id="3be0d-117">claimType</span></span>|<span data-ttu-id="3be0d-118">Универсальный код ресурса (URI), определяющий тип утверждения, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="3be0d-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3be0d-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3be0d-119">Child Elements</span></span>  
 <span data-ttu-id="3be0d-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3be0d-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3be0d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3be0d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3be0d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="3be0d-122">Element</span></span>|<span data-ttu-id="3be0d-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="3be0d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3be0d-124">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="3be0d-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="3be0d-125">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="3be0d-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="3be0d-126">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="3be0d-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="3be0d-127">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="3be0d-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="3be0d-128">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="3be0d-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="3be0d-129">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="3be0d-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3be0d-130">См. также</span><span class="sxs-lookup"><span data-stu-id="3be0d-130">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
