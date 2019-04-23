---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 18359e871feed17a11006d0b2998907faf25c158
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106591"
---
# <a name="custom"></a><span data-ttu-id="db93b-101">\<пользовательские ></span><span class="sxs-lookup"><span data-stu-id="db93b-101">\<custom></span></span>
<span data-ttu-id="db93b-102">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="db93b-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="db93b-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="db93b-103">\<system.serviceModel></span></span>  
<span data-ttu-id="db93b-104">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="db93b-104">\<bindings></span></span>  
<span data-ttu-id="db93b-105">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="db93b-105">\<netPeerBinding></span></span>  
<span data-ttu-id="db93b-106">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="db93b-106">\<binding></span></span>  
<span data-ttu-id="db93b-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="db93b-107">\<resolver></span></span>  
<span data-ttu-id="db93b-108">\<пользовательские ></span><span class="sxs-lookup"><span data-stu-id="db93b-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db93b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db93b-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db93b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="db93b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="db93b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="db93b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db93b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="db93b-112">Attributes</span></span>  
  
|<span data-ttu-id="db93b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="db93b-113">Attribute</span></span>|<span data-ttu-id="db93b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="db93b-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="db93b-115">URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="db93b-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="db93b-116">Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="db93b-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db93b-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="db93b-117">Child Elements</span></span>  
  
|<span data-ttu-id="db93b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="db93b-118">Element</span></span>|<span data-ttu-id="db93b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="db93b-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db93b-120">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="db93b-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="db93b-121">Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="db93b-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="db93b-122">Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="db93b-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="db93b-123">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="db93b-123">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="db93b-124">Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="db93b-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="db93b-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="db93b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="db93b-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="db93b-126">Element</span></span>|<span data-ttu-id="db93b-127">Описание</span><span class="sxs-lookup"><span data-stu-id="db93b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="db93b-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="db93b-128">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="db93b-129">Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="db93b-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db93b-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="db93b-130">Remarks</span></span>  
 <span data-ttu-id="db93b-131">Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки.</span><span class="sxs-lookup"><span data-stu-id="db93b-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="db93b-132">Дополнительные сведения о создании пользовательского распознавателя см. в разделе [Добавление в приложение PeerChannel пользовательского распознавателя](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="db93b-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db93b-133">См. также</span><span class="sxs-lookup"><span data-stu-id="db93b-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="db93b-134">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="db93b-134">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="db93b-135">[Добавление в приложение PeerChannel пользовательского распознавателя](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="db93b-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
