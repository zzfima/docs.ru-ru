---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 6e78275aaeb202405e327302455d56fa431d7f27
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855256"
---
# <a name="filter"></a><span data-ttu-id="246ac-101">\<> фильтра</span><span class="sxs-lookup"><span data-stu-id="246ac-101">\<filter></span></span>

<span data-ttu-id="246ac-102">Определяет фильтр маршрутизации, определяющий тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , который будет использоваться при оценке входящих сообщений, а также любые вспомогательные данные или параметры, необходимые для фильтра.</span><span class="sxs-lookup"><span data-stu-id="246ac-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="246ac-103">[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="246ac-103">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="246ac-104">&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="246ac-104">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="246ac-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Фильтры >** ](filters-of-routing.md)</span><span class="sxs-lookup"><span data-stu-id="246ac-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<filters>**](filters-of-routing.md)</span></span>\
<span data-ttu-id="246ac-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> фильтра**</span><span class="sxs-lookup"><span data-stu-id="246ac-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="246ac-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="246ac-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="246ac-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="246ac-108">Attributes and elements</span></span>

<span data-ttu-id="246ac-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="246ac-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="246ac-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="246ac-110">Attributes</span></span>

| <span data-ttu-id="246ac-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="246ac-111">Attribute</span></span>  | <span data-ttu-id="246ac-112">Описание</span><span class="sxs-lookup"><span data-stu-id="246ac-112">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="246ac-113">customType</span><span class="sxs-lookup"><span data-stu-id="246ac-113">customType</span></span> | <span data-ttu-id="246ac-114">Строка, содержащая полное имя для пользовательского типа, используемого в качестве фильтра.</span><span class="sxs-lookup"><span data-stu-id="246ac-114">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="246ac-115">Если `filterType` параметр имеет `custom`значение, этот атрибут содержит полное имя типа создаваемого класса.</span><span class="sxs-lookup"><span data-stu-id="246ac-115">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="246ac-116">`filterData`может также содержать значения, используемые при вычислении настраиваемого фильтра типов.</span><span class="sxs-lookup"><span data-stu-id="246ac-116">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="246ac-117">filterData</span><span class="sxs-lookup"><span data-stu-id="246ac-117">filterData</span></span> | <span data-ttu-id="246ac-118">Строка, содержащая данные фильтра.</span><span class="sxs-lookup"><span data-stu-id="246ac-118">A string containing the filter data.</span></span> <span data-ttu-id="246ac-119">Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="246ac-119">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="246ac-120">filterType</span><span class="sxs-lookup"><span data-stu-id="246ac-120">filterType</span></span> | <span data-ttu-id="246ac-121">Строка, содержащая тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="246ac-121">A string containing the filter type.</span></span> <span data-ttu-id="246ac-122">Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="246ac-122">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="246ac-123">Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="246ac-123">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="246ac-124">имя</span><span class="sxs-lookup"><span data-stu-id="246ac-124">name</span></span>       | <span data-ttu-id="246ac-125">Строка, содержащая уникальное имя этого элемента фильтра.</span><span class="sxs-lookup"><span data-stu-id="246ac-125">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="246ac-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="246ac-126">Child elements</span></span>

<span data-ttu-id="246ac-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="246ac-127">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="246ac-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="246ac-128">Parent elements</span></span>

| <span data-ttu-id="246ac-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="246ac-129">Element</span></span> | <span data-ttu-id="246ac-130">Описание</span><span class="sxs-lookup"><span data-stu-id="246ac-130">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="246ac-131">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="246ac-131">\<routing></span></span>](routing.md) | <span data-ttu-id="246ac-132">Раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="246ac-132">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="246ac-133">См. также</span><span class="sxs-lookup"><span data-stu-id="246ac-133">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
