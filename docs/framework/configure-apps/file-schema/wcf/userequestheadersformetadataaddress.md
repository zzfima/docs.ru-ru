---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: 84310d4ae5e04e76e4484f4fc606c9896239c776
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940549"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="246ae-101">\<Усерекуессеадерсформетадатааддресс ></span><span class="sxs-lookup"><span data-stu-id="246ae-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="246ae-102">Включает получение сведений об адресе метаданных из заголовков сообщений запросов.</span><span class="sxs-lookup"><span data-stu-id="246ae-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="246ae-103">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="246ae-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="246ae-104">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="246ae-104">\<behaviors></span></span>  
<span data-ttu-id="246ae-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="246ae-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="246ae-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="246ae-106">\<behavior></span></span>  
<span data-ttu-id="246ae-107">\<Усерекуессеадерсформетадатааддресс ></span><span class="sxs-lookup"><span data-stu-id="246ae-107">\<useRequestHeadersForMetadataAddress></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="246ae-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="246ae-108">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="246ae-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="246ae-109">Attributes and Elements</span></span>  
 <span data-ttu-id="246ae-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="246ae-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="246ae-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="246ae-111">Attributes</span></span>  
 <span data-ttu-id="246ae-112">Нет.</span><span class="sxs-lookup"><span data-stu-id="246ae-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="246ae-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="246ae-113">Child Elements</span></span>  
  
|<span data-ttu-id="246ae-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="246ae-114">Element</span></span>|<span data-ttu-id="246ae-115">Описание</span><span class="sxs-lookup"><span data-stu-id="246ae-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="246ae-116">\<Дефаултпортс ></span><span class="sxs-lookup"><span data-stu-id="246ae-116">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="246ae-117">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="246ae-117">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="246ae-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="246ae-118">Parent Elements</span></span>  
  
|<span data-ttu-id="246ae-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="246ae-119">Element</span></span>|<span data-ttu-id="246ae-120">Описание</span><span class="sxs-lookup"><span data-stu-id="246ae-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="246ae-121">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="246ae-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="246ae-122">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="246ae-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="246ae-123">См. также</span><span class="sxs-lookup"><span data-stu-id="246ae-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
