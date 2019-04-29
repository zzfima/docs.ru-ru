---
title: <filters> из <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 8b2c735a19c4cece16dcb77e3ec548eb2d39ec18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701038"
---
# <a name="filters-of-routing"></a><span data-ttu-id="c860a-102">\<Фильтры > из \<маршрутизации ></span><span class="sxs-lookup"><span data-stu-id="c860a-102">\<filters> of \<routing></span></span>

<span data-ttu-id="c860a-103">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="c860a-103">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="c860a-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="c860a-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="c860a-105">&nbsp;&nbsp;[**\<Маршрутизация >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="c860a-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="c860a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Фильтры >**</span><span class="sxs-lookup"><span data-stu-id="c860a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c860a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c860a-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c860a-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="c860a-108">Attributes and elements</span></span>

<span data-ttu-id="c860a-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c860a-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c860a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c860a-110">Attributes</span></span>

<span data-ttu-id="c860a-111">Нет</span><span class="sxs-lookup"><span data-stu-id="c860a-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c860a-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c860a-112">Child elements</span></span>

|     | <span data-ttu-id="c860a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c860a-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c860a-114">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="c860a-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="c860a-115">Содержит фильтр маршрутизации, который определяет тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> будет использоваться при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="c860a-115">Contains a routing filter that determines the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="c860a-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c860a-116">Parent elements</span></span>

|     | <span data-ttu-id="c860a-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c860a-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c860a-118">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="c860a-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="c860a-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="c860a-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c860a-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c860a-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
