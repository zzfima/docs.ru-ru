---
title: "&lt;Фильтр&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 186c511cd8a69cef5e30e369641628a10a0972d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltergt"></a><span data-ttu-id="d932f-102">&lt;Фильтр&gt;</span><span class="sxs-lookup"><span data-stu-id="d932f-102">&lt;filter&gt;</span></span>

<span data-ttu-id="d932f-103">Задает фильтр маршрутизации, который определяет тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при оценке входящих сообщений, а также все требуемые фильтру сопутствующие данные или параметры.</span><span class="sxs-lookup"><span data-stu-id="d932f-103">Defines a routing filter, which determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well any supporting data or parameters required by the filter.</span></span>

<span data-ttu-id="d932f-104">\<system.serviceModel > \<маршрутизации > \<фильтры > \<фильтра ></span><span class="sxs-lookup"><span data-stu-id="d932f-104">\<system.serviceModel> \<routing> \<filters> \<filter></span></span>

## <a name="syntax"></a><span data-ttu-id="d932f-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d932f-105">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="d932f-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="d932f-106">Attributes and elements</span></span>

<span data-ttu-id="d932f-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d932f-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d932f-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d932f-108">Attributes</span></span>

| <span data-ttu-id="d932f-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d932f-109">Attribute</span></span>  | <span data-ttu-id="d932f-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d932f-110">Description</span></span> |
| ---------- | ----------- |
| <span data-ttu-id="d932f-111">customType</span><span class="sxs-lookup"><span data-stu-id="d932f-111">customType</span></span> | <span data-ttu-id="d932f-112">Строка, содержащая полное имя для пользовательского типа, используемого в качестве фильтра.</span><span class="sxs-lookup"><span data-stu-id="d932f-112">A string containing the fully qualified type name of the custom type to be used as a filter.</span></span> <span data-ttu-id="d932f-113">Если `filterType` равно `custom`, этот атрибут содержит имя класса, чтобы создать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="d932f-113">If `filterType` is set to `custom`, this attribute contains the fully qualified type name of the class to create.</span></span>  <span data-ttu-id="d932f-114">`filterData`также может содержать значения для использования во время вычисления фильтра пользовательского типа.</span><span class="sxs-lookup"><span data-stu-id="d932f-114">`filterData` may also contain values to be used during evaluation of the custom type filter.</span></span> |
| <span data-ttu-id="d932f-115">filterData</span><span class="sxs-lookup"><span data-stu-id="d932f-115">filterData</span></span> | <span data-ttu-id="d932f-116">Строка, содержащая данные фильтра.</span><span class="sxs-lookup"><span data-stu-id="d932f-116">A string containing the filter data.</span></span> <span data-ttu-id="d932f-117">Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d932f-117">For more information on how to specify this attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="d932f-118">filterType</span><span class="sxs-lookup"><span data-stu-id="d932f-118">filterType</span></span> | <span data-ttu-id="d932f-119">Строка, содержащая тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="d932f-119">A string containing the filter type.</span></span> <span data-ttu-id="d932f-120">Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.</span><span class="sxs-lookup"><span data-stu-id="d932f-120">This attribute is of <xref:System.ServiceModel.Routing.Configuration.FilterType> type.</span></span>  <span data-ttu-id="d932f-121">Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span><span class="sxs-lookup"><span data-stu-id="d932f-121">For more information on how this works with the `filterData` attribute, see <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.</span></span> |
| <span data-ttu-id="d932f-122">имя</span><span class="sxs-lookup"><span data-stu-id="d932f-122">name</span></span>       | <span data-ttu-id="d932f-123">Строка, содержащая уникальное имя этого элемента фильтра.</span><span class="sxs-lookup"><span data-stu-id="d932f-123">A string containing the unique name of this filter element.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="d932f-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d932f-124">Child elements</span></span>

<span data-ttu-id="d932f-125">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d932f-125">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d932f-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d932f-126">Parent elements</span></span>

| <span data-ttu-id="d932f-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="d932f-127">Element</span></span> | <span data-ttu-id="d932f-128">Описание:</span><span class="sxs-lookup"><span data-stu-id="d932f-128">Description</span></span> |
| ------- | ----------- |
| [<span data-ttu-id="d932f-129">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="d932f-129">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="d932f-130">Раздел конфигурации, в котором определяется набор фильтров маршрутизации, которые определяют тип [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="d932f-130">A configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span> |

## <a name="see-also"></a><span data-ttu-id="d932f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d932f-131">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
