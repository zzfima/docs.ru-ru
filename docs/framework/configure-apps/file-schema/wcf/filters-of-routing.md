---
title: <filters> из <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: c9bc3a2c379e14d8cf687676a3ec40702d150e1e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855236"
---
# <a name="filters-of-routing"></a><span data-ttu-id="8ec3b-102">\<фильтрует > \<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="8ec3b-102">\<filters> of \<routing></span></span>

<span data-ttu-id="8ec3b-103">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="8ec3b-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="8ec3b-104">[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="8ec3b-104">[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="8ec3b-105">&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="8ec3b-105">&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="8ec3b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Фильтры >**</span><span class="sxs-lookup"><span data-stu-id="8ec3b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ec3b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ec3b-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ec3b-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="8ec3b-108">Attributes and elements</span></span>

<span data-ttu-id="8ec3b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8ec3b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8ec3b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8ec3b-110">Attributes</span></span>

<span data-ttu-id="8ec3b-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="8ec3b-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="8ec3b-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8ec3b-112">Child elements</span></span>

|     | <span data-ttu-id="8ec3b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8ec3b-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8ec3b-114"> **\<> фильтра**</span><span class="sxs-lookup"><span data-stu-id="8ec3b-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="8ec3b-115">Содержит фильтр маршрутизации, определяющий тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , который будет использоваться при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="8ec3b-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="8ec3b-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8ec3b-116">Parent elements</span></span>

|     | <span data-ttu-id="8ec3b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8ec3b-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8ec3b-118"> **\<> маршрутизации**</span><span class="sxs-lookup"><span data-stu-id="8ec3b-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="8ec3b-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки. Отправка сообщений в при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="8ec3b-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8ec3b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8ec3b-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
