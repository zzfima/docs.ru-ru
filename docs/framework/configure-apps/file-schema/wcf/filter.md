---
title: '&lt;Фильтр&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 93d47fc6b25a75eedae43cd70582abc863a74e6c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltergt"></a><span data-ttu-id="6f11d-102">&lt;Фильтр&gt;</span><span class="sxs-lookup"><span data-stu-id="6f11d-102">&lt;filter&gt;</span></span>

<span data-ttu-id="6f11d-103">Определяет фильтр маршрутизации, который определяет тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при вычислении входящих сообщений также все вспомогательные данные и параметры, необходимые для фильтра.</span><span class="sxs-lookup"><span data-stu-id="6f11d-103">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="6f11d-104">\<system.serviceModel > \<маршрутизации > \<фильтры > \<фильтра ></span><span class="sxs-lookup"><span data-stu-id="6f11d-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="6f11d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f11d-105">Syntax</span></span>

```xml
<routing>
  <filters>
    <filter customType="String" 
            filterData="String" 
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
            name="String" />
  </filters>
</routing>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6f11d-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="6f11d-106">Attributes and elements</span></span>

<span data-ttu-id="6f11d-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6f11d-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6f11d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6f11d-108">Attributes</span></span>

| <span data-ttu-id="6f11d-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6f11d-109">Attribute</span></span>  | <span data-ttu-id="6f11d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="6f11d-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="6f11d-111">customType</span><span class="sxs-lookup"><span data-stu-id="6f11d-111">customType</span></span> | <span data-ttu-id="6f11d-112">Строка, содержащая полное имя для пользовательского типа, используемого в качестве фильтра.</span><span class="sxs-lookup"><span data-stu-id="6f11d-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="6f11d-113">Если `filterType` равно `custom`, этот атрибут содержит имя класса, чтобы создать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="6f11d-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="6f11d-114">`filterData` также может содержать значения для использования во время вычисления фильтра пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="6f11d-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="6f11d-115">filterData</span><span class="sxs-lookup"><span data-stu-id="6f11d-115">filterData</span></span> | <span data-ttu-id="6f11d-116">Строка, содержащая данные фильтра.</span><span class="sxs-lookup"><span data-stu-id="6f11d-116">A string containing the filter data.</span></span> <span data-ttu-id="6f11d-117">Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f11d-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="6f11d-118">filterType</span><span class="sxs-lookup"><span data-stu-id="6f11d-118">filterType</span></span> | <span data-ttu-id="6f11d-119">Строка, содержащая тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="6f11d-119">A string containing the filter type.</span></span> <span data-ttu-id="6f11d-120">Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="6f11d-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="6f11d-121">Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f11d-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="6f11d-122">имя</span><span class="sxs-lookup"><span data-stu-id="6f11d-122">name</span></span>       | <span data-ttu-id="6f11d-123">Строка, содержащая уникальное имя этого элемента фильтра.</span><span class="sxs-lookup"><span data-stu-id="6f11d-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="6f11d-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6f11d-124">Child elements</span></span>

<span data-ttu-id="6f11d-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6f11d-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6f11d-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6f11d-126">Parent elements</span></span>

| <span data-ttu-id="6f11d-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="6f11d-127">Element</span></span> | <span data-ttu-id="6f11d-128">Описание</span><span class="sxs-lookup"><span data-stu-id="6f11d-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="6f11d-129">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="6f11d-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="6f11d-130">Раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="6f11d-130">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="6f11d-131">См. также</span><span class="sxs-lookup"><span data-stu-id="6f11d-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
