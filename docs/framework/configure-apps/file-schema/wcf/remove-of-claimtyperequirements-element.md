---
title: <remove> элемента <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 9ab1162ff5d86b8a9d43dae79ebf9c9321119206
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783101"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="c01a8-102">\<Удалить > из \<claimTypeRequirements > элемент</span><span class="sxs-lookup"><span data-stu-id="c01a8-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="c01a8-103">Указывает типы утверждений в федеративных учетных данных, которые должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="c01a8-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
 <span data-ttu-id="c01a8-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c01a8-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c01a8-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="c01a8-105">\<bindings></span></span>  
<span data-ttu-id="c01a8-106">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="c01a8-106">\<wsFederatedBinding></span></span>  
<span data-ttu-id="c01a8-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c01a8-107">\<binding></span></span>  
<span data-ttu-id="c01a8-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="c01a8-108">\<security></span></span>  
<span data-ttu-id="c01a8-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="c01a8-109">\<message></span></span>  
<span data-ttu-id="c01a8-110">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="c01a8-110">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c01a8-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c01a8-111">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c01a8-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c01a8-112">Attributes and Elements</span></span>  
 <span data-ttu-id="c01a8-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c01a8-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c01a8-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c01a8-114">Attributes</span></span>  
  
|<span data-ttu-id="c01a8-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c01a8-115">Attribute</span></span>|<span data-ttu-id="c01a8-116">Описание</span><span class="sxs-lookup"><span data-stu-id="c01a8-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c01a8-117">claimType</span><span class="sxs-lookup"><span data-stu-id="c01a8-117">claimType</span></span>|<span data-ttu-id="c01a8-118">Универсальный код ресурса (URI), определяющий тип утверждения, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c01a8-118">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c01a8-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c01a8-119">Child Elements</span></span>  
 <span data-ttu-id="c01a8-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="c01a8-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c01a8-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c01a8-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c01a8-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="c01a8-122">Element</span></span>|<span data-ttu-id="c01a8-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c01a8-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c01a8-124">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="c01a8-124">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="c01a8-125">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="c01a8-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="c01a8-126">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="c01a8-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="c01a8-127">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="c01a8-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="c01a8-128">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="c01a8-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="c01a8-129">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="c01a8-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c01a8-130">См. также</span><span class="sxs-lookup"><span data-stu-id="c01a8-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
