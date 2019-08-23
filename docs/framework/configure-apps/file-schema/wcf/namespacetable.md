---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 0316e983446644671ead2f8f843dc91b493b29c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933168"
---
# <a name="namespacetable"></a><span data-ttu-id="eb2b5-101">\<Намеспацетабле ></span><span class="sxs-lookup"><span data-stu-id="eb2b5-101">\<namespaceTable></span></span>

<span data-ttu-id="eb2b5-102">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="eb2b5-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="eb2b5-103">**\<> System. serviceModel** </span><span class="sxs-lookup"><span data-stu-id="eb2b5-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="eb2b5-104">&nbsp;&nbsp; **\<> маршрутизации** </span><span class="sxs-lookup"><span data-stu-id="eb2b5-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="eb2b5-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<Намеспацетабле >**</span><span class="sxs-lookup"><span data-stu-id="eb2b5-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="eb2b5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb2b5-106">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb2b5-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="eb2b5-107">Attributes and elements</span></span>

<span data-ttu-id="eb2b5-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eb2b5-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="eb2b5-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eb2b5-109">Attributes</span></span>

<span data-ttu-id="eb2b5-110">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="eb2b5-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="eb2b5-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eb2b5-111">Child elements</span></span>

|     | <span data-ttu-id="eb2b5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="eb2b5-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="eb2b5-113"> **\<> фильтра**</span><span class="sxs-lookup"><span data-stu-id="eb2b5-113">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="eb2b5-114">Определяет сопоставление префикса пространства имен, используемого в выражениях XPath.</span><span class="sxs-lookup"><span data-stu-id="eb2b5-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="eb2b5-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eb2b5-115">Parent elements</span></span>

|     | <span data-ttu-id="eb2b5-116">Описание</span><span class="sxs-lookup"><span data-stu-id="eb2b5-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="eb2b5-117"> **\<> маршрутизации**</span><span class="sxs-lookup"><span data-stu-id="eb2b5-117">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="eb2b5-118">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки. Отправка сообщений в при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="eb2b5-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="eb2b5-119">См. также</span><span class="sxs-lookup"><span data-stu-id="eb2b5-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
