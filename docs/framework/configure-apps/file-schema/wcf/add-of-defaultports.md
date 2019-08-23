---
title: <add> из <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: d2723dad14a63c4b05fdb70157f7eb21d193d3ab
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926711"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="9ee79-102">\<Добавление > \<> дефаултпортс</span><span class="sxs-lookup"><span data-stu-id="9ee79-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="9ee79-103">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="9ee79-103">A default communications endpoint that the client application listens to.</span></span>  
  
 <span data-ttu-id="9ee79-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9ee79-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="9ee79-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="9ee79-105">\<behaviors></span></span>  
<span data-ttu-id="9ee79-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="9ee79-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="9ee79-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="9ee79-107">\<behavior></span></span>  
<span data-ttu-id="9ee79-108">\<Усерекуессеадерсформетадатааддресс ></span><span class="sxs-lookup"><span data-stu-id="9ee79-108">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="9ee79-109">\<Дефаултпортс ></span><span class="sxs-lookup"><span data-stu-id="9ee79-109">\<defaultPorts></span></span>  
<span data-ttu-id="9ee79-110">\<add></span><span class="sxs-lookup"><span data-stu-id="9ee79-110">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee79-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9ee79-111">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ee79-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9ee79-112">Attributes and Elements</span></span>  
 <span data-ttu-id="9ee79-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9ee79-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ee79-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9ee79-114">Attributes</span></span>  
  
|<span data-ttu-id="9ee79-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9ee79-115">Attribute</span></span>|<span data-ttu-id="9ee79-116">Описание</span><span class="sxs-lookup"><span data-stu-id="9ee79-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9ee79-117">порт</span><span class="sxs-lookup"><span data-stu-id="9ee79-117">port</span></span>|<span data-ttu-id="9ee79-118">Целочисленное значение, определяющее номер COM-порта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9ee79-118">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="9ee79-119">scheme</span><span class="sxs-lookup"><span data-stu-id="9ee79-119">scheme</span></span>|<span data-ttu-id="9ee79-120">Строка, в которой указана группа параметров протокола, связанных с COM-портом.</span><span class="sxs-lookup"><span data-stu-id="9ee79-120">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ee79-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9ee79-121">Child Elements</span></span>  
 <span data-ttu-id="9ee79-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="9ee79-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ee79-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9ee79-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9ee79-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="9ee79-124">Element</span></span>|<span data-ttu-id="9ee79-125">Описание</span><span class="sxs-lookup"><span data-stu-id="9ee79-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ee79-126">\<Дефаултпортс ></span><span class="sxs-lookup"><span data-stu-id="9ee79-126">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="9ee79-127">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="9ee79-127">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ee79-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9ee79-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
