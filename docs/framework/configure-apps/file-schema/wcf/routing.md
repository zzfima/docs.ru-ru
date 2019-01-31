---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: cc7c1a64f9481a7ab41cf35241ade04bd690dae0
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275578"
---
# <a name="routing"></a><span data-ttu-id="572af-101">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="572af-101">\<routing></span></span>

<span data-ttu-id="572af-102">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="572af-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="572af-103">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="572af-103">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="572af-104">&nbsp;&nbsp;**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="572af-104">&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="572af-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="572af-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="572af-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="572af-106">Attributes and elements</span></span>

<span data-ttu-id="572af-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="572af-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="572af-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="572af-108">Attributes</span></span>

<span data-ttu-id="572af-109">Нет</span><span class="sxs-lookup"><span data-stu-id="572af-109">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="572af-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="572af-110">Child elements</span></span>

|     | <span data-ttu-id="572af-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="572af-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="572af-112">**\<Фильтры >**</span><span class="sxs-lookup"><span data-stu-id="572af-112">**\<filters>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | <span data-ttu-id="572af-113">Содержит набор фильтров маршрутизации, которые определяют, что тип MessageFilter Windows Communication Foundation (WCF), который будет использоваться при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="572af-113">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="572af-114">**\<filterTables >**</span><span class="sxs-lookup"><span data-stu-id="572af-114">**\<filterTables>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | <span data-ttu-id="572af-115">Содержит сопоставление между фильтрами маршрутизации и целевыми конечными точками для определения того, какие конечные точки будут использоваться при совпадении с критериями фильтра.</span><span class="sxs-lookup"><span data-stu-id="572af-115">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="572af-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="572af-116">Parent elements</span></span>

|     | <span data-ttu-id="572af-117">Описание:</span><span class="sxs-lookup"><span data-stu-id="572af-117">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="572af-118">**\<system.ServiceModel>**</span><span class="sxs-lookup"><span data-stu-id="572af-118">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="572af-119">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="572af-119">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="572af-120">См. также</span><span class="sxs-lookup"><span data-stu-id="572af-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
