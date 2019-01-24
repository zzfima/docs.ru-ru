---
title: '&lt;useRequestHeadersForMetadataAddress&gt;'
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 6c03057fca23b037702c702b9a574045ebb302b4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656640"
---
# <a name="ltuserequestheadersformetadataaddressgt"></a><span data-ttu-id="91398-102">&lt;useRequestHeadersForMetadataAddress&gt;</span><span class="sxs-lookup"><span data-stu-id="91398-102">&lt;useRequestHeadersForMetadataAddress&gt;</span></span>
<span data-ttu-id="91398-103">Включает получение сведений об адресе метаданных из заголовков сообщений запросов.</span><span class="sxs-lookup"><span data-stu-id="91398-103">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="91398-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="91398-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="91398-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="91398-105">\<behaviors></span></span>  
<span data-ttu-id="91398-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="91398-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="91398-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="91398-107">\<behavior></span></span>  
<span data-ttu-id="91398-108">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="91398-108">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91398-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91398-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91398-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="91398-110">Attributes and Elements</span></span>  
 <span data-ttu-id="91398-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="91398-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91398-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="91398-112">Attributes</span></span>  
 <span data-ttu-id="91398-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="91398-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="91398-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="91398-114">Child Elements</span></span>  
  
|<span data-ttu-id="91398-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="91398-115">Element</span></span>|<span data-ttu-id="91398-116">Описание</span><span class="sxs-lookup"><span data-stu-id="91398-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91398-117">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="91398-117">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="91398-118">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="91398-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="91398-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="91398-119">Parent Elements</span></span>  
  
|<span data-ttu-id="91398-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="91398-120">Element</span></span>|<span data-ttu-id="91398-121">Описание</span><span class="sxs-lookup"><span data-stu-id="91398-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="91398-122">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="91398-122">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="91398-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="91398-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="91398-124">См. также</span><span class="sxs-lookup"><span data-stu-id="91398-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
