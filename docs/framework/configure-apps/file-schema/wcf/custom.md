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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5bccfc95313ae3ae4a692be2165dc694783a460e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltcustomgt"></a><span data-ttu-id="eac9c-102">&lt;пользовательские&gt;</span><span class="sxs-lookup"><span data-stu-id="eac9c-102">&lt;custom&gt;</span></span>
<span data-ttu-id="eac9c-103">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="eac9c-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="eac9c-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="eac9c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="eac9c-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="eac9c-105">\<bindings></span></span>  
<span data-ttu-id="eac9c-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="eac9c-106">\<netPeerBinding></span></span>  
<span data-ttu-id="eac9c-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="eac9c-107">\<binding></span></span>  
<span data-ttu-id="eac9c-108">\<Сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="eac9c-108">\<resolver></span></span>  
<span data-ttu-id="eac9c-109">\<пользовательские ></span><span class="sxs-lookup"><span data-stu-id="eac9c-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eac9c-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eac9c-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eac9c-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eac9c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="eac9c-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eac9c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eac9c-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eac9c-113">Attributes</span></span>  
  
|<span data-ttu-id="eac9c-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eac9c-114">Attribute</span></span>|<span data-ttu-id="eac9c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="eac9c-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="eac9c-116">URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="eac9c-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="eac9c-117">Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="eac9c-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eac9c-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eac9c-118">Child Elements</span></span>  
  
|<span data-ttu-id="eac9c-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="eac9c-119">Element</span></span>|<span data-ttu-id="eac9c-120">Описание</span><span class="sxs-lookup"><span data-stu-id="eac9c-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eac9c-121">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="eac9c-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="eac9c-122">Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="eac9c-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="eac9c-123">Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="eac9c-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="eac9c-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="eac9c-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="eac9c-125">Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="eac9c-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eac9c-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eac9c-126">Parent Elements</span></span>  
  
|<span data-ttu-id="eac9c-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="eac9c-127">Element</span></span>|<span data-ttu-id="eac9c-128">Описание</span><span class="sxs-lookup"><span data-stu-id="eac9c-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eac9c-129">\<Сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="eac9c-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="eac9c-130">Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="eac9c-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eac9c-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="eac9c-131">Remarks</span></span>  
 <span data-ttu-id="eac9c-132">Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки.</span><span class="sxs-lookup"><span data-stu-id="eac9c-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="eac9c-133">Дополнительные сведения о создании пользовательского арбитра конфликтов см. в разделе [Добавление пользовательского арбитра конфликтов в приложении PeerChannel](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="eac9c-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eac9c-134">См. также</span><span class="sxs-lookup"><span data-stu-id="eac9c-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="eac9c-135">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="eac9c-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="eac9c-136">Добавление пользовательского арбитра конфликтов в приложении PeerChannel</span><span class="sxs-lookup"><span data-stu-id="eac9c-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/en-us/12aa3787-2962-439c-ad27-46523c8b0419)
