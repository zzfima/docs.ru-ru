---
title: '&lt;transportConfigurationTypes&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa136f75fda4a87171a8ca3e369e7cb8621ac398
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportconfigurationtypesgt"></a><span data-ttu-id="dc0db-102">&lt;transportConfigurationTypes&gt;</span><span class="sxs-lookup"><span data-stu-id="dc0db-102">&lt;transportConfigurationTypes&gt;</span></span>
<span data-ttu-id="dc0db-103">Представляет коллекцию элементов конфигурации, которые определяют тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="dc0db-103">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="dc0db-104">Может использоваться для добавления пользовательских протоколов WAS.</span><span class="sxs-lookup"><span data-stu-id="dc0db-104">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="dc0db-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dc0db-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="dc0db-106">\<ServiceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="dc0db-106">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="dc0db-107">\<transportConfigurationTypes ></span><span class="sxs-lookup"><span data-stu-id="dc0db-107">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc0db-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc0db-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc0db-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc0db-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dc0db-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc0db-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc0db-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc0db-111">Attributes</span></span>  
  
|<span data-ttu-id="dc0db-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dc0db-112">Attribute</span></span>|<span data-ttu-id="dc0db-113">Описание</span><span class="sxs-lookup"><span data-stu-id="dc0db-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dc0db-114">имя</span><span class="sxs-lookup"><span data-stu-id="dc0db-114">name</span></span>|<span data-ttu-id="dc0db-115">Имя транспорта</span><span class="sxs-lookup"><span data-stu-id="dc0db-115">The name of the transport</span></span>|  
|<span data-ttu-id="dc0db-116">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="dc0db-116">transportConfigurationType</span></span>|<span data-ttu-id="dc0db-117">Тип, реализующий транспорт</span><span class="sxs-lookup"><span data-stu-id="dc0db-117">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc0db-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc0db-118">Child Elements</span></span>  
  
|<span data-ttu-id="dc0db-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc0db-119">Element</span></span>|<span data-ttu-id="dc0db-120">Описание</span><span class="sxs-lookup"><span data-stu-id="dc0db-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc0db-121">\<add></span><span class="sxs-lookup"><span data-stu-id="dc0db-121">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="dc0db-122">Добавляет элемент конфигурации, который определяет тип конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="dc0db-122">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc0db-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc0db-123">Parent Elements</span></span>  
  
|<span data-ttu-id="dc0db-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc0db-124">Element</span></span>|<span data-ttu-id="dc0db-125">Описание</span><span class="sxs-lookup"><span data-stu-id="dc0db-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc0db-126">\<serviceHostingEnvironment ></span><span class="sxs-lookup"><span data-stu-id="dc0db-126">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="dc0db-127">Определяет, какой тип среда размещения служб создает для конкретного транспорта.</span><span class="sxs-lookup"><span data-stu-id="dc0db-127">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dc0db-128">См. также</span><span class="sxs-lookup"><span data-stu-id="dc0db-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>  
 <xref:System.ServiceModel.ServiceHostingEnvironment>  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>  
 [<span data-ttu-id="dc0db-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="dc0db-129">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
