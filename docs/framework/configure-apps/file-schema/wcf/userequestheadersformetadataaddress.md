---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: bcbf1c633e0796c6056759dfbb55014838e0e293
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151414"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="e7fd7-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="e7fd7-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="e7fd7-103">Включает получение сведений об адресе метаданных из заголовков сообщений запросов.</span><span class="sxs-lookup"><span data-stu-id="e7fd7-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="e7fd7-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="e7fd7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="e7fd7-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="e7fd7-105">\<behaviors></span></span>  
<span data-ttu-id="e7fd7-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="e7fd7-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="e7fd7-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e7fd7-107">\<behavior></span></span>  
<span data-ttu-id="e7fd7-108">\<useRequestHeadersForMetadataAddress ></span><span class="sxs-lookup"><span data-stu-id="e7fd7-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7fd7-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7fd7-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e7fd7-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e7fd7-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e7fd7-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e7fd7-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e7fd7-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e7fd7-112">Attributes</span></span>  
 <span data-ttu-id="e7fd7-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e7fd7-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e7fd7-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e7fd7-114">Child Elements</span></span>  
  
|<span data-ttu-id="e7fd7-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7fd7-115">Element</span></span>|<span data-ttu-id="e7fd7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e7fd7-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7fd7-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="e7fd7-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="e7fd7-118">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="e7fd7-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e7fd7-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e7fd7-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e7fd7-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="e7fd7-120">Element</span></span>|<span data-ttu-id="e7fd7-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="e7fd7-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e7fd7-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="e7fd7-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="e7fd7-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="e7fd7-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7fd7-124">См. также</span><span class="sxs-lookup"><span data-stu-id="e7fd7-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
