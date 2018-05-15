---
title: '&lt;mexEndpoint&gt;'
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: aceff3e373d9a5f7e57c28d85870af19ae8ef3e1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="5d8e9-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="5d8e9-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="5d8e9-103">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом IMetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="5d8e9-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="5d8e9-104">Поскольку все конечные точки обмена метаданными указывают IMetadataExchange в качестве своего контракта, можно использовать эту стандартную точку вместо определения собственной точки.</span><span class="sxs-lookup"><span data-stu-id="5d8e9-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="5d8e9-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5d8e9-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="5d8e9-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="5d8e9-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d8e9-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d8e9-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d8e9-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5d8e9-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5d8e9-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5d8e9-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d8e9-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5d8e9-110">Attributes</span></span>  
  
|<span data-ttu-id="5d8e9-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5d8e9-111">Attribute</span></span>|<span data-ttu-id="5d8e9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="5d8e9-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d8e9-113">имя</span><span class="sxs-lookup"><span data-stu-id="5d8e9-113">name</span></span>|<span data-ttu-id="5d8e9-114">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5d8e9-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="5d8e9-115">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="5d8e9-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d8e9-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5d8e9-116">Child Elements</span></span>  
 <span data-ttu-id="5d8e9-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5d8e9-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d8e9-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5d8e9-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5d8e9-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="5d8e9-119">Element</span></span>|<span data-ttu-id="5d8e9-120">Описание</span><span class="sxs-lookup"><span data-stu-id="5d8e9-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d8e9-121">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="5d8e9-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="5d8e9-122">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="5d8e9-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
