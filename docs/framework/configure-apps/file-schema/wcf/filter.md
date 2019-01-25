---
title: '&lt;Фильтр&gt;'
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 9fae9a599299fdd8cf1e996593514fc0ef38b6ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645513"
---
# <a name="ltfiltergt"></a><span data-ttu-id="21f17-102">&lt;Фильтр&gt;</span><span class="sxs-lookup"><span data-stu-id="21f17-102">&lt;filter&gt;</span></span>

<span data-ttu-id="21f17-103">Определяет фильтр маршрутизации, который определяет тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений также все вспомогательные данные и параметры, необходимые для фильтра.</span><span class="sxs-lookup"><span data-stu-id="21f17-103">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="21f17-104">\<system.serviceModel> \<routing> \<filters> \<filter></span><span class="sxs-lookup"><span data-stu-id="21f17-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="21f17-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="21f17-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21f17-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="21f17-106">Attributes and elements</span></span>

<span data-ttu-id="21f17-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="21f17-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="21f17-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="21f17-108">Attributes</span></span>

| <span data-ttu-id="21f17-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="21f17-109">Attribute</span></span>  | <span data-ttu-id="21f17-110">Описание</span><span class="sxs-lookup"><span data-stu-id="21f17-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="21f17-111">customType</span><span class="sxs-lookup"><span data-stu-id="21f17-111">customType</span></span> | <span data-ttu-id="21f17-112">Строка, содержащая полное имя для пользовательского типа, используемого в качестве фильтра.</span><span class="sxs-lookup"><span data-stu-id="21f17-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="21f17-113">Если `filterType` присваивается `custom`, этот атрибут содержит имя полное имя типа создаваемого класса.</span><span class="sxs-lookup"><span data-stu-id="21f17-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="21f17-114">`filterData` также может содержать значения, используемые при оценке фильтра с пользовательским типом.</span><span class="sxs-lookup"><span data-stu-id="21f17-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="21f17-115">filterData</span><span class="sxs-lookup"><span data-stu-id="21f17-115">filterData</span></span> | <span data-ttu-id="21f17-116">Строка, содержащая данные фильтра.</span><span class="sxs-lookup"><span data-stu-id="21f17-116">A string containing the filter data.</span></span> <span data-ttu-id="21f17-117">Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="21f17-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="21f17-118">filterType</span><span class="sxs-lookup"><span data-stu-id="21f17-118">filterType</span></span> | <span data-ttu-id="21f17-119">Строка, содержащая тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="21f17-119">A string containing the filter type.</span></span> <span data-ttu-id="21f17-120">Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="21f17-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="21f17-121">Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="21f17-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="21f17-122">имя</span><span class="sxs-lookup"><span data-stu-id="21f17-122">name</span></span>       | <span data-ttu-id="21f17-123">Строка, содержащая уникальное имя этого элемента фильтра.</span><span class="sxs-lookup"><span data-stu-id="21f17-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="21f17-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="21f17-124">Child elements</span></span>

<span data-ttu-id="21f17-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="21f17-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="21f17-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="21f17-126">Parent elements</span></span>

| <span data-ttu-id="21f17-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="21f17-127">Element</span></span> | <span data-ttu-id="21f17-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="21f17-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="21f17-129">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="21f17-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="21f17-130">Раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="21f17-130">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="21f17-131">См. также</span><span class="sxs-lookup"><span data-stu-id="21f17-131">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
