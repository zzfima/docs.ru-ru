---
title: '&lt;namespaceTable&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 470dd2dcc2e8554bb89eec159c6b96b24795c5d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltnamespacetablegt"></a><span data-ttu-id="c4bec-102">&lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="c4bec-102">&lt;namespaceTable&gt;</span></span>

<span data-ttu-id="c4bec-103">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="c4bec-103">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="c4bec-104">**\<system.serviceModel >** </span><span class="sxs-lookup"><span data-stu-id="c4bec-104">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="c4bec-105">&nbsp;&nbsp;**\<Маршрутизация >** </span><span class="sxs-lookup"><span data-stu-id="c4bec-105">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="c4bec-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**</span><span class="sxs-lookup"><span data-stu-id="c4bec-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c4bec-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4bec-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
``` 

## <a name="attributes-and-elements"></a><span data-ttu-id="c4bec-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="c4bec-108">Attributes and elements</span></span>

<span data-ttu-id="c4bec-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c4bec-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c4bec-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c4bec-110">Attributes</span></span>

<span data-ttu-id="c4bec-111">Нет</span><span class="sxs-lookup"><span data-stu-id="c4bec-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c4bec-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c4bec-112">Child elements</span></span>

|     | <span data-ttu-id="c4bec-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c4bec-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c4bec-114">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="c4bec-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="c4bec-115">Определяет сопоставление префикса пространства имен, используемого в выражениях XPath.</span><span class="sxs-lookup"><span data-stu-id="c4bec-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="c4bec-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c4bec-116">Parent elements</span></span>

|     | <span data-ttu-id="c4bec-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c4bec-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c4bec-118">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="c4bec-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="c4bec-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип фильтра [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, используемого при вычислении входящих сообщений, а также в качестве таблиц маршрутизации, определяющих целевые конечные точки для отправки сообщений при соответствии критериям фильтра.</span><span class="sxs-lookup"><span data-stu-id="c4bec-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c4bec-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c4bec-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
