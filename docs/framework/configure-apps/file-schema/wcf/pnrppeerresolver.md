---
title: '&lt;pnrpPeerResolver&gt;'
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: cefd46d7810149264f9c431a212da0f3f51f8186
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577650"
---
# <a name="ltpnrppeerresolvergt"></a><span data-ttu-id="83628-102">&lt;pnrpPeerResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="83628-102">&lt;pnrpPeerResolver&gt;</span></span>
<span data-ttu-id="83628-103">Задает использование распознавателя протокола PNRP (протокола однорангового разрешения имен) в качестве распознавателя.</span><span class="sxs-lookup"><span data-stu-id="83628-103">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="83628-104">Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83628-104">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="83628-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="83628-105">\<system.serviceModel></span></span>  
<span data-ttu-id="83628-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="83628-106">\<bindings></span></span>  
<span data-ttu-id="83628-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="83628-107">\<customBinding></span></span>  
<span data-ttu-id="83628-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="83628-108">\<binding></span></span>  
<span data-ttu-id="83628-109">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="83628-109">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83628-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83628-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83628-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="83628-111">Attributes and Elements</span></span>  
 <span data-ttu-id="83628-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="83628-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83628-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="83628-113">Attributes</span></span>  
  
|<span data-ttu-id="83628-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="83628-114">Attribute</span></span>|<span data-ttu-id="83628-115">Описание</span><span class="sxs-lookup"><span data-stu-id="83628-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83628-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="83628-116">resolverType</span></span>|<span data-ttu-id="83628-117">Строка, указывающая распознаватель для использования.</span><span class="sxs-lookup"><span data-stu-id="83628-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="83628-118">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="83628-118">This attribute is optional.</span></span> <span data-ttu-id="83628-119">Если значение не задано или равно пустой строке, используется протокол PNRP.</span><span class="sxs-lookup"><span data-stu-id="83628-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83628-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="83628-120">Child Elements</span></span>  
 <span data-ttu-id="83628-121">Нет</span><span class="sxs-lookup"><span data-stu-id="83628-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83628-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="83628-122">Parent Elements</span></span>  
  
|<span data-ttu-id="83628-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="83628-123">Element</span></span>|<span data-ttu-id="83628-124">Описание</span><span class="sxs-lookup"><span data-stu-id="83628-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83628-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="83628-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="83628-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="83628-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="83628-127">Пример</span><span class="sxs-lookup"><span data-stu-id="83628-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="83628-128">См. также</span><span class="sxs-lookup"><span data-stu-id="83628-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="83628-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="83628-129">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="83628-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="83628-130">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="83628-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="83628-131">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="83628-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="83628-132">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="83628-133">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="83628-133">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
