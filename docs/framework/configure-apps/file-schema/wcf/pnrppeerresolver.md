---
title: <pnrpPeerResolver>
ms.date: 03/30/2017
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
ms.openlocfilehash: f98c358cc9891e9d7223d280fc8e50c19aad9759
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55260659"
---
# <a name="pnrppeerresolver"></a><span data-ttu-id="cdca3-101">\<pnrpPeerResolver ></span><span class="sxs-lookup"><span data-stu-id="cdca3-101">\<pnrpPeerResolver></span></span>
<span data-ttu-id="cdca3-102">Задает использование распознавателя протокола PNRP (протокола однорангового разрешения имен) в качестве распознавателя.</span><span class="sxs-lookup"><span data-stu-id="cdca3-102">Specifies that the PNRP (Peer Name Resolution Protocol) resolver is to be used as a resolver.</span></span> <span data-ttu-id="cdca3-103">Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cdca3-103">This element is optional because PNRP is the default resolver.</span></span>  
  
 <span data-ttu-id="cdca3-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="cdca3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="cdca3-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="cdca3-105">\<bindings></span></span>  
<span data-ttu-id="cdca3-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="cdca3-106">\<customBinding></span></span>  
<span data-ttu-id="cdca3-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cdca3-107">\<binding></span></span>  
<span data-ttu-id="cdca3-108">\<pnrpResolver></span><span class="sxs-lookup"><span data-stu-id="cdca3-108">\<pnrpResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdca3-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cdca3-109">Syntax</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cdca3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cdca3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cdca3-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cdca3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cdca3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cdca3-112">Attributes</span></span>  
  
|<span data-ttu-id="cdca3-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cdca3-113">Attribute</span></span>|<span data-ttu-id="cdca3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cdca3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cdca3-115">resolverType</span><span class="sxs-lookup"><span data-stu-id="cdca3-115">resolverType</span></span>|<span data-ttu-id="cdca3-116">Строка, указывающая распознаватель для использования.</span><span class="sxs-lookup"><span data-stu-id="cdca3-116">A string that specifies the resolver to be used.</span></span> <span data-ttu-id="cdca3-117">Этот атрибут является необязательным.</span><span class="sxs-lookup"><span data-stu-id="cdca3-117">This attribute is optional.</span></span> <span data-ttu-id="cdca3-118">Если значение не задано или равно пустой строке, используется протокол PNRP.</span><span class="sxs-lookup"><span data-stu-id="cdca3-118">If it is not set, or if it is set to an empty string, PNRP is used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cdca3-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cdca3-119">Child Elements</span></span>  
 <span data-ttu-id="cdca3-120">Нет</span><span class="sxs-lookup"><span data-stu-id="cdca3-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cdca3-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cdca3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="cdca3-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="cdca3-122">Element</span></span>|<span data-ttu-id="cdca3-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="cdca3-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cdca3-124">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="cdca3-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="cdca3-125">Определяет все возможности пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="cdca3-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cdca3-126">Пример</span><span class="sxs-lookup"><span data-stu-id="cdca3-126">Example</span></span>  
  
```xml  
<pnrpResolver resolverType="String" />
```  
  
## <a name="see-also"></a><span data-ttu-id="cdca3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="cdca3-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>
- <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="cdca3-128">Привязки</span><span class="sxs-lookup"><span data-stu-id="cdca3-128">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="cdca3-129">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="cdca3-129">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="cdca3-130">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="cdca3-130">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="cdca3-131">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="cdca3-131">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="cdca3-132">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="cdca3-132">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
