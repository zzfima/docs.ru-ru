---
title: <routing>
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: fcf2d4eec93fd7127c6f800e1c739ad1fac49203
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399964"
---
# <a name="routing"></a><span data-ttu-id="c8a3c-101">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="c8a3c-101">\<routing></span></span>

<span data-ttu-id="c8a3c-102">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки. Отправка сообщений в при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-102">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span>

<span data-ttu-id="c8a3c-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c8a3c-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c8a3c-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c8a3c-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c8a3c-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<> маршрутизации**</span><span class="sxs-lookup"><span data-stu-id="c8a3c-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<routing>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c8a3c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c8a3c-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c8a3c-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8a3c-107">Attributes and elements</span></span>

<span data-ttu-id="c8a3c-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c8a3c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c8a3c-109">Attributes</span></span>

<span data-ttu-id="c8a3c-110">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c8a3c-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c8a3c-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c8a3c-111">Child elements</span></span>

|     | <span data-ttu-id="c8a3c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c8a3c-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c8a3c-113"> **\<Фильтры >** </span><span class="sxs-lookup"><span data-stu-id="c8a3c-113">**\<filters>**</span></span>](filters-of-routing.md) | <span data-ttu-id="c8a3c-114">Содержит набор фильтров маршрутизации, определяющих тип Windows Communication Foundation (WCF) MessageFilter, которые будут использоваться при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-114">Contains a set of routing filters that determine the type of Windows Communication Foundation (WCF) MessageFilter will be used when evaluating incoming messages.</span></span> |
| [<span data-ttu-id="c8a3c-115"> **\<Филтертаблес >** </span><span class="sxs-lookup"><span data-stu-id="c8a3c-115">**\<filterTables>**</span></span>](filtertables.md) | <span data-ttu-id="c8a3c-116">Содержит сопоставление между фильтрами маршрутизации и целевыми конечными точками для определения того, какие конечные точки будут использоваться при совпадении с критериями фильтра.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-116">Contains mappings between the routing filters and the target endpoints to specify which endpoint to use when the filter matches.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="c8a3c-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c8a3c-117">Parent elements</span></span>

|     | <span data-ttu-id="c8a3c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c8a3c-118">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="c8a3c-119">**\<системой. > ServiceModel**</span><span class="sxs-lookup"><span data-stu-id="c8a3c-119">**\<system.ServiceModel>**</span></span> | <span data-ttu-id="c8a3c-120">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="c8a3c-120">The root element of all WCF configuration elements.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c8a3c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c8a3c-121">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
