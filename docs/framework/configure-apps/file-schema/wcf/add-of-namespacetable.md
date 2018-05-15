---
title: '&lt;add&gt; для &lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 5ae672f12a2ef58efc9738624c113855e59e02b6
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="bf218-102">&lt;add&gt; для &lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="bf218-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="bf218-103">Представляет элемент конфигурации, содержащий пространство имен, используемое в качестве префикса сопоставления, которое затем можно использовать в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="bf218-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="bf218-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="bf218-104">\<system.serviceModel></span></span>  
<span data-ttu-id="bf218-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="bf218-105">\<routing></span></span>  
<span data-ttu-id="bf218-106">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="bf218-106">\<namespaceTable></span></span>  
<span data-ttu-id="bf218-107">\<add></span><span class="sxs-lookup"><span data-stu-id="bf218-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf218-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf218-108">Syntax</span></span>  
  
```xml  
   <routing>   <namespaceTable>  
     <add namespace="String" prefix="String" />    </namespaceTable></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf218-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bf218-109">Attributes and Elements</span></span>  
 <span data-ttu-id="bf218-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bf218-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf218-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bf218-111">Attributes</span></span>  
  
|<span data-ttu-id="bf218-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bf218-112">Attribute</span></span>|<span data-ttu-id="bf218-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bf218-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf218-114">namespace</span><span class="sxs-lookup"><span data-stu-id="bf218-114">namespace</span></span>|<span data-ttu-id="bf218-115">Строка, содержащая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="bf218-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="bf218-116">prefix</span><span class="sxs-lookup"><span data-stu-id="bf218-116">prefix</span></span>|<span data-ttu-id="bf218-117">Строка, содержащая префикс этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="bf218-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf218-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bf218-118">Child Elements</span></span>  
 <span data-ttu-id="bf218-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bf218-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf218-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bf218-120">Parent Elements</span></span>  
  
|<span data-ttu-id="bf218-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="bf218-121">Element</span></span>|<span data-ttu-id="bf218-122">Описание</span><span class="sxs-lookup"><span data-stu-id="bf218-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf218-123">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="bf218-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="bf218-124">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="bf218-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf218-125">См. также</span><span class="sxs-lookup"><span data-stu-id="bf218-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
