---
title: <clear> элемента <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: ef42fde7-f292-4610-9111-9fea382c3b5f
ms.openlocfilehash: 01f101f7d0dd5da6a834a4ffb2c7e09df0e23cd8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400524"
---
# <a name="clear-of-claimtyperequirements-element"></a><span data-ttu-id="eb2b7-102">\<Очистка > \<элемента > claimTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="eb2b7-102">\<clear> of \<claimTypeRequirements> element</span></span>
<span data-ttu-id="eb2b7-103">Указывает, что все типы утверждений в федеративных учетных данных должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-103">Specifies that all the claim types to be removed in the federated credential.</span></span> <span data-ttu-id="eb2b7-104">Это обеспечивает запуск пустой коллекции.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-104">This ensures that the collection starts empty.</span></span>  
  
<span data-ttu-id="eb2b7-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="eb2b7-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="eb2b7-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="eb2b7-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="eb2b7-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="eb2b7-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="eb2b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="eb2b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="eb2b7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="eb2b7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="eb2b7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="eb2b7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="eb2b7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> сообщения**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="eb2b7-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="eb2b7-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<claimTypeRequirements >** ](claimtyperequirements-for-message.md)</span><span class="sxs-lookup"><span data-stu-id="eb2b7-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-for-message.md)</span></span>\
<span data-ttu-id="eb2b7-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<очистить >**</span><span class="sxs-lookup"><span data-stu-id="eb2b7-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb2b7-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb2b7-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <clear />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb2b7-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eb2b7-115">Attributes and Elements</span></span>  
 <span data-ttu-id="eb2b7-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb2b7-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eb2b7-117">Attributes</span></span>  
 <span data-ttu-id="eb2b7-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-118">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb2b7-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eb2b7-119">Child Elements</span></span>  
 <span data-ttu-id="eb2b7-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb2b7-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eb2b7-121">Parent Elements</span></span>  
  
|<span data-ttu-id="eb2b7-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="eb2b7-122">Element</span></span>|<span data-ttu-id="eb2b7-123">Описание</span><span class="sxs-lookup"><span data-stu-id="eb2b7-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb2b7-124">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="eb2b7-124">\<claimTypeRequirements></span></span>](claimtyperequirements-for-message.md)|<span data-ttu-id="eb2b7-125">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-125">Specifies a collection of required claim types.</span></span> <span data-ttu-id="eb2b7-126">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-126">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="eb2b7-127">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-127">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="eb2b7-128">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-128">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="eb2b7-129">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="eb2b7-129">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eb2b7-130">См. также</span><span class="sxs-lookup"><span data-stu-id="eb2b7-130">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
