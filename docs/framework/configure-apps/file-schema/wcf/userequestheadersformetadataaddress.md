---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 969461d0e5bdc9f8c49b7a019a6000af5af77eec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121190"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="cb4db-101">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="cb4db-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="cb4db-102">Включает получение сведений об адресе метаданных из заголовков сообщений запросов.</span><span class="sxs-lookup"><span data-stu-id="cb4db-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="cb4db-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="cb4db-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="cb4db-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="cb4db-104">\<behaviors></span></span>  
<span data-ttu-id="cb4db-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="cb4db-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="cb4db-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="cb4db-106">\<behavior></span></span>  
<span data-ttu-id="cb4db-107">\<useRequestHeadersForMetadataAddress></span><span class="sxs-lookup"><span data-stu-id="cb4db-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb4db-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb4db-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb4db-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb4db-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cb4db-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb4db-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb4db-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb4db-111">Attributes</span></span>  
 <span data-ttu-id="cb4db-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cb4db-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cb4db-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb4db-113">Child Elements</span></span>  
  
|<span data-ttu-id="cb4db-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb4db-114">Element</span></span>|<span data-ttu-id="cb4db-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cb4db-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb4db-116">\<defaultPorts ></span><span class="sxs-lookup"><span data-stu-id="cb4db-116">\<defaultPorts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultports.md)|<span data-ttu-id="cb4db-117">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="cb4db-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb4db-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb4db-118">Parent Elements</span></span>  
  
|<span data-ttu-id="cb4db-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb4db-119">Element</span></span>|<span data-ttu-id="cb4db-120">Описание</span><span class="sxs-lookup"><span data-stu-id="cb4db-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb4db-121">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="cb4db-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="cb4db-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="cb4db-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cb4db-123">См. также</span><span class="sxs-lookup"><span data-stu-id="cb4db-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
