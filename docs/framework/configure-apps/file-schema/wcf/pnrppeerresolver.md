---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: d3e88d7f2dd991091d3d7abdc715e125ddc9ac56
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738783"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="5baf1-101">\<Пнрппирресолвер ></span><span class="sxs-lookup"><span data-stu-id="5baf1-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="5baf1-102">Задает использование распознавателя протокола PNRP (протокола однорангового разрешения имен) в качестве распознавателя.</span><span class="sxs-lookup"><span data-stu-id="5baf1-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="5baf1-103">Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5baf1-103">This element is optional because PNRP is the default resolver.</span></span>  
  
<span data-ttu-id="5baf1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5baf1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5baf1-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="5baf1-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="5baf1-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="5baf1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="5baf1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="5baf1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="5baf1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="5baf1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="5baf1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<пнрпресолвер >**</span><span class="sxs-lookup"><span data-stu-id="5baf1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<pnrpResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5baf1-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5baf1-110">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5baf1-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5baf1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5baf1-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5baf1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5baf1-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5baf1-113">Attributes</span></span>  
  
|<span data-ttu-id="5baf1-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5baf1-114">Attribute</span></span>|<span data-ttu-id="5baf1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5baf1-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5baf1-116">resolverType</span><span class="sxs-lookup"><span data-stu-id="5baf1-116">resolverType</span></span>|<span data-ttu-id="5baf1-117">Строка, указывающая распознаватель для использования.</span><span class="sxs-lookup"><span data-stu-id="5baf1-117">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="5baf1-118">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="5baf1-118">This attribute is optional.</span></span> <span data-ttu-id="5baf1-119">Если значение не задано или равно пустой строке, используется протокол PNRP.</span><span class="sxs-lookup"><span data-stu-id="5baf1-119">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5baf1-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5baf1-120">Child Elements</span></span>  
 <span data-ttu-id="5baf1-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="5baf1-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5baf1-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5baf1-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5baf1-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="5baf1-123">Element</span></span>|<span data-ttu-id="5baf1-124">Описание</span><span class="sxs-lookup"><span data-stu-id="5baf1-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5baf1-125">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="5baf1-125">\<binding></span></span>](bindings.md)|<span data-ttu-id="5baf1-126">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="5baf1-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5baf1-127">Пример</span><span class="sxs-lookup"><span data-stu-id="5baf1-127">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="5baf1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5baf1-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5baf1-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="5baf1-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5baf1-130">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="5baf1-130">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5baf1-131">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="5baf1-131">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5baf1-132">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="5baf1-132">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="5baf1-133">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="5baf1-133">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
