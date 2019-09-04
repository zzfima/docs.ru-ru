---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 9f3a95fd0a39f199eaf13c7509aff22caa0e3b66
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251786"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="3a1be-101">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="3a1be-101">\<tokenReplayCache></span></span>
<span data-ttu-id="3a1be-102">Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="3a1be-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
<span data-ttu-id="3a1be-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3a1be-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3a1be-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="3a1be-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="3a1be-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3a1be-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="3a1be-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> кэшей**](caches.md)</span><span class="sxs-lookup"><span data-stu-id="3a1be-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<caches>**](caches.md)</span></span>\
<span data-ttu-id="3a1be-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<tokenReplayCache >**</span><span class="sxs-lookup"><span data-stu-id="3a1be-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayCache>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a1be-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a1be-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a1be-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3a1be-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3a1be-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3a1be-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a1be-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3a1be-111">Attributes</span></span>  
  
|<span data-ttu-id="3a1be-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3a1be-112">Attribute</span></span>|<span data-ttu-id="3a1be-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3a1be-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3a1be-114">type</span><span class="sxs-lookup"><span data-stu-id="3a1be-114">type</span></span>|<span data-ttu-id="3a1be-115">Тип, производный от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса.</span><span class="sxs-lookup"><span data-stu-id="3a1be-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="3a1be-116">Дополнительные сведения о том, как указать пользовательский `type`параметр, см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="3a1be-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="3a1be-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3a1be-117">Child Elements</span></span>  
 <span data-ttu-id="3a1be-118">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="3a1be-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3a1be-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3a1be-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3a1be-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a1be-120">Element</span></span>|<span data-ttu-id="3a1be-121">Описание</span><span class="sxs-lookup"><span data-stu-id="3a1be-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3a1be-122">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="3a1be-122">\<caches></span></span>](caches.md)|<span data-ttu-id="3a1be-123">Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="3a1be-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a1be-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="3a1be-124">Remarks</span></span>  
 <span data-ttu-id="3a1be-125">Кэш воспроизведения токенов используется для обнаружения воспроизводимых токенов.</span><span class="sxs-lookup"><span data-stu-id="3a1be-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="3a1be-126">Обнаружение воспроизведения токенов включено [ \<элементом токенреплайдетектион >](tokenreplaydetection.md) , который также указывает максимальный срок действия токенов.</span><span class="sxs-lookup"><span data-stu-id="3a1be-126">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a1be-127">Пример</span><span class="sxs-lookup"><span data-stu-id="3a1be-127">Example</span></span>  
 <span data-ttu-id="3a1be-128">В следующем коде XML показана конфигурация пользовательского кэша для обнаружения воспроизводимых токенов.</span><span class="sxs-lookup"><span data-stu-id="3a1be-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a1be-129">См. также</span><span class="sxs-lookup"><span data-stu-id="3a1be-129">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="3a1be-130">\<Токенреплайдетектион ></span><span class="sxs-lookup"><span data-stu-id="3a1be-130">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
