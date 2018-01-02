---
title: "&lt;add&gt; для &lt;defaultPorts&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1efe61bf5f4276836c65e9c81d316dc0664f3de2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="e275b-102">&lt;add&gt; для &lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="e275b-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="e275b-103">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="e275b-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="e275b-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e275b-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e275b-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="e275b-105">\<behaviors></span></span>  
<span data-ttu-id="e275b-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e275b-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e275b-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e275b-107">\<behavior></span></span>  
<span data-ttu-id="e275b-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="e275b-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="e275b-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="e275b-109">\<defaultPorts></span></span>  
<span data-ttu-id="e275b-110">\<add></span><span class="sxs-lookup"><span data-stu-id="e275b-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e275b-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e275b-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>   <defaultPorts>      <add port="Integer" scheme="String" />   </defaultPorts></useRequestHeadersForMetadataAddress>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e275b-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e275b-112">Attributes and Elements</span></span>  
 <span data-ttu-id="e275b-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e275b-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e275b-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e275b-114">Attributes</span></span>  
  
|<span data-ttu-id="e275b-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e275b-115">Attribute</span></span>|<span data-ttu-id="e275b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e275b-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e275b-117">порт</span><span class="sxs-lookup"><span data-stu-id="e275b-117">port</span></span>|<span data-ttu-id="e275b-118">Целочисленное значение, определяющее номер COM-порта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e275b-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="e275b-119">scheme</span><span class="sxs-lookup"><span data-stu-id="e275b-119">scheme</span></span>|<span data-ttu-id="e275b-120">Строка, в которой указана группа параметров протокола, связанных с COM-портом.</span><span class="sxs-lookup"><span data-stu-id="e275b-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e275b-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e275b-121">Child Elements</span></span>  
 <span data-ttu-id="e275b-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e275b-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e275b-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e275b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e275b-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="e275b-124">Element</span></span>|<span data-ttu-id="e275b-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="e275b-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e275b-126">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="e275b-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="e275b-127">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="e275b-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e275b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e275b-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
