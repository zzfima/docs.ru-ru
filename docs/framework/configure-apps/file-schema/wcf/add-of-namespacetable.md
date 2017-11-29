---
title: "&lt;add&gt; для &lt;namespaceTable&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f08f4b46c6e6290602fc78a2f06954b9cf0b07d5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a><span data-ttu-id="d3219-102">&lt;add&gt; для &lt;namespaceTable&gt;</span><span class="sxs-lookup"><span data-stu-id="d3219-102">&lt;add&gt; of &lt;namespaceTable&gt;</span></span>
<span data-ttu-id="d3219-103">Представляет элемент конфигурации, содержащий пространство имен, используемое в качестве префикса сопоставления, которое затем можно использовать в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="d3219-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="d3219-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="d3219-104">\<system.serviceModel></span></span>  
<span data-ttu-id="d3219-105">\<Маршрутизация ></span><span class="sxs-lookup"><span data-stu-id="d3219-105">\<routing></span></span>  
<span data-ttu-id="d3219-106">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="d3219-106">\<namespaceTable></span></span>  
<span data-ttu-id="d3219-107">\<add></span><span class="sxs-lookup"><span data-stu-id="d3219-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3219-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3219-108">Syntax</span></span>  
  
```xml  
   <routing>   <namespaceTable>  
     <add namespace="String" prefix="String" />    </namespaceTable></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3219-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d3219-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d3219-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d3219-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3219-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d3219-111">Attributes</span></span>  
  
|<span data-ttu-id="d3219-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d3219-112">Attribute</span></span>|<span data-ttu-id="d3219-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d3219-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3219-114">namespace</span><span class="sxs-lookup"><span data-stu-id="d3219-114">namespace</span></span>|<span data-ttu-id="d3219-115">Строка, содержащая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="d3219-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="d3219-116">prefix</span><span class="sxs-lookup"><span data-stu-id="d3219-116">prefix</span></span>|<span data-ttu-id="d3219-117">Строка, содержащая префикс этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d3219-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3219-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d3219-118">Child Elements</span></span>  
 <span data-ttu-id="d3219-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="d3219-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3219-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d3219-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d3219-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="d3219-121">Element</span></span>|<span data-ttu-id="d3219-122">Описание</span><span class="sxs-lookup"><span data-stu-id="d3219-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3219-123">\<namespaceTable ></span><span class="sxs-lookup"><span data-stu-id="d3219-123">\<namespaceTable></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|<span data-ttu-id="d3219-124">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="d3219-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d3219-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d3219-125">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
