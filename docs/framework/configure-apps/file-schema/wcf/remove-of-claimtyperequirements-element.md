---
title: <remove> элемента <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: 8ef05bc4-1950-4ee4-95c5-1c6a394eff7e
ms.openlocfilehash: 84f4208d3f4581cf7e8c4455bf3f5d78f7e13b9f
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399997"
---
# <a name="remove-of-claimtyperequirements-element"></a><span data-ttu-id="6a95d-102">\<Удаление > \<элемента > claimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="6a95d-102">\<remove> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="6a95d-103">Указывает типы утверждений в федеративных учетных данных, которые должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="6a95d-103">Specifies the types of claims to be removed in the federated credential.</span></span>  
  
<span data-ttu-id="6a95d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6a95d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6a95d-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6a95d-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6a95d-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6a95d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6a95d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6a95d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="6a95d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="6a95d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6a95d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6a95d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="6a95d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> сообщения**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6a95d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="6a95d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequirements >** ](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="6a95d-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="6a95d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Удалить >**</span><span class="sxs-lookup"><span data-stu-id="6a95d-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a95d-113">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a95d-113">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <remove claimType="URI" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a95d-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6a95d-114">Attributes and Elements</span></span>  
 <span data-ttu-id="6a95d-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6a95d-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a95d-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6a95d-116">Attributes</span></span>  
  
|<span data-ttu-id="6a95d-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6a95d-117">Attribute</span></span>|<span data-ttu-id="6a95d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="6a95d-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a95d-119">claimType</span><span class="sxs-lookup"><span data-stu-id="6a95d-119">claimType</span></span>|<span data-ttu-id="6a95d-120">Универсальный код ресурса (URI), определяющий тип утверждения, которое требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="6a95d-120">A URI that defines the type of a claim to be removed.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a95d-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6a95d-121">Child Elements</span></span>  
 <span data-ttu-id="6a95d-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="6a95d-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6a95d-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6a95d-123">Parent Elements</span></span>  
  
|<span data-ttu-id="6a95d-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="6a95d-124">Element</span></span>|<span data-ttu-id="6a95d-125">Описание</span><span class="sxs-lookup"><span data-stu-id="6a95d-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a95d-126">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="6a95d-126">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="6a95d-127">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="6a95d-127">Specifies a collection of required claim types.</span></span> <span data-ttu-id="6a95d-128">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="6a95d-128">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="6a95d-129">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="6a95d-129">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="6a95d-130">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="6a95d-130">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="6a95d-131">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="6a95d-131">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a95d-132">См. также</span><span class="sxs-lookup"><span data-stu-id="6a95d-132">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
