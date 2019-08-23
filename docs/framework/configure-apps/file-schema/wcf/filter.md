---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 68de255b9f11dc4377159d1cc3efa575633db316
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918894"
---
# <a name="filter"></a><span data-ttu-id="7030a-101">\<> фильтра</span><span class="sxs-lookup"><span data-stu-id="7030a-101">\<filter></span></span>

<span data-ttu-id="7030a-102">Определяет фильтр маршрутизации, определяющий тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , который будет использоваться при оценке входящих сообщений, а также любые вспомогательные данные или параметры, необходимые для фильтра.</span><span class="sxs-lookup"><span data-stu-id="7030a-102">Defines a routing filter, which determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="7030a-103">\<\<> \< фильтровмаршрутизации>System.\<ServiceModel > фильтров ></span><span class="sxs-lookup"><span data-stu-id="7030a-103">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>
  
## <a name="syntax"></a><span data-ttu-id="7030a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7030a-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7030a-105">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="7030a-105">Attributes and elements</span></span>

<span data-ttu-id="7030a-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7030a-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7030a-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7030a-107">Attributes</span></span>

| <span data-ttu-id="7030a-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7030a-108">Attribute</span></span>  | <span data-ttu-id="7030a-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7030a-109">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="7030a-110">customType</span><span class="sxs-lookup"><span data-stu-id="7030a-110">customType</span></span> | <span data-ttu-id="7030a-111">Строка, содержащая полное имя для пользовательского типа, используемого в качестве фильтра.</span><span class="sxs-lookup"><span data-stu-id="7030a-111">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="7030a-112">Если `filterType` параметр имеет `custom`значение, этот атрибут содержит полное имя типа создаваемого класса.</span><span class="sxs-lookup"><span data-stu-id="7030a-112">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="7030a-113">`filterData`может также содержать значения, используемые при вычислении настраиваемого фильтра типов.</span><span class="sxs-lookup"><span data-stu-id="7030a-113">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="7030a-114">filterData</span><span class="sxs-lookup"><span data-stu-id="7030a-114">filterData</span></span> | <span data-ttu-id="7030a-115">Строка, содержащая данные фильтра.</span><span class="sxs-lookup"><span data-stu-id="7030a-115">A string containing the filter data.</span></span> <span data-ttu-id="7030a-116">Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="7030a-116">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="7030a-117">filterType</span><span class="sxs-lookup"><span data-stu-id="7030a-117">filterType</span></span> | <span data-ttu-id="7030a-118">Строка, содержащая тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="7030a-118">A string containing the filter type.</span></span> <span data-ttu-id="7030a-119">Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="7030a-119">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="7030a-120">Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="7030a-120">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="7030a-121">имя</span><span class="sxs-lookup"><span data-stu-id="7030a-121">name</span></span>       | <span data-ttu-id="7030a-122">Строка, содержащая уникальное имя этого элемента фильтра.</span><span class="sxs-lookup"><span data-stu-id="7030a-122">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="7030a-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7030a-123">Child elements</span></span>

<span data-ttu-id="7030a-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="7030a-124">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7030a-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7030a-125">Parent elements</span></span>

| <span data-ttu-id="7030a-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="7030a-126">Element</span></span> | <span data-ttu-id="7030a-127">Описание</span><span class="sxs-lookup"><span data-stu-id="7030a-127">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="7030a-128">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="7030a-128">\<routing></span></span>](routing.md) | <span data-ttu-id="7030a-129">Раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="7030a-129">A configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="7030a-130">См. также</span><span class="sxs-lookup"><span data-stu-id="7030a-130">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
