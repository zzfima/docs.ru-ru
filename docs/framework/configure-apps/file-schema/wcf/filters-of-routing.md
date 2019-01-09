---
title: '&lt;filters&gt; для &lt;routing&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 4a6a079264c54ac481c3a8996b74ac924c33bdc7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150894"
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="6a10d-102">&lt;filters&gt; для &lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="6a10d-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="6a10d-103">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="6a10d-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="6a10d-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="6a10d-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="6a10d-105">&nbsp;&nbsp;[**\<Маршрутизация >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="6a10d-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="6a10d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Фильтры >**</span><span class="sxs-lookup"><span data-stu-id="6a10d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="6a10d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a10d-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a10d-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="6a10d-108">Attributes and elements</span></span>

<span data-ttu-id="6a10d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6a10d-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6a10d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6a10d-110">Attributes</span></span>

<span data-ttu-id="6a10d-111">Нет</span><span class="sxs-lookup"><span data-stu-id="6a10d-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="6a10d-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6a10d-112">Child elements</span></span>

|     | <span data-ttu-id="6a10d-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="6a10d-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6a10d-114">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="6a10d-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="6a10d-115">Содержит фильтр маршрутизации, который определяет тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> будет использоваться при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="6a10d-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="6a10d-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6a10d-116">Parent elements</span></span>

|     | <span data-ttu-id="6a10d-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="6a10d-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="6a10d-118">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="6a10d-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="6a10d-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="6a10d-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="6a10d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6a10d-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
