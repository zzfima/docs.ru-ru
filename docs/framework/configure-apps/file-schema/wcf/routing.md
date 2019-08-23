---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 3c7e9cb1284ab55c8dd199d9fb47a223698814f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934129"
---
# <a name="routing"></a><span data-ttu-id="668eb-101">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="668eb-101">\<routing></span></span>

<span data-ttu-id="668eb-102">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки. Отправка сообщений в при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="668eb-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="668eb-103">[ **\<> System. serviceModel**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="668eb-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="668eb-104">&nbsp;&nbsp; **\<> маршрутизации**</span><span class="sxs-lookup"><span data-stu-id="668eb-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="668eb-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="668eb-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="668eb-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="668eb-106">Attributes and elements</span></span>

<span data-ttu-id="668eb-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="668eb-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="668eb-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="668eb-108">Attributes</span></span>

<span data-ttu-id="668eb-109">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="668eb-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="668eb-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="668eb-110">Child elements</span></span>

|     | <span data-ttu-id="668eb-111">Описание</span><span class="sxs-lookup"><span data-stu-id="668eb-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="668eb-112"> **\<Фильтры >** </span><span class="sxs-lookup"><span data-stu-id="668eb-112">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="668eb-113">Содержит набор фильтров маршрутизации, определяющих тип Windows Communication Foundation (WCF) MessageFilter, которые будут использоваться при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="668eb-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="668eb-114"> **\<Филтертаблес >** </span><span class="sxs-lookup"><span data-stu-id="668eb-114">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="668eb-115">Содержит сопоставление между фильтрами маршрутизации и целевыми конечными точками для определения того, какие конечные точки будут использоваться при совпадении с критериями фильтра.</span><span class="sxs-lookup"><span data-stu-id="668eb-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="668eb-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="668eb-116">Parent elements</span></span>

|     | <span data-ttu-id="668eb-117">Описание</span><span class="sxs-lookup"><span data-stu-id="668eb-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="668eb-118">**\<системой. > ServiceModel**</span><span class="sxs-lookup"><span data-stu-id="668eb-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="668eb-119">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="668eb-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="668eb-120">См. также</span><span class="sxs-lookup"><span data-stu-id="668eb-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
