---
title: '&lt;remove&gt; элемента &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 7610a8e95996f15133ae58ec33c4afd9e2309cac
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146216"
---
# <a name="ltremovegt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="07f25-102">&lt;remove&gt; элемента &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="07f25-102">&lt;remove&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="07f25-103">Указывает типы утверждений в федеративных учетных данных, которые должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="07f25-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="07f25-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="07f25-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="07f25-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="07f25-105">\<bindings></span></span>  
<span data-ttu-id="07f25-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="07f25-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="07f25-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="07f25-107">\<binding></span></span>  
<span data-ttu-id="07f25-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="07f25-108">\<security></span></span>  
<span data-ttu-id="07f25-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="07f25-109">\<message></span></span>  
<span data-ttu-id="07f25-110">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="07f25-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07f25-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="07f25-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07f25-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="07f25-112">Attributes and Elements</span></span>  
 <span data-ttu-id="07f25-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="07f25-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07f25-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="07f25-114">Attributes</span></span>  
  
|<span data-ttu-id="07f25-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="07f25-115">Attribute</span></span>|<span data-ttu-id="07f25-116">Описание</span><span class="sxs-lookup"><span data-stu-id="07f25-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07f25-117">claimType</span><span class="sxs-lookup"><span data-stu-id="07f25-117">claimType</span></span>|<span data-ttu-id="07f25-118">Универсальный код ресурса (URI), определяющий тип утверждения, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="07f25-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07f25-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="07f25-119">Child Elements</span></span>  
 <span data-ttu-id="07f25-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="07f25-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07f25-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="07f25-121">Parent Elements</span></span>  
  
|<span data-ttu-id="07f25-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="07f25-122">Element</span></span>|<span data-ttu-id="07f25-123">Описание</span><span class="sxs-lookup"><span data-stu-id="07f25-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07f25-124">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="07f25-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="07f25-125">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="07f25-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="07f25-126">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="07f25-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="07f25-127">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="07f25-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="07f25-128">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="07f25-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="07f25-129">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="07f25-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07f25-130">См. также</span><span class="sxs-lookup"><span data-stu-id="07f25-130">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
