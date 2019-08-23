---
title: Раздел <extensions>
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 4c8b5fe6eef1863ee3f02cb761a3aac61406e446
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918970"
---
# <a name="extensions-section"></a><span data-ttu-id="fddcd-102">\<раздел > расширений</span><span class="sxs-lookup"><span data-stu-id="fddcd-102">\<extensions> section</span></span>
<span data-ttu-id="fddcd-103">Данный раздел конфигурации содержит коллекцию расширений, которые позволяют пользователю создавать пользовательские привязки, поведения и другие возможности расширений.</span><span class="sxs-lookup"><span data-stu-id="fddcd-103">This configuration section contains a collection of extensions, which enable the user to create user-defined bindings, behaviors, and other aspects of extensions.</span></span>  
  
<span data-ttu-id="fddcd-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fddcd-104">\<system.ServiceModel></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fddcd-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fddcd-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fddcd-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fddcd-106">Attributes and Elements</span></span>  
 <span data-ttu-id="fddcd-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fddcd-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fddcd-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fddcd-108">Attributes</span></span>  
 <span data-ttu-id="fddcd-109">Нет.</span><span class="sxs-lookup"><span data-stu-id="fddcd-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="fddcd-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fddcd-110">Child Elements</span></span>  
  
|<span data-ttu-id="fddcd-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="fddcd-111">Element</span></span>|<span data-ttu-id="fddcd-112">Описание</span><span class="sxs-lookup"><span data-stu-id="fddcd-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fddcd-113">\<Бехавиорекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="fddcd-113">\<behaviorExtensions></span></span>](behaviorextensions.md)|<span data-ttu-id="fddcd-114">Этот раздел содержит дочерние элементы, которые задают расширения поведений, которые позволяют пользователю настроить поведения службы или конечной точки.</span><span class="sxs-lookup"><span data-stu-id="fddcd-114">This section contains child elements that specify behavior extensions, which enable the user to customize service or endpoint behaviors.</span></span>|  
|[<span data-ttu-id="fddcd-115">\<Биндинжелементекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="fddcd-115">\<bindingElementExtensions></span></span>](bindingelementextensions.md)|<span data-ttu-id="fddcd-116">В этом разделе описывается, как обеспечивается использование пользовательского элемента привязки в файле конфигурации компьютера или приложения.</span><span class="sxs-lookup"><span data-stu-id="fddcd-116">This section enables the use of a custom binding element from a machine or application configuration file.</span></span>|  
|[<span data-ttu-id="fddcd-117">\<Биндинжекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="fddcd-117">\<bindingExtensions></span></span>](bindingextensions.md)|<span data-ttu-id="fddcd-118">Этот раздел содержит дочерние элементы, которые задают расширения привязки, которые позволяют пользователю настроить привязки.</span><span class="sxs-lookup"><span data-stu-id="fddcd-118">This section contains child elements that specify binding extensions, which enable the user to customize bindings.</span></span>|  
|[<span data-ttu-id="fddcd-119">\<Ендпоинтекстенсионс ></span><span class="sxs-lookup"><span data-stu-id="fddcd-119">\<endpointExtensions></span></span>](endpointextensions.md)|<span data-ttu-id="fddcd-120">Этот раздел содержит дочерние элементы, которые регистрируют стандартные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="fddcd-120">This section contains child elements that registers standard endpoints.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fddcd-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fddcd-121">Parent Elements</span></span>  
  
|<span data-ttu-id="fddcd-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="fddcd-122">Element</span></span>|<span data-ttu-id="fddcd-123">Описание</span><span class="sxs-lookup"><span data-stu-id="fddcd-123">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fddcd-124">system.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="fddcd-124">system.ServiceModel</span></span>|<span data-ttu-id="fddcd-125">Корневой элемент всех элементов конфигурации WCF.</span><span class="sxs-lookup"><span data-stu-id="fddcd-125">The root element of all WCF configuration elements.</span></span>|
