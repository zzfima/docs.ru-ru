---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 31d661f39f9e3de0f7012c7fa52d4964e7ee4a69
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748884"
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="8d97b-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="8d97b-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="8d97b-103">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="8d97b-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="8d97b-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="8d97b-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="8d97b-105">&nbsp;&nbsp;**\<Маршрутизация >** </span><span class="sxs-lookup"><span data-stu-id="8d97b-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="8d97b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="8d97b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8d97b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d97b-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="8d97b-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d97b-108">Attributes and elements</span></span>

<span data-ttu-id="8d97b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8d97b-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="8d97b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8d97b-110">Attributes</span></span>

<span data-ttu-id="8d97b-111">Нет</span><span class="sxs-lookup"><span data-stu-id="8d97b-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="8d97b-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8d97b-112">Child elements</span></span>

|     | <span data-ttu-id="8d97b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8d97b-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8d97b-114">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="8d97b-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="8d97b-115">Определяет сопоставление префикса пространства имен, используемого в выражениях XPath.</span><span class="sxs-lookup"><span data-stu-id="8d97b-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="8d97b-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8d97b-116">Parent elements</span></span>

|     | <span data-ttu-id="8d97b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="8d97b-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8d97b-118">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="8d97b-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="8d97b-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизацию таблиц, определяющих целевые конечные точки для Отправка сообщений при соответствии критериям фильтра.</span><span class="sxs-lookup"><span data-stu-id="8d97b-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="8d97b-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8d97b-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
