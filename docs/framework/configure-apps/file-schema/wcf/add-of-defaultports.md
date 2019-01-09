---
title: '&lt;add&gt; для &lt;defaultPorts&gt;'
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 0932ef9afacb6278c4857dcfd6ba545595ff8f9d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147724"
---
# <a name="ltaddgt-of-ltdefaultportsgt"></a><span data-ttu-id="4456f-102">&lt;add&gt; для &lt;defaultPorts&gt;</span><span class="sxs-lookup"><span data-stu-id="4456f-102">&lt;add&gt; of &lt;defaultPorts&gt;</span></span>
<span data-ttu-id="4456f-103">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="4456f-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="4456f-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="4456f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4456f-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="4456f-105">\<behaviors></span></span>  
<span data-ttu-id="4456f-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="4456f-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="4456f-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="4456f-107">\<behavior></span></span>  
<span data-ttu-id="4456f-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="4456f-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="4456f-109">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="4456f-109">\<defaultPorts></span></span>  
<span data-ttu-id="4456f-110">\<add></span><span class="sxs-lookup"><span data-stu-id="4456f-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4456f-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4456f-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4456f-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4456f-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4456f-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4456f-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4456f-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4456f-114">Attributes</span></span>  
  
|<span data-ttu-id="4456f-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4456f-115">Attribute</span></span>|<span data-ttu-id="4456f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4456f-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4456f-117">порт</span><span class="sxs-lookup"><span data-stu-id="4456f-117">port</span></span>|<span data-ttu-id="4456f-118">Целочисленное значение, определяющее номер COM-порта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4456f-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="4456f-119">scheme</span><span class="sxs-lookup"><span data-stu-id="4456f-119">scheme</span></span>|<span data-ttu-id="4456f-120">Строка, в которой указана группа параметров протокола, связанных с COM-портом.</span><span class="sxs-lookup"><span data-stu-id="4456f-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4456f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4456f-121">Child Elements</span></span>  
 <span data-ttu-id="4456f-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4456f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4456f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4456f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4456f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="4456f-124">Element</span></span>|<span data-ttu-id="4456f-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="4456f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4456f-126">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="4456f-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="4456f-127">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="4456f-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4456f-128">См. также</span><span class="sxs-lookup"><span data-stu-id="4456f-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.DefaultPortElement>
