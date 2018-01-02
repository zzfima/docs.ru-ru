---
title: "&lt;пользовательские&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bcab1e8361448abfe14db8ac38a924c656b9065
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomgt"></a><span data-ttu-id="f0b59-102">&lt;пользовательские&gt;</span><span class="sxs-lookup"><span data-stu-id="f0b59-102">&lt;custom&gt;</span></span>
<span data-ttu-id="f0b59-103">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="f0b59-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="f0b59-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="f0b59-104">\<system.serviceModel></span></span>  
<span data-ttu-id="f0b59-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="f0b59-105">\<bindings></span></span>  
<span data-ttu-id="f0b59-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="f0b59-106">\<netPeerBinding></span></span>  
<span data-ttu-id="f0b59-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="f0b59-107">\<binding></span></span>  
<span data-ttu-id="f0b59-108">\<Сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="f0b59-108">\<resolver></span></span>  
<span data-ttu-id="f0b59-109">\<пользовательские ></span><span class="sxs-lookup"><span data-stu-id="f0b59-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0b59-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0b59-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f0b59-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f0b59-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f0b59-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f0b59-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f0b59-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f0b59-113">Attributes</span></span>  
  
|<span data-ttu-id="f0b59-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f0b59-114">Attribute</span></span>|<span data-ttu-id="f0b59-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f0b59-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="f0b59-116">URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="f0b59-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="f0b59-117">Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="f0b59-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f0b59-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f0b59-118">Child Elements</span></span>  
  
|<span data-ttu-id="f0b59-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="f0b59-119">Element</span></span>|<span data-ttu-id="f0b59-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="f0b59-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0b59-121">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="f0b59-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f0b59-122">Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="f0b59-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="f0b59-123">Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="f0b59-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="f0b59-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="f0b59-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="f0b59-125">Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="f0b59-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f0b59-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f0b59-126">Parent Elements</span></span>  
  
|<span data-ttu-id="f0b59-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="f0b59-127">Element</span></span>|<span data-ttu-id="f0b59-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="f0b59-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f0b59-129">\<Сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="f0b59-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="f0b59-130">Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="f0b59-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0b59-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0b59-131">Remarks</span></span>  
 <span data-ttu-id="f0b59-132">Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки.</span><span class="sxs-lookup"><span data-stu-id="f0b59-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="f0b59-133">Дополнительные сведения о создании пользовательского арбитра конфликтов см. в разделе [Добавление пользовательского арбитра конфликтов в приложении PeerChannel](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="f0b59-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0b59-134">См. также</span><span class="sxs-lookup"><span data-stu-id="f0b59-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="f0b59-135">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="f0b59-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="f0b59-136">Добавление пользовательского арбитра конфликтов в приложении PeerChannel</span><span class="sxs-lookup"><span data-stu-id="f0b59-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
