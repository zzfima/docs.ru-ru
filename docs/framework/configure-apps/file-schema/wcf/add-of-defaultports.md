---
title: <add> из <defaultPorts>
ms.date: 03/30/2017
ms.assetid: f162ce42-963b-4779-96a7-d6d8b4ea0d2f
ms.openlocfilehash: f5de2aa897a3bc37d08932451a2c7b94bc603b9e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400638"
---
# <a name="add-of-defaultports"></a><span data-ttu-id="098ed-102">\<Добавление > \<> дефаултпортс</span><span class="sxs-lookup"><span data-stu-id="098ed-102">\<add> of \<defaultPorts></span></span>
<span data-ttu-id="098ed-103">Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="098ed-103">A default communications endpoint that the client application listens to.</span></span>  
  
<span data-ttu-id="098ed-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="098ed-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="098ed-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="098ed-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="098ed-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="098ed-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="098ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="098ed-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="098ed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="098ed-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="098ed-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Усерекуессеадерсформетадатааддресс >** ](userequestheadersformetadataaddress.md)</span><span class="sxs-lookup"><span data-stu-id="098ed-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<useRequestHeadersForMetadataAddress>**](userequestheadersformetadataaddress.md)</span></span>\
<span data-ttu-id="098ed-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Дефаултпортс >** ](defaultports.md)</span><span class="sxs-lookup"><span data-stu-id="098ed-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultPorts>**](defaultports.md)</span></span>\
<span data-ttu-id="098ed-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="098ed-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="098ed-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="098ed-112">Syntax</span></span>  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add port="Integer"
         scheme="String" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="098ed-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="098ed-113">Attributes and Elements</span></span>  
 <span data-ttu-id="098ed-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="098ed-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="098ed-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="098ed-115">Attributes</span></span>  
  
|<span data-ttu-id="098ed-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="098ed-116">Attribute</span></span>|<span data-ttu-id="098ed-117">Описание</span><span class="sxs-lookup"><span data-stu-id="098ed-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="098ed-118">порт</span><span class="sxs-lookup"><span data-stu-id="098ed-118">port</span></span>|<span data-ttu-id="098ed-119">Целочисленное значение, определяющее номер COM-порта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="098ed-119">An integer that specifies the default communications port number</span></span>|  
|<span data-ttu-id="098ed-120">scheme</span><span class="sxs-lookup"><span data-stu-id="098ed-120">scheme</span></span>|<span data-ttu-id="098ed-121">Строка, в которой указана группа параметров протокола, связанных с COM-портом.</span><span class="sxs-lookup"><span data-stu-id="098ed-121">A string that specifies the group of protocol settings associated with a communications port.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="098ed-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="098ed-122">Child Elements</span></span>  
 <span data-ttu-id="098ed-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="098ed-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="098ed-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="098ed-124">Parent Elements</span></span>  
  
|<span data-ttu-id="098ed-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="098ed-125">Element</span></span>|<span data-ttu-id="098ed-126">Описание</span><span class="sxs-lookup"><span data-stu-id="098ed-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="098ed-127">\<Дефаултпортс ></span><span class="sxs-lookup"><span data-stu-id="098ed-127">\<defaultPorts></span></span>](defaultports.md)|<span data-ttu-id="098ed-128">Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.</span><span class="sxs-lookup"><span data-stu-id="098ed-128">A collection of default ports listing the default communications endpoints that the client application listens to.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="098ed-129">См. также</span><span class="sxs-lookup"><span data-stu-id="098ed-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.DefaultPortElement>
