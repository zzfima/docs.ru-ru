---
title: '&lt;filters&gt; для &lt;routing&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 9f0fa9bf51d264346738172f57a8efca7950fdb7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="5f264-102">&lt;filters&gt; для &lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="5f264-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="5f264-103">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="5f264-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="5f264-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="5f264-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="5f264-105">&nbsp;&nbsp;[**\<Маршрутизация >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="5f264-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="5f264-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Фильтры >**</span><span class="sxs-lookup"><span data-stu-id="5f264-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5f264-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f264-107">Syntax</span></span>

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

## <a name="attributes-and-elements"></a><span data-ttu-id="5f264-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="5f264-108">Attributes and elements</span></span>

<span data-ttu-id="5f264-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5f264-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="5f264-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5f264-110">Attributes</span></span>

<span data-ttu-id="5f264-111">Нет</span><span class="sxs-lookup"><span data-stu-id="5f264-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="5f264-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5f264-112">Child elements</span></span>

|     | <span data-ttu-id="5f264-113">Описание</span><span class="sxs-lookup"><span data-stu-id="5f264-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5f264-114">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="5f264-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="5f264-115">Содержит фильтр маршрутизации, который определяет тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> будет использоваться при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="5f264-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="5f264-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5f264-116">Parent elements</span></span>

|     | <span data-ttu-id="5f264-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5f264-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5f264-118">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="5f264-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="5f264-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизацию таблиц, определяющих целевые конечные точки для Отправка сообщений при соответствии критериям фильтра.</span><span class="sxs-lookup"><span data-stu-id="5f264-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="5f264-120">См. также</span><span class="sxs-lookup"><span data-stu-id="5f264-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
