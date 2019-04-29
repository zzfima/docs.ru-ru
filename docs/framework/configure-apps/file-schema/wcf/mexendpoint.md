---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 8fffcc05d5f53f719efce182083fbf103b1230ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772480"
---
# <a name="mexendpoint"></a><span data-ttu-id="ecd06-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="ecd06-101">\<mexEndpoint></span></span>
<span data-ttu-id="ecd06-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом IMetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="ecd06-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="ecd06-103">Поскольку все конечные точки обмена метаданными указывают IMetadataExchange в качестве своего контракта, можно использовать эту стандартную точку вместо определения собственной точки.</span><span class="sxs-lookup"><span data-stu-id="ecd06-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
 <span data-ttu-id="ecd06-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ecd06-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="ecd06-105">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="ecd06-105">\<standardEndpoints></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecd06-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ecd06-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ecd06-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ecd06-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ecd06-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ecd06-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ecd06-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ecd06-109">Attributes</span></span>  
  
|<span data-ttu-id="ecd06-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ecd06-110">Attribute</span></span>|<span data-ttu-id="ecd06-111">Описание</span><span class="sxs-lookup"><span data-stu-id="ecd06-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ecd06-112">имя</span><span class="sxs-lookup"><span data-stu-id="ecd06-112">name</span></span>|<span data-ttu-id="ecd06-113">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ecd06-113">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="ecd06-114">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="ecd06-114">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ecd06-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ecd06-115">Child Elements</span></span>  
 <span data-ttu-id="ecd06-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ecd06-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ecd06-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ecd06-117">Parent Elements</span></span>  
  
|<span data-ttu-id="ecd06-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="ecd06-118">Element</span></span>|<span data-ttu-id="ecd06-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ecd06-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ecd06-120">\<standardEndpoints ></span><span class="sxs-lookup"><span data-stu-id="ecd06-120">\<standardEndpoints></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|<span data-ttu-id="ecd06-121">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="ecd06-121">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
