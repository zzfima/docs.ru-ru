---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925888"
---
# <a name="defaultports"></a><span data-ttu-id="d9b07-101">\<Дефаултпортс ></span><span class="sxs-lookup"><span data-stu-id="d9b07-101">\<defaultPorts></span></span>
<span data-ttu-id="d9b07-102">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="d9b07-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="d9b07-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d9b07-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d9b07-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="d9b07-104">\<behaviors></span></span>  
<span data-ttu-id="d9b07-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="d9b07-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="d9b07-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="d9b07-106">\<behavior></span></span>  
<span data-ttu-id="d9b07-107">\<Усерекуессеадерсформетадатааддресс ></span><span class="sxs-lookup"><span data-stu-id="d9b07-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="d9b07-108">\<Дефаултпортс ></span><span class="sxs-lookup"><span data-stu-id="d9b07-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9b07-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d9b07-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9b07-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d9b07-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d9b07-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d9b07-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9b07-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d9b07-112">Attributes</span></span>  
 <span data-ttu-id="d9b07-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="d9b07-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d9b07-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d9b07-114">Child Elements</span></span>  
  
|<span data-ttu-id="d9b07-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="d9b07-115">Element</span></span>|<span data-ttu-id="d9b07-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d9b07-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9b07-117">\<Добавление > \<> дефаултпортс</span><span class="sxs-lookup"><span data-stu-id="d9b07-117">\<add> of \<defaultPorts></span></span>](add-of-defaultports.md)|<span data-ttu-id="d9b07-118">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="d9b07-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d9b07-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d9b07-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d9b07-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="d9b07-120">Element</span></span>|<span data-ttu-id="d9b07-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d9b07-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9b07-122">\<Усерекуессеадерсформетадатааддресс ></span><span class="sxs-lookup"><span data-stu-id="d9b07-122">\<useRequestHeadersForMetadataAddress></span></span>](userequestheadersformetadataaddress.md)|<span data-ttu-id="d9b07-123">Список портов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d9b07-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d9b07-124">См. также</span><span class="sxs-lookup"><span data-stu-id="d9b07-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
