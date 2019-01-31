---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269579"
---
# <a name="namespacetable"></a><span data-ttu-id="06b34-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="06b34-101">\<namespaceTable></span></span>

<span data-ttu-id="06b34-102">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="06b34-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="06b34-103">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="06b34-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="06b34-104">&nbsp;&nbsp;**\<Маршрутизация >** </span><span class="sxs-lookup"><span data-stu-id="06b34-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="06b34-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="06b34-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="06b34-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06b34-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="06b34-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="06b34-107">Attributes and elements</span></span>

<span data-ttu-id="06b34-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="06b34-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="06b34-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="06b34-109">Attributes</span></span>

<span data-ttu-id="06b34-110">Нет</span><span class="sxs-lookup"><span data-stu-id="06b34-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="06b34-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="06b34-111">Child elements</span></span>

|     | <span data-ttu-id="06b34-112">Описание</span><span class="sxs-lookup"><span data-stu-id="06b34-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="06b34-113">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="06b34-113">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="06b34-114">Определяет сопоставление префикса пространства имен, используемого в выражениях XPath.</span><span class="sxs-lookup"><span data-stu-id="06b34-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="06b34-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="06b34-115">Parent elements</span></span>

|     | <span data-ttu-id="06b34-116">Описание</span><span class="sxs-lookup"><span data-stu-id="06b34-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="06b34-117">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="06b34-117">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="06b34-118">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="06b34-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="06b34-119">См. также</span><span class="sxs-lookup"><span data-stu-id="06b34-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
