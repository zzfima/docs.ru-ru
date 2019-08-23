---
title: <add> из <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 7e2a2e26099f2d31116e4a89297fc1ac984c480d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920078"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="01601-102">\<Добавление > \<> намеспацетабле</span><span class="sxs-lookup"><span data-stu-id="01601-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="01601-103">Представляет элемент конфигурации, содержащий пространство имен, используемое в качестве префикса сопоставления, которое затем можно использовать в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="01601-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
 <span data-ttu-id="01601-104">\<> System. serviceModel</span><span class="sxs-lookup"><span data-stu-id="01601-104">\<system.serviceModel></span></span>  
<span data-ttu-id="01601-105">\<> маршрутизации</span><span class="sxs-lookup"><span data-stu-id="01601-105">\<routing></span></span>  
<span data-ttu-id="01601-106">\<Намеспацетабле ></span><span class="sxs-lookup"><span data-stu-id="01601-106">\<namespaceTable></span></span>  
<span data-ttu-id="01601-107">\<add></span><span class="sxs-lookup"><span data-stu-id="01601-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01601-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="01601-108">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01601-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="01601-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01601-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="01601-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01601-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="01601-111">Attributes</span></span>  
  
|<span data-ttu-id="01601-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="01601-112">Attribute</span></span>|<span data-ttu-id="01601-113">Описание</span><span class="sxs-lookup"><span data-stu-id="01601-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="01601-114">namespace</span><span class="sxs-lookup"><span data-stu-id="01601-114">namespace</span></span>|<span data-ttu-id="01601-115">Строка, содержащая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="01601-115">A string containing the namespace.</span></span>|  
|<span data-ttu-id="01601-116">prefix</span><span class="sxs-lookup"><span data-stu-id="01601-116">prefix</span></span>|<span data-ttu-id="01601-117">Строка, содержащая префикс этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="01601-117">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="01601-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="01601-118">Child Elements</span></span>  
 <span data-ttu-id="01601-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="01601-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="01601-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="01601-120">Parent Elements</span></span>  
  
|<span data-ttu-id="01601-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="01601-121">Element</span></span>|<span data-ttu-id="01601-122">Описание</span><span class="sxs-lookup"><span data-stu-id="01601-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="01601-123">\<Намеспацетабле ></span><span class="sxs-lookup"><span data-stu-id="01601-123">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="01601-124">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="01601-124">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="01601-125">См. также</span><span class="sxs-lookup"><span data-stu-id="01601-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
