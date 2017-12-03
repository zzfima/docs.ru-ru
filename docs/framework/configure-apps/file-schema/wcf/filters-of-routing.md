---
title: "&lt;filters&gt; для &lt;routing&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c9dd9faf63ade725bb8bea12b40390fd30c91973
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltersgt-of-ltroutinggt"></a><span data-ttu-id="03cdd-102">&lt;filters&gt; для &lt;routing&gt;</span><span class="sxs-lookup"><span data-stu-id="03cdd-102">&lt;filters&gt; of &lt;routing&gt;</span></span>

<span data-ttu-id="03cdd-103">Представляет раздел конфигурации, где задается набор фильтров маршрутизации, которые определяют тип фильтра [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при вычислении входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="03cdd-103">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages.</span></span>

<span data-ttu-id="03cdd-104">[**\<system.serviceModel >**](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="03cdd-104">[**\<system.serviceModel>**](system-servicemodel.md) </span></span>  
<span data-ttu-id="03cdd-105">&nbsp;&nbsp;[**\<Маршрутизация >**](routing.md) </span><span class="sxs-lookup"><span data-stu-id="03cdd-105">&nbsp;&nbsp;[**\<routing>**](routing.md) </span></span>  
<span data-ttu-id="03cdd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Фильтры >**</span><span class="sxs-lookup"><span data-stu-id="03cdd-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<filters>**</span></span>

## <a name="syntax"></a><span data-ttu-id="03cdd-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="03cdd-107">Syntax</span></span>

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="03cdd-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="03cdd-108">Attributes and elements</span></span>

<span data-ttu-id="03cdd-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="03cdd-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="03cdd-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="03cdd-110">Attributes</span></span>

<span data-ttu-id="03cdd-111">Нет</span><span class="sxs-lookup"><span data-stu-id="03cdd-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="03cdd-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="03cdd-112">Child elements</span></span>

|     | <span data-ttu-id="03cdd-113">Описание</span><span class="sxs-lookup"><span data-stu-id="03cdd-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="03cdd-114">**\<Фильтр >**</span><span class="sxs-lookup"><span data-stu-id="03cdd-114">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="03cdd-115">Содержит фильтр маршрутизации, определяющий тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, который будет использован при оценке входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="03cdd-115">Contains a routing filter that determines the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> will be used when evaluating incoming messages.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="03cdd-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="03cdd-116">Parent elements</span></span>

|     | <span data-ttu-id="03cdd-117">Описание</span><span class="sxs-lookup"><span data-stu-id="03cdd-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="03cdd-118">**\<Маршрутизация >**</span><span class="sxs-lookup"><span data-stu-id="03cdd-118">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="03cdd-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип фильтра [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, используемого при вычислении входящих сообщений, а также в качестве таблиц маршрутизации, определяющих целевые конечные точки для отправки сообщений при соответствии критериям фильтра.</span><span class="sxs-lookup"><span data-stu-id="03cdd-119">Represents a configuration section for defining a set of routing filters, which determine the type of [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="03cdd-120">См. также</span><span class="sxs-lookup"><span data-stu-id="03cdd-120">See also</span></span>

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
