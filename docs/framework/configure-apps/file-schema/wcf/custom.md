---
title: '&lt;Custom&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 7d558be66b8a1e46d9743c5f8bf0bb9a8b4c349e
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838964"
---
# <a name="ltcustomgt"></a><span data-ttu-id="5d09f-102">&lt;Custom&gt;</span><span class="sxs-lookup"><span data-stu-id="5d09f-102">&lt;custom&gt;</span></span>
<span data-ttu-id="5d09f-103">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="5d09f-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="5d09f-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="5d09f-104">\<system.serviceModel></span></span>  
<span data-ttu-id="5d09f-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="5d09f-105">\<bindings></span></span>  
<span data-ttu-id="5d09f-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="5d09f-106">\<netPeerBinding></span></span>  
<span data-ttu-id="5d09f-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="5d09f-107">\<binding></span></span>  
<span data-ttu-id="5d09f-108">\<Сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="5d09f-108">\<resolver></span></span>  
<span data-ttu-id="5d09f-109">\<пользовательские ></span><span class="sxs-lookup"><span data-stu-id="5d09f-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d09f-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d09f-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d09f-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5d09f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5d09f-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5d09f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d09f-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5d09f-113">Attributes</span></span>  
  
|<span data-ttu-id="5d09f-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5d09f-114">Attribute</span></span>|<span data-ttu-id="5d09f-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5d09f-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="5d09f-116">URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="5d09f-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="5d09f-117">Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="5d09f-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d09f-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5d09f-118">Child Elements</span></span>  
  
|<span data-ttu-id="5d09f-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="5d09f-119">Element</span></span>|<span data-ttu-id="5d09f-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="5d09f-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d09f-121">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="5d09f-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="5d09f-122">Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="5d09f-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="5d09f-123">Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="5d09f-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="5d09f-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="5d09f-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="5d09f-125">Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="5d09f-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5d09f-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5d09f-126">Parent Elements</span></span>  
  
|<span data-ttu-id="5d09f-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="5d09f-127">Element</span></span>|<span data-ttu-id="5d09f-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="5d09f-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d09f-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="5d09f-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="5d09f-130">Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="5d09f-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d09f-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="5d09f-131">Remarks</span></span>  
 <span data-ttu-id="5d09f-132">Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки.</span><span class="sxs-lookup"><span data-stu-id="5d09f-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="5d09f-133">Дополнительные сведения о создании пользовательского распознавателя см. в разделе [Добавление в приложение PeerChannel пользовательского распознавателя](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="5d09f-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d09f-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5d09f-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="5d09f-135">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="5d09f-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="5d09f-136">Добавление в приложение PeerChannel пользовательского распознавателя</span><span class="sxs-lookup"><span data-stu-id="5d09f-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
