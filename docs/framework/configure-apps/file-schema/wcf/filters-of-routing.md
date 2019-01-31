---
title: <filters> из <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 8b2c735a19c4cece16dcb77e3ec548eb2d39ec18
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272692"
---
# <a name="filters-of-routing"></a><span data-ttu-id="698bb-102">\<Фильтры > из \<маршрутизации ></span><span class="sxs-lookup"><span data-stu-id="698bb-102">\<filters> of \<routing></span></span>

<span data-ttu-id="698bb-103">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="698bb-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="698bb-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="698bb-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="698bb-105">&nbsp;&nbsp;[**\<Маршрутизация >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="698bb-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="698bb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Фильтры >**</span><span class="sxs-lookup"><span data-stu-id="698bb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="698bb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="698bb-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="698bb-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="698bb-108">Attributes and elements</span></span>

<span data-ttu-id="698bb-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="698bb-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="698bb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="698bb-110">Attributes</span></span>

<span data-ttu-id="698bb-111">Нет</span><span class="sxs-lookup"><span data-stu-id="698bb-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="698bb-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="698bb-112">Child elements</span></span>

|     | <span data-ttu-id="698bb-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="698bb-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="698bb-114">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="698bb-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="698bb-115">Содержит фильтр маршрутизации, который определяет тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> будет использоваться при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="698bb-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="698bb-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="698bb-116">Parent elements</span></span>

|     | <span data-ttu-id="698bb-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="698bb-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="698bb-118">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="698bb-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="698bb-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="698bb-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="698bb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="698bb-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
