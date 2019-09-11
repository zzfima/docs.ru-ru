---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855108"
---
# <a name="mexendpoint"></a><span data-ttu-id="fda1f-101">\<Мексендпоинт ></span><span class="sxs-lookup"><span data-stu-id="fda1f-101">\<mexEndpoint></span></span>
<span data-ttu-id="fda1f-102">Этот элемент конфигурации определяет стандартную конечную точку с фиксированным контрактом IMetadataExchange.</span><span class="sxs-lookup"><span data-stu-id="fda1f-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="fda1f-103">Поскольку все конечные точки обмена метаданными указывают IMetadataExchange в качестве своего контракта, можно использовать эту стандартную точку вместо определения собственной точки.</span><span class="sxs-lookup"><span data-stu-id="fda1f-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
<span data-ttu-id="fda1f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fda1f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fda1f-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fda1f-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fda1f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Стандардендпоинтс >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="fda1f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="fda1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Мексендпоинт >**</span><span class="sxs-lookup"><span data-stu-id="fda1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fda1f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fda1f-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fda1f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fda1f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fda1f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fda1f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fda1f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fda1f-111">Attributes</span></span>  
  
|<span data-ttu-id="fda1f-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fda1f-112">Attribute</span></span>|<span data-ttu-id="fda1f-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fda1f-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fda1f-114">имя</span><span class="sxs-lookup"><span data-stu-id="fda1f-114">name</span></span>|<span data-ttu-id="fda1f-115">Строка, указывающая имя конфигурации стандартной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fda1f-115">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="fda1f-116">Это имя используется в атрибуте `endpointConfiguration` конечной точки службы для связывания стандартной конечной точки с ее конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="fda1f-116">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fda1f-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fda1f-117">Child Elements</span></span>  
 <span data-ttu-id="fda1f-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="fda1f-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fda1f-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fda1f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="fda1f-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="fda1f-120">Element</span></span>|<span data-ttu-id="fda1f-121">Описание</span><span class="sxs-lookup"><span data-stu-id="fda1f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fda1f-122">\<Стандардендпоинтс ></span><span class="sxs-lookup"><span data-stu-id="fda1f-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="fda1f-123">Коллекция стандартных конечных точек, одно или несколько свойств которых (адрес, привязка, контракт) являются фиксированными.</span><span class="sxs-lookup"><span data-stu-id="fda1f-123">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
