---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 78788f9dfbf6cdf3439fd6e33eddfe721e49840d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931260"
---
# <a name="mexendpoint"></a><span data-ttu-id="43632-101">\<Мексендпоинт ></span><span class="sxs-lookup"><span data-stu-id="43632-101">\<mexEndpoint></span></span>
<span data-ttu-id="43632-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом IMetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="43632-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="43632-103">Поскольку все конечные точки обмена метаданными указывают IMetadataExchange в качестве своего контракта, можно использовать эту стандартную точку вместо определения собственной точки.</span><span class="sxs-lookup"><span data-stu-id="43632-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="43632-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="43632-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="43632-105">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="43632-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43632-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43632-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43632-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="43632-107">Attributes and Elements</span></span>  
 <span data-ttu-id="43632-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="43632-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43632-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="43632-109">Attributes</span></span>  
  
|<span data-ttu-id="43632-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="43632-110">Attribute</span></span>|<span data-ttu-id="43632-111">Описание</span><span class="sxs-lookup"><span data-stu-id="43632-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43632-112">имя</span><span class="sxs-lookup"><span data-stu-id="43632-112">name</span></span>|<span data-ttu-id="43632-113">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="43632-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="43632-114">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="43632-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43632-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="43632-115">Child Elements</span></span>  
 <span data-ttu-id="43632-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="43632-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43632-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="43632-117">Parent Elements</span></span>  
  
|<span data-ttu-id="43632-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="43632-118">Element</span></span>|<span data-ttu-id="43632-119">Описание</span><span class="sxs-lookup"><span data-stu-id="43632-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43632-120">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="43632-120">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="43632-121">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="43632-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
