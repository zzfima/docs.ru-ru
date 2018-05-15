---
title: '&lt;Настройка&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 19f960c14b6171557ec0f353dae34f26d7a7686c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcustomgt"></a><span data-ttu-id="974ce-102">&lt;Настройка&gt;</span><span class="sxs-lookup"><span data-stu-id="974ce-102">&lt;custom&gt;</span></span>
<span data-ttu-id="974ce-103">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="974ce-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="974ce-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="974ce-104">\<system.serviceModel></span></span>  
<span data-ttu-id="974ce-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="974ce-105">\<bindings></span></span>  
<span data-ttu-id="974ce-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="974ce-106">\<netPeerBinding></span></span>  
<span data-ttu-id="974ce-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="974ce-107">\<binding></span></span>  
<span data-ttu-id="974ce-108">\<Сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="974ce-108">\<resolver></span></span>  
<span data-ttu-id="974ce-109">\<пользовательские ></span><span class="sxs-lookup"><span data-stu-id="974ce-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="974ce-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="974ce-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="974ce-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="974ce-111">Attributes and Elements</span></span>  
 <span data-ttu-id="974ce-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="974ce-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="974ce-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="974ce-113">Attributes</span></span>  
  
|<span data-ttu-id="974ce-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="974ce-114">Attribute</span></span>|<span data-ttu-id="974ce-115">Описание</span><span class="sxs-lookup"><span data-stu-id="974ce-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="974ce-116">URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="974ce-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="974ce-117">Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="974ce-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="974ce-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="974ce-118">Child Elements</span></span>  
  
|<span data-ttu-id="974ce-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="974ce-119">Element</span></span>|<span data-ttu-id="974ce-120">Описание</span><span class="sxs-lookup"><span data-stu-id="974ce-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="974ce-121">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="974ce-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="974ce-122">Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="974ce-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="974ce-123">Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="974ce-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="974ce-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="974ce-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="974ce-125">Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="974ce-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="974ce-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="974ce-126">Parent Elements</span></span>  
  
|<span data-ttu-id="974ce-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="974ce-127">Element</span></span>|<span data-ttu-id="974ce-128">Описание</span><span class="sxs-lookup"><span data-stu-id="974ce-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="974ce-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="974ce-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="974ce-130">Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="974ce-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="974ce-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="974ce-131">Remarks</span></span>  
 <span data-ttu-id="974ce-132">Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки.</span><span class="sxs-lookup"><span data-stu-id="974ce-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="974ce-133">Дополнительные сведения о создании пользовательского арбитра конфликтов см. в разделе [Добавление пользовательского арбитра конфликтов в приложении PeerChannel](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="974ce-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974ce-134">См. также</span><span class="sxs-lookup"><span data-stu-id="974ce-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="974ce-135">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="974ce-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="974ce-136">Добавление пользовательского арбитра конфликтов в приложении PeerChannel</span><span class="sxs-lookup"><span data-stu-id="974ce-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](http://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
