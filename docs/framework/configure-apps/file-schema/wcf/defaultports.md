---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 4d7fdfb1cccb14f03d11864f1939cb578c79880a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704119"
---
# <a name="defaultports"></a><span data-ttu-id="e2184-101">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="e2184-101">\<defaultPorts></span></span>
<span data-ttu-id="e2184-102">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="e2184-102">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>  
  
<span data-ttu-id="e2184-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="e2184-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="e2184-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="e2184-104">\<behaviors></span></span>  
<span data-ttu-id="e2184-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e2184-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="e2184-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e2184-106">\<behavior></span></span>  
<span data-ttu-id="e2184-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="e2184-107">\<useRequestHeadersForMetadataAddress></span></span>  
<span data-ttu-id="e2184-108">\<defaultPorts></span><span class="sxs-lookup"><span data-stu-id="e2184-108">\<defaultPorts></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2184-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2184-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2184-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e2184-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e2184-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e2184-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2184-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e2184-112">Attributes</span></span>  
 <span data-ttu-id="e2184-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e2184-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2184-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e2184-114">Child Elements</span></span>  
  
|<span data-ttu-id="e2184-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2184-115">Element</span></span>|<span data-ttu-id="e2184-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e2184-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2184-117">\<Добавить > из \<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="e2184-117">\<add> of \<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|<span data-ttu-id="e2184-118">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="e2184-118">A default communications endpoint that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2184-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e2184-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e2184-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="e2184-120">Element</span></span>|<span data-ttu-id="e2184-121">Описание</span><span class="sxs-lookup"><span data-stu-id="e2184-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e2184-122">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="e2184-122">\<useRequestHeadersForMetadataAddress></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|<span data-ttu-id="e2184-123">Список портов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e2184-123">A list of default ports.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e2184-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e2184-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
