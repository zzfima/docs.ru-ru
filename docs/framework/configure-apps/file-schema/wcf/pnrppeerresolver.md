---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: e7e82117304ac133e5e84c0fc36b987560bcef96
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933800"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="c5269-101">\<Пнрппирресолвер ></span><span class="sxs-lookup"><span data-stu-id="c5269-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="c5269-102">Задает использование распознавателя протокола PNRP (протокола однорангового разрешения имен) в качестве распознавателя.</span><span class="sxs-lookup"><span data-stu-id="c5269-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="c5269-103">Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5269-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="c5269-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="c5269-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c5269-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="c5269-105">\<bindings></span></span>  
<span data-ttu-id="c5269-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c5269-106">\<customBinding></span></span>  
<span data-ttu-id="c5269-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c5269-107">\<binding></span></span>  
<span data-ttu-id="c5269-108">\<Пнрпресолвер ></span><span class="sxs-lookup"><span data-stu-id="c5269-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5269-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5269-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5269-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c5269-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c5269-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c5269-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5269-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c5269-112">Attributes</span></span>  
  
|<span data-ttu-id="c5269-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c5269-113">Attribute</span></span>|<span data-ttu-id="c5269-114">Описание</span><span class="sxs-lookup"><span data-stu-id="c5269-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5269-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="c5269-115">resolverType</span></span>|<span data-ttu-id="c5269-116">Строка, указывающая распознаватель для использования.</span><span class="sxs-lookup"><span data-stu-id="c5269-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="c5269-117">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c5269-117">This attribute is optional.</span></span> <span data-ttu-id="c5269-118">Если значение не задано или равно пустой строке, используется протокол PNRP.</span><span class="sxs-lookup"><span data-stu-id="c5269-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5269-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c5269-119">Child Elements</span></span>  
 <span data-ttu-id="c5269-120">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c5269-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c5269-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c5269-121">Parent Elements</span></span>  
  
|<span data-ttu-id="c5269-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="c5269-122">Element</span></span>|<span data-ttu-id="c5269-123">Описание</span><span class="sxs-lookup"><span data-stu-id="c5269-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5269-124">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c5269-124">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c5269-125">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="c5269-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c5269-126">Пример</span><span class="sxs-lookup"><span data-stu-id="c5269-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="c5269-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c5269-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c5269-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="c5269-128">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c5269-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="c5269-129">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c5269-130">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="c5269-130">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c5269-131">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c5269-131">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="c5269-132">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="c5269-132">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
