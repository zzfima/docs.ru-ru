---
title: <filters> из <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: ba60958ad33b46b40285f3f70001273bb3af3a63
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925617"
---
# <a name="filters-of-routing"></a><span data-ttu-id="1a255-102">\<фильтрует > \<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1a255-102">\<filters> of \<routing></span></span>

<span data-ttu-id="1a255-103">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="1a255-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="1a255-104">[ **\<> System. serviceModel**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="1a255-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="1a255-105">&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="1a255-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="1a255-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Фильтры >**</span><span class="sxs-lookup"><span data-stu-id="1a255-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="1a255-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1a255-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a255-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="1a255-108">Attributes and elements</span></span>

<span data-ttu-id="1a255-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1a255-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="1a255-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1a255-110">Attributes</span></span>

<span data-ttu-id="1a255-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="1a255-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="1a255-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1a255-112">Child elements</span></span>

|     | <span data-ttu-id="1a255-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1a255-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1a255-114"> **\<> фильтра**</span><span class="sxs-lookup"><span data-stu-id="1a255-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="1a255-115">Содержит фильтр маршрутизации, определяющий тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , который будет использоваться при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="1a255-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="1a255-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1a255-116">Parent elements</span></span>

|     | <span data-ttu-id="1a255-117">Описание</span><span class="sxs-lookup"><span data-stu-id="1a255-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1a255-118"> **\<> маршрутизации**</span><span class="sxs-lookup"><span data-stu-id="1a255-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="1a255-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки. Отправка сообщений в при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="1a255-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="1a255-120">См. также</span><span class="sxs-lookup"><span data-stu-id="1a255-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
