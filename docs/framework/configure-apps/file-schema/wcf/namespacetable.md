---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: fb2b324a2c128b470f1a9a21343408280c5e1862
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743248"
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="aa3a6-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="aa3a6-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="aa3a6-103">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="aa3a6-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="aa3a6-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="aa3a6-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="aa3a6-105">&nbsp;&nbsp;**\<Маршрутизация >** </span><span class="sxs-lookup"><span data-stu-id="aa3a6-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="aa3a6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="aa3a6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="aa3a6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa3a6-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa3a6-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa3a6-108">Attributes and elements</span></span>

<span data-ttu-id="aa3a6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa3a6-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="aa3a6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa3a6-110">Attributes</span></span>

<span data-ttu-id="aa3a6-111">Нет</span><span class="sxs-lookup"><span data-stu-id="aa3a6-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="aa3a6-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa3a6-112">Child elements</span></span>

|     | <span data-ttu-id="aa3a6-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="aa3a6-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="aa3a6-114">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="aa3a6-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="aa3a6-115">Определяет сопоставление префикса пространства имен, используемого в выражениях XPath.</span><span class="sxs-lookup"><span data-stu-id="aa3a6-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="aa3a6-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa3a6-116">Parent elements</span></span>

|     | <span data-ttu-id="aa3a6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="aa3a6-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="aa3a6-118">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="aa3a6-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="aa3a6-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="aa3a6-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="aa3a6-120">См. также</span><span class="sxs-lookup"><span data-stu-id="aa3a6-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
