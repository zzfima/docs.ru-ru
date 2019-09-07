---
title: <useRequestHeadersForMetadataAddress>
ms.date: 03/30/2017
ms.assetid: 679f0eae-f353-44d1-b42d-a9e247509774
ms.openlocfilehash: e0b46953924a3825420b719085e1210981da643a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399206"
---
# <a name="userequestheadersformetadataaddress"></a><span data-ttu-id="a0af9-101">\<Усерекуессеадерсформетадатааддресс ></span><span class="sxs-lookup"><span data-stu-id="a0af9-101">\<useRequestHeadersForMetadataAddress></span></span>
<span data-ttu-id="a0af9-102">Включает получение сведений об адресе метаданных из заголовков сообщений запросов.</span><span class="sxs-lookup"><span data-stu-id="a0af9-102">Enables the retrieval of metadata address information from the request message headers.</span></span>  
  
<span data-ttu-id="a0af9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a0af9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a0af9-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="a0af9-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="a0af9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a0af9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="a0af9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a0af9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="a0af9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="a0af9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="a0af9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Усерекуессеадерсформетадатааддресс >**</span><span class="sxs-lookup"><span data-stu-id="a0af9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<useRequestHeadersForMetadataAddress>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0af9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0af9-109">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a0af9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a0af9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a0af9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a0af9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a0af9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a0af9-112">Attributes</span></span>  
 <span data-ttu-id="a0af9-113">Нет.</span><span class="sxs-lookup"><span data-stu-id="a0af9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a0af9-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a0af9-114">Child Elements</span></span>  
  
|<span data-ttu-id="a0af9-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0af9-115">Element</span></span>|<span data-ttu-id="a0af9-116">Описание</span><span class="sxs-lookup"><span data-stu-id="a0af9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0af9-117">\<Дефаултпортс ></span><span class="sxs-lookup"><span data-stu-id="a0af9-117">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="a0af9-118">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="a0af9-118">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a0af9-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a0af9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="a0af9-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="a0af9-120">Element</span></span>|<span data-ttu-id="a0af9-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a0af9-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a0af9-122">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="a0af9-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="a0af9-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="a0af9-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a0af9-124">См. также</span><span class="sxs-lookup"><span data-stu-id="a0af9-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseRequestHeadersForMetadataAddressElement>
