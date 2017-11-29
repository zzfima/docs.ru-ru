---
title: '&lt;mexEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75886c08d3e358d4ed6d3d3048594ef28f06a7af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltmexendpointgt"></a><span data-ttu-id="882b4-102">&lt;mexEndpoint&gt;</span><span class="sxs-lookup"><span data-stu-id="882b4-102">&lt;mexEndpoint&gt;</span></span>
<span data-ttu-id="882b4-103">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом IMetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="882b4-103">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="882b4-104">Поскольку все конечные точки обмена метаданными указывают IMetadataExchange в качестве своего контракта, можно использовать эту стандартную точку вместо определения собственной точки.</span><span class="sxs-lookup"><span data-stu-id="882b4-104">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="882b4-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="882b4-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="882b4-106">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="882b4-106">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="882b4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="882b4-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="882b4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="882b4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="882b4-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="882b4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="882b4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="882b4-110">Attributes</span></span>  
  
|<span data-ttu-id="882b4-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="882b4-111">Attribute</span></span>|<span data-ttu-id="882b4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="882b4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="882b4-113">имя</span><span class="sxs-lookup"><span data-stu-id="882b4-113">name</span></span>|<span data-ttu-id="882b4-114">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="882b4-114">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="882b4-115">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="882b4-115">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="882b4-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="882b4-116">Child Elements</span></span>  
 <span data-ttu-id="882b4-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="882b4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="882b4-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="882b4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="882b4-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="882b4-119">Element</span></span>|<span data-ttu-id="882b4-120">Описание</span><span class="sxs-lookup"><span data-stu-id="882b4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="882b4-121">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="882b4-121">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="882b4-122">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="882b4-122">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
