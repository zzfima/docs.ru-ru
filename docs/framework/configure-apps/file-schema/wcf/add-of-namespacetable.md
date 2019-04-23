---
title: <add> из <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e65b66170465a8b3bb60754feebb7730b959d9d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089722"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="6bf1a-102">\<Добавить > из \<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="6bf1a-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="6bf1a-103">Представляет элемент конфигурации, содержащий пространство имен, используемое в качестве префикса сопоставления, которое затем можно использовать в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="6bf1a-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="6bf1a-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6bf1a-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6bf1a-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="6bf1a-105">\<routing></span></span>  
<span data-ttu-id="6bf1a-106">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="6bf1a-106">\<namespaceTable></span></span>  
<span data-ttu-id="6bf1a-107">\<add></span><span class="sxs-lookup"><span data-stu-id="6bf1a-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bf1a-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bf1a-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6bf1a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6bf1a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6bf1a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6bf1a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6bf1a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6bf1a-111">Attributes</span></span>  
  
|<span data-ttu-id="6bf1a-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6bf1a-112">Attribute</span></span>|<span data-ttu-id="6bf1a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6bf1a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6bf1a-114">namespace</span><span class="sxs-lookup"><span data-stu-id="6bf1a-114">namespace</span></span>|<span data-ttu-id="6bf1a-115">Строка, содержащая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="6bf1a-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="6bf1a-116">prefix</span><span class="sxs-lookup"><span data-stu-id="6bf1a-116">prefix</span></span>|<span data-ttu-id="6bf1a-117">Строка, содержащая префикс этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="6bf1a-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6bf1a-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6bf1a-118">Child Elements</span></span>  
 <span data-ttu-id="6bf1a-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6bf1a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6bf1a-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6bf1a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="6bf1a-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="6bf1a-121">Element</span></span>|<span data-ttu-id="6bf1a-122">Описание</span><span class="sxs-lookup"><span data-stu-id="6bf1a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6bf1a-123">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="6bf1a-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="6bf1a-124">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="6bf1a-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6bf1a-125">См. также</span><span class="sxs-lookup"><span data-stu-id="6bf1a-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
