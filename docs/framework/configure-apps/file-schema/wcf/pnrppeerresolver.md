---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: 2404f00b2a3ba03e89c1e21fb25e13cabb8feed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783283"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="4a39d-101">\<pnrpPeerResolver ></span><span class="sxs-lookup"><span data-stu-id="4a39d-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="4a39d-102">Задает использование распознавателя протокола PNRP (протокола однорангового разрешения имен) в качестве распознавателя.</span><span class="sxs-lookup"><span data-stu-id="4a39d-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="4a39d-103">Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4a39d-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="4a39d-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4a39d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4a39d-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="4a39d-105">\<bindings></span></span>  
<span data-ttu-id="4a39d-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4a39d-106">\<customBinding></span></span>  
<span data-ttu-id="4a39d-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4a39d-107">\<binding></span></span>  
<span data-ttu-id="4a39d-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="4a39d-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a39d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a39d-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a39d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4a39d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4a39d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4a39d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a39d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4a39d-112">Attributes</span></span>  
  
|<span data-ttu-id="4a39d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4a39d-113">Attribute</span></span>|<span data-ttu-id="4a39d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4a39d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4a39d-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="4a39d-115">resolverType</span></span>|<span data-ttu-id="4a39d-116">Строка, указывающая распознаватель для использования.</span><span class="sxs-lookup"><span data-stu-id="4a39d-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="4a39d-117">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="4a39d-117">This attribute is optional.</span></span> <span data-ttu-id="4a39d-118">Если значение не задано или равно пустой строке, используется протокол PNRP.</span><span class="sxs-lookup"><span data-stu-id="4a39d-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a39d-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4a39d-119">Child Elements</span></span>  
 <span data-ttu-id="4a39d-120">Нет</span><span class="sxs-lookup"><span data-stu-id="4a39d-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a39d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4a39d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="4a39d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="4a39d-122">Element</span></span>|<span data-ttu-id="4a39d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="4a39d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a39d-124">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4a39d-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="4a39d-125">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="4a39d-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4a39d-126">Пример</span><span class="sxs-lookup"><span data-stu-id="4a39d-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="4a39d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4a39d-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="4a39d-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="4a39d-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="4a39d-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="4a39d-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="4a39d-130">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="4a39d-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="4a39d-131">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="4a39d-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="4a39d-132">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="4a39d-132">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
