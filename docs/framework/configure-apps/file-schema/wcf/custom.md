---
title: '&lt;Custom&gt;'
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 7d558be66b8a1e46d9743c5f8bf0bb9a8b4c349e
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266999"
---
# <a name="ltcustomgt"></a><span data-ttu-id="ceda1-102">&lt;Custom&gt;</span><span class="sxs-lookup"><span data-stu-id="ceda1-102">&lt;custom&gt;</span></span>
<span data-ttu-id="ceda1-103">Задает параметры службы пользовательского распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="ceda1-103">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="ceda1-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ceda1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ceda1-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="ceda1-105">\<bindings></span></span>  
<span data-ttu-id="ceda1-106">\<netPeerBinding ></span><span class="sxs-lookup"><span data-stu-id="ceda1-106">\<netPeerBinding></span></span>  
<span data-ttu-id="ceda1-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="ceda1-107">\<binding></span></span>  
<span data-ttu-id="ceda1-108">\<Сопоставитель ></span><span class="sxs-lookup"><span data-stu-id="ceda1-108">\<resolver></span></span>  
<span data-ttu-id="ceda1-109">\<пользовательские ></span><span class="sxs-lookup"><span data-stu-id="ceda1-109">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceda1-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ceda1-110">Syntax</span></span>  
  
```xml
<custom address="Uri" 
        resolverType="String">  
  <headers/>  
  <identity/>  
</custom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ceda1-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ceda1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ceda1-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ceda1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ceda1-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ceda1-113">Attributes</span></span>  
  
|<span data-ttu-id="ceda1-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ceda1-114">Attribute</span></span>|<span data-ttu-id="ceda1-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ceda1-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="ceda1-116">URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="ceda1-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="ceda1-117">Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="ceda1-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ceda1-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ceda1-118">Child Elements</span></span>  
  
|<span data-ttu-id="ceda1-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="ceda1-119">Element</span></span>|<span data-ttu-id="ceda1-120">Описание</span><span class="sxs-lookup"><span data-stu-id="ceda1-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ceda1-121">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="ceda1-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="ceda1-122">Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента.</span><span class="sxs-lookup"><span data-stu-id="ceda1-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="ceda1-123">Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.</span><span class="sxs-lookup"><span data-stu-id="ceda1-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="ceda1-124">\<заголовки ></span><span class="sxs-lookup"><span data-stu-id="ceda1-124">\<headers></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|<span data-ttu-id="ceda1-125">Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.</span><span class="sxs-lookup"><span data-stu-id="ceda1-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ceda1-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ceda1-126">Parent Elements</span></span>  
  
|<span data-ttu-id="ceda1-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="ceda1-127">Element</span></span>|<span data-ttu-id="ceda1-128">Описание</span><span class="sxs-lookup"><span data-stu-id="ceda1-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ceda1-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="ceda1-129">\<resolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|<span data-ttu-id="ceda1-130">Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.</span><span class="sxs-lookup"><span data-stu-id="ceda1-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ceda1-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="ceda1-131">Remarks</span></span>  
 <span data-ttu-id="ceda1-132">Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки.</span><span class="sxs-lookup"><span data-stu-id="ceda1-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="ceda1-133">Дополнительные сведения о создании пользовательского распознавателя см. в разделе [Добавление в приложение PeerChannel пользовательского распознавателя](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span><span class="sxs-lookup"><span data-stu-id="ceda1-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceda1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="ceda1-134">See Also</span></span>  
 <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>  
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>  
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>  
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>  
 [<span data-ttu-id="ceda1-135">Одноранговые распознаватели</span><span class="sxs-lookup"><span data-stu-id="ceda1-135">Peer Resolvers</span></span>](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)  
 [<span data-ttu-id="ceda1-136">Добавление в приложение PeerChannel пользовательского распознавателя</span><span class="sxs-lookup"><span data-stu-id="ceda1-136">Adding a Custom Resolver to a PeerChannel Application</span></span>](https://msdn.microsoft.com/library/12aa3787-2962-439c-ad27-46523c8b0419)
