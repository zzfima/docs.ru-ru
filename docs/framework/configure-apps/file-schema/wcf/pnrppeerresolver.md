---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d7c6c8efa971fb60f0257cc1c74ceda72e31cb84
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400050"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="c966b-101">\<Пнрппирресолвер ></span><span class="sxs-lookup"><span data-stu-id="c966b-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="c966b-102">Задает использование распознавателя протокола PNRP (протокола однорангового разрешения имен) в качестве распознавателя.</span><span class="sxs-lookup"><span data-stu-id="c966b-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="c966b-103">Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c966b-103">This element is optional because PNRP is the default resolver.</span></span>  
  
<span data-ttu-id="c966b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c966b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c966b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c966b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c966b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="c966b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="c966b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="c966b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="c966b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="c966b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="c966b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Пнрпресолвер >**</span><span class="sxs-lookup"><span data-stu-id="c966b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c966b-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c966b-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c966b-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c966b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c966b-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c966b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c966b-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c966b-113">Attributes</span></span>  
  
|<span data-ttu-id="c966b-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c966b-114">Attribute</span></span>|<span data-ttu-id="c966b-115">Описание</span><span class="sxs-lookup"><span data-stu-id="c966b-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c966b-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="c966b-116">resolverType</span></span>|<span data-ttu-id="c966b-117">Строка, указывающая распознаватель для использования.</span><span class="sxs-lookup"><span data-stu-id="c966b-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="c966b-118">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c966b-118">This attribute is optional.</span></span> <span data-ttu-id="c966b-119">Если значение не задано или равно пустой строке, используется протокол PNRP.</span><span class="sxs-lookup"><span data-stu-id="c966b-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c966b-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c966b-120">Child Elements</span></span>  
 <span data-ttu-id="c966b-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c966b-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c966b-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c966b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="c966b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="c966b-123">Element</span></span>|<span data-ttu-id="c966b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="c966b-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c966b-125">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="c966b-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="c966b-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="c966b-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c966b-127">Пример</span><span class="sxs-lookup"><span data-stu-id="c966b-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="c966b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="c966b-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c966b-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="c966b-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c966b-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="c966b-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c966b-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="c966b-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c966b-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="c966b-132">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="c966b-133">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="c966b-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
