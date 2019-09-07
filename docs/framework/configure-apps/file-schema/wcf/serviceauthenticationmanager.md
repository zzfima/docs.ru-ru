---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399710"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="bf8e5-101">\<Сервицеаусентикатионманажер ></span><span class="sxs-lookup"><span data-stu-id="bf8e5-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="bf8e5-102">Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.</span><span class="sxs-lookup"><span data-stu-id="bf8e5-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="bf8e5-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bf8e5-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bf8e5-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bf8e5-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bf8e5-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bf8e5-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="bf8e5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bf8e5-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="bf8e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="bf8e5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="bf8e5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Сервицеаусентикатионманажер >**</span><span class="sxs-lookup"><span data-stu-id="bf8e5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf8e5-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf8e5-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf8e5-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bf8e5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bf8e5-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bf8e5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf8e5-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bf8e5-112">Attributes</span></span>  
  
|<span data-ttu-id="bf8e5-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bf8e5-113">Attribute</span></span>|<span data-ttu-id="bf8e5-114">Описание</span><span class="sxs-lookup"><span data-stu-id="bf8e5-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf8e5-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="bf8e5-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="bf8e5-116">Строка, в которой указан тип политики проверки подлинности для текущего поведения.</span><span class="sxs-lookup"><span data-stu-id="bf8e5-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf8e5-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bf8e5-117">Child Elements</span></span>  
 <span data-ttu-id="bf8e5-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="bf8e5-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf8e5-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bf8e5-119">Parent Elements</span></span>  
  
|<span data-ttu-id="bf8e5-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="bf8e5-120">Element</span></span>|<span data-ttu-id="bf8e5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="bf8e5-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf8e5-122">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="bf8e5-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="bf8e5-123">Указывает элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="bf8e5-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf8e5-124">См. также</span><span class="sxs-lookup"><span data-stu-id="bf8e5-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>
