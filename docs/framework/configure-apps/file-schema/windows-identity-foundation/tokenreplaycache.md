---
title: '&lt;tokenReplayCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f388369d4dc2e590473ad98189ade70b77551b10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="f7015-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="f7015-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="f7015-103">Регистрирует кэш воспроизведения токена службы или коллекции обработчик маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="f7015-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="f7015-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="f7015-104">\<system.identityModel></span></span>  
<span data-ttu-id="f7015-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f7015-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f7015-106">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="f7015-106">\<caches></span></span>  
<span data-ttu-id="f7015-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="f7015-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7015-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7015-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7015-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f7015-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f7015-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f7015-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7015-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f7015-111">Attributes</span></span>  
  
|<span data-ttu-id="f7015-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f7015-112">Attribute</span></span>|<span data-ttu-id="f7015-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f7015-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7015-114">type</span><span class="sxs-lookup"><span data-stu-id="f7015-114">type</span></span>|<span data-ttu-id="f7015-115">Тип, который является производным от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса.</span><span class="sxs-lookup"><span data-stu-id="f7015-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="f7015-116">Дополнительные сведения о том, как задать пользовательский `type`, в разделе [ссылок на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="f7015-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="f7015-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f7015-117">Child Elements</span></span>  
 <span data-ttu-id="f7015-118">Нет</span><span class="sxs-lookup"><span data-stu-id="f7015-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7015-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f7015-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f7015-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="f7015-120">Element</span></span>|<span data-ttu-id="f7015-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="f7015-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7015-122">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="f7015-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="f7015-123">Регистрирует кэши, используемая службой или коллекцию обработчика токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="f7015-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7015-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7015-124">Remarks</span></span>  
 <span data-ttu-id="f7015-125">Кэш воспроизведения токена используется для обнаружения воспроизводимой маркеры.</span><span class="sxs-lookup"><span data-stu-id="f7015-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="f7015-126">Обнаружение воспроизведения токенов включено по [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) элемент, указывающий максимальный срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="f7015-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7015-127">Пример</span><span class="sxs-lookup"><span data-stu-id="f7015-127">Example</span></span>  
 <span data-ttu-id="f7015-128">Следующий код XML показана конфигурация пользовательского кэша для обнаружения воспроизводимой маркеры.</span><span class="sxs-lookup"><span data-stu-id="f7015-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7015-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f7015-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="f7015-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="f7015-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
