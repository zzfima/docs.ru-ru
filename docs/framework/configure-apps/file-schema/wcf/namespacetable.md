---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: aefe7beec7335d80341e670961800907c2bd0200
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855094"
---
# <a name="namespacetable"></a><span data-ttu-id="c6d75-101">\<Намеспацетабле ></span><span class="sxs-lookup"><span data-stu-id="c6d75-101">\<namespaceTable></span></span>

<span data-ttu-id="c6d75-102">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="c6d75-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="c6d75-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c6d75-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c6d75-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c6d75-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c6d75-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="c6d75-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="c6d75-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Намеспацетабле >**</span><span class="sxs-lookup"><span data-stu-id="c6d75-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d75-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6d75-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6d75-108">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="c6d75-108">Attributes and elements</span></span>

<span data-ttu-id="c6d75-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c6d75-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c6d75-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c6d75-110">Attributes</span></span>

<span data-ttu-id="c6d75-111">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c6d75-111">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c6d75-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c6d75-112">Child elements</span></span>

|     | <span data-ttu-id="c6d75-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c6d75-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c6d75-114"> **\<> фильтра**</span><span class="sxs-lookup"><span data-stu-id="c6d75-114">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="c6d75-115">Определяет сопоставление префикса пространства имен, используемого в выражениях XPath.</span><span class="sxs-lookup"><span data-stu-id="c6d75-115">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="c6d75-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c6d75-116">Parent elements</span></span>

|     | <span data-ttu-id="c6d75-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c6d75-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c6d75-118"> **\<> маршрутизации**</span><span class="sxs-lookup"><span data-stu-id="c6d75-118">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="c6d75-119">Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки. Отправка сообщений в при совпадении фильтра.</span><span class="sxs-lookup"><span data-stu-id="c6d75-119">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c6d75-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c6d75-120">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
