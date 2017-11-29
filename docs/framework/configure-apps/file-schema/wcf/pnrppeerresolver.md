---
title: '&lt;pnrpPeerResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cd93bdadec120050813fcc1097d3041d6be94f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="4d9e8-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="4d9e8-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="4d9e8-103">Задает использование распознавателя протокола PNRP (протокола однорангового разрешения имен) в качестве распознавателя.</span><span class="sxs-lookup"><span data-stu-id="4d9e8-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="4d9e8-104">Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4d9e8-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="4d9e8-105">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="4d9e8-105">\<system.serviceModel></span></span>  
<span data-ttu-id="4d9e8-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="4d9e8-106">\<bindings></span></span>  
<span data-ttu-id="4d9e8-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4d9e8-107">\<customBinding></span></span>  
<span data-ttu-id="4d9e8-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4d9e8-108">\<binding></span></span>  
<span data-ttu-id="4d9e8-109">\<pnrpResolver ></span><span class="sxs-lookup"><span data-stu-id="4d9e8-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d9e8-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4d9e8-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4d9e8-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4d9e8-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4d9e8-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4d9e8-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4d9e8-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4d9e8-113">Attributes</span></span>  
  
|<span data-ttu-id="4d9e8-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4d9e8-114">Attribute</span></span>|<span data-ttu-id="4d9e8-115">Описание</span><span class="sxs-lookup"><span data-stu-id="4d9e8-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4d9e8-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="4d9e8-116">resolverType</span></span>|<span data-ttu-id="4d9e8-117">Строка, указывающая распознаватель для использования.</span><span class="sxs-lookup"><span data-stu-id="4d9e8-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="4d9e8-118">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="4d9e8-118">This attribute is optional.</span></span> <span data-ttu-id="4d9e8-119">Если значение не задано или равно пустой строке, используется протокол PNRP.</span><span class="sxs-lookup"><span data-stu-id="4d9e8-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4d9e8-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4d9e8-120">Child Elements</span></span>  
 <span data-ttu-id="4d9e8-121">Нет</span><span class="sxs-lookup"><span data-stu-id="4d9e8-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4d9e8-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4d9e8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4d9e8-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="4d9e8-123">Element</span></span>|<span data-ttu-id="4d9e8-124">Описание</span><span class="sxs-lookup"><span data-stu-id="4d9e8-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4d9e8-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4d9e8-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4d9e8-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="4d9e8-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4d9e8-127">Пример</span><span class="sxs-lookup"><span data-stu-id="4d9e8-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d9e8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="4d9e8-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>  
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="4d9e8-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="4d9e8-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4d9e8-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="4d9e8-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="4d9e8-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="4d9e8-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="4d9e8-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4d9e8-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="4d9e8-133">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="4d9e8-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
