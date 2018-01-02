---
title: "&lt;Маршрутизация&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ef71753a4b0ff20a966842119adb6e637ded1f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltroutinggt"></a><span data-ttu-id="a7a11-102">&lt;Маршрутизация&gt;</span><span class="sxs-lookup"><span data-stu-id="a7a11-102">&lt;routing&gt;</span></span>

<span data-ttu-id="a7a11-103">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип фильтра [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter>, используемого при вычислении входящих сообщений, а также в качестве таблиц маршрутизации, определяющих целевые конечные точки для отправки сообщений при соответствии критериям фильтра.</span><span class="sxs-lookup"><span data-stu-id="a7a11-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="a7a11-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="a7a11-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="a7a11-105">&nbsp;&nbsp;**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="a7a11-105">&nbsp;&nbsp;**\<routing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="a7a11-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7a11-106">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String" 
               filterName="String" 
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="a7a11-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="a7a11-107">Attributes and elements</span></span>

<span data-ttu-id="a7a11-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a7a11-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="a7a11-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a7a11-109">Attributes</span></span>

<span data-ttu-id="a7a11-110">Нет</span><span class="sxs-lookup"><span data-stu-id="a7a11-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="a7a11-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a7a11-111">Child elements</span></span>

|     | <span data-ttu-id="a7a11-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="a7a11-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a7a11-113">**\<Фильтры >**</span><span class="sxs-lookup"><span data-stu-id="a7a11-113">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="a7a11-114">Содержит набор фильтров маршрутизации, которые определяет тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter, который будет использован при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="a7a11-114">Contains a set of routing filters that determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="a7a11-115">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="a7a11-115">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="a7a11-116">Содержит сопоставление между фильтрами маршрутизации и целевыми конечными точками для определения того, какие конечные точки будут использоваться при совпадении с критериями фильтра.</span><span class="sxs-lookup"><span data-stu-id="a7a11-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="a7a11-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a7a11-117">Parent elements</span></span>

|     | <span data-ttu-id="a7a11-118">Описание:</span><span class="sxs-lookup"><span data-stu-id="a7a11-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="a7a11-119">**\<система. ServiceModel >**</span><span class="sxs-lookup"><span data-stu-id="a7a11-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="a7a11-120">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="a7a11-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="a7a11-121">См. также</span><span class="sxs-lookup"><span data-stu-id="a7a11-121">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
