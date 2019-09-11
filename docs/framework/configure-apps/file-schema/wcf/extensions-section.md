---
title: Раздел <extensions>
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 35621acaf96a80ffa3ffe4a3c6605143c48995a5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855352"
---
# <a name="extensions-section"></a><span data-ttu-id="2fcd8-102">\<раздел > расширений</span><span class="sxs-lookup"><span data-stu-id="2fcd8-102">\<extensions> section</span></span>
<span data-ttu-id="2fcd8-103">Данный раздел конфигурации содержит коллекцию расширений, которые позволяют пользователю создавать пользовательские привязки, поведения и другие возможности расширений.</span><span class="sxs-lookup"><span data-stu-id="2fcd8-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="2fcd8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2fcd8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2fcd8-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2fcd8-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2fcd8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<расширения >**</span><span class="sxs-lookup"><span data-stu-id="2fcd8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<extensions>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fcd8-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2fcd8-107">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fcd8-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2fcd8-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2fcd8-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2fcd8-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fcd8-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2fcd8-110">Attributes</span></span>  
 <span data-ttu-id="2fcd8-111">Нет.</span><span class="sxs-lookup"><span data-stu-id="2fcd8-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2fcd8-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2fcd8-112">Child Elements</span></span>  
  
|<span data-ttu-id="2fcd8-113">Элемент</span><span class="sxs-lookup"><span data-stu-id="2fcd8-113">Element</span></span>|<span data-ttu-id="2fcd8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2fcd8-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fcd8-115">\<Бехавиорекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="2fcd8-115">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="2fcd8-116">Этот раздел содержит дочерние элементы, которые задают расширения поведений, которые позволяют пользователю настроить поведения службы или конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2fcd8-116">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="2fcd8-117">\<Биндинжелементекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="2fcd8-117">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="2fcd8-118">В этом разделе описывается, как обеспечивается использование пользовательского элемента привязки в файле конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="2fcd8-118">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="2fcd8-119">\<Биндинжекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="2fcd8-119">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="2fcd8-120">Этот раздел содержит дочерние элементы, которые задают расширения привязки, которые позволяют пользователю настроить привязки.</span><span class="sxs-lookup"><span data-stu-id="2fcd8-120">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="2fcd8-121">\<Ендпоинтекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="2fcd8-121">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="2fcd8-122">Этот раздел содержит дочерние элементы, которые регистрируют стандартные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="2fcd8-122">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2fcd8-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2fcd8-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2fcd8-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="2fcd8-124">Element</span></span>|<span data-ttu-id="2fcd8-125">Описание</span><span class="sxs-lookup"><span data-stu-id="2fcd8-125">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fcd8-126">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="2fcd8-126">system.ServiceModel</span></span>|<span data-ttu-id="2fcd8-127">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="2fcd8-127">The root element of all WCF configuration elements.</span></span>|
