---
title: <add> из <namespaceTable>
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: 3b3b4a1584b37601269368ee0e4e973626ddf9cf
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850398"
---
# <a name="add-of-namespacetable"></a><span data-ttu-id="431d9-102">\<Добавление > \<> намеспацетабле</span><span class="sxs-lookup"><span data-stu-id="431d9-102">\<add> of \<namespaceTable></span></span>
<span data-ttu-id="431d9-103">Представляет элемент конфигурации, содержащий пространство имен, используемое в качестве префикса сопоставления, которое затем можно использовать в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="431d9-103">Represents a configuration element that contains a namespace to prefix mapping that can then be used in XPath filters for routing.</span></span>  
  
<span data-ttu-id="431d9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="431d9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="431d9-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="431d9-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="431d9-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)</span><span class="sxs-lookup"><span data-stu-id="431d9-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="431d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Намеспацетабле >** ](namespacetable.md)</span><span class="sxs-lookup"><span data-stu-id="431d9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namespaceTable>**](namespacetable.md)</span></span>\
<span data-ttu-id="431d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="431d9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="431d9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="431d9-109">Syntax</span></span>  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="431d9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="431d9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="431d9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="431d9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="431d9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="431d9-112">Attributes</span></span>  
  
|<span data-ttu-id="431d9-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="431d9-113">Attribute</span></span>|<span data-ttu-id="431d9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="431d9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="431d9-115">namespace</span><span class="sxs-lookup"><span data-stu-id="431d9-115">namespace</span></span>|<span data-ttu-id="431d9-116">Строка, содержащая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="431d9-116">A string containing the namespace.</span></span>|  
|<span data-ttu-id="431d9-117">prefix</span><span class="sxs-lookup"><span data-stu-id="431d9-117">prefix</span></span>|<span data-ttu-id="431d9-118">Строка, содержащая префикс этого пространства имен.</span><span class="sxs-lookup"><span data-stu-id="431d9-118">A string containing the prefix for this namespace.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="431d9-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="431d9-119">Child Elements</span></span>  
 <span data-ttu-id="431d9-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="431d9-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="431d9-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="431d9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="431d9-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="431d9-122">Element</span></span>|<span data-ttu-id="431d9-123">Описание</span><span class="sxs-lookup"><span data-stu-id="431d9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="431d9-124">\<Намеспацетабле ></span><span class="sxs-lookup"><span data-stu-id="431d9-124">\<namespaceTable></span></span>](namespacetable.md)|<span data-ttu-id="431d9-125">Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="431d9-125">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="431d9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="431d9-126">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>
