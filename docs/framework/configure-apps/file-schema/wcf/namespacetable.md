---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772415"
---
# <a name="namespacetable"></a><span data-ttu-id="f455e-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="f455e-101">\<namespaceTable></span></span>

<span data-ttu-id="f455e-102">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="f455e-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="f455e-103">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="f455e-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="f455e-104">&nbsp;&nbsp;**\<Маршрутизация >** </span><span class="sxs-lookup"><span data-stu-id="f455e-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="f455e-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="f455e-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="f455e-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f455e-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f455e-107">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="f455e-107">Attributes and elements</span></span>

<span data-ttu-id="f455e-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f455e-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="f455e-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f455e-109">Attributes</span></span>

<span data-ttu-id="f455e-110">Нет</span><span class="sxs-lookup"><span data-stu-id="f455e-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="f455e-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f455e-111">Child elements</span></span>

|     | <span data-ttu-id="f455e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f455e-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f455e-113">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="f455e-113">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="f455e-114">Определяет сопоставление префикса пространства имен, используемого в выражениях XPath.</span><span class="sxs-lookup"><span data-stu-id="f455e-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="f455e-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f455e-115">Parent elements</span></span>

|     | <span data-ttu-id="f455e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="f455e-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f455e-117">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="f455e-117">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="f455e-118">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.</span><span class="sxs-lookup"><span data-stu-id="f455e-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f455e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="f455e-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
