---
title: <add> из <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: 5200c8893a89488b72c2c71d1a3703bf2aad1235
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136751"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="5ec79-102">\<Добавить > из \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="5ec79-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="5ec79-103">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="5ec79-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="5ec79-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5ec79-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5ec79-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="5ec79-105">\<behaviors></span></span>  
<span data-ttu-id="5ec79-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5ec79-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5ec79-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5ec79-107">\<behavior></span></span>  
<span data-ttu-id="5ec79-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="5ec79-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="5ec79-109">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="5ec79-109">\<defaultPorts></span></span>  
<span data-ttu-id="5ec79-110">\<add></span><span class="sxs-lookup"><span data-stu-id="5ec79-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ec79-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ec79-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5ec79-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5ec79-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5ec79-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5ec79-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5ec79-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5ec79-114">Attributes</span></span>  
  
|<span data-ttu-id="5ec79-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5ec79-115">Attribute</span></span>|<span data-ttu-id="5ec79-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5ec79-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5ec79-117">порт</span><span class="sxs-lookup"><span data-stu-id="5ec79-117">port</span></span>|<span data-ttu-id="5ec79-118">Целочисленное значение, определяющее номер COM-порта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5ec79-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="5ec79-119">scheme</span><span class="sxs-lookup"><span data-stu-id="5ec79-119">scheme</span></span>|<span data-ttu-id="5ec79-120">Строка, в которой указана группа параметров протокола, связанных с COM-портом.</span><span class="sxs-lookup"><span data-stu-id="5ec79-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5ec79-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5ec79-121">Child Elements</span></span>  
 <span data-ttu-id="5ec79-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5ec79-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5ec79-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5ec79-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5ec79-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="5ec79-124">Element</span></span>|<span data-ttu-id="5ec79-125">Описание</span><span class="sxs-lookup"><span data-stu-id="5ec79-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5ec79-126">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="5ec79-126">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="5ec79-127">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="5ec79-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ec79-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5ec79-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
