---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 79022319944c4042c6f62a7521784b826b90d4ce
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="d192e-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="d192e-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="d192e-103">Регистрирует кэш воспроизведения токена службы или коллекции обработчик маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d192e-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="d192e-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="d192e-104">\<system.identityModel></span></span>  
<span data-ttu-id="d192e-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d192e-105">\<identityConfiguration></span></span>  
<span data-ttu-id="d192e-106">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="d192e-106">\<caches></span></span>  
<span data-ttu-id="d192e-107">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="d192e-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d192e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d192e-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d192e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d192e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d192e-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d192e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d192e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d192e-111">Attributes</span></span>  
  
|<span data-ttu-id="d192e-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d192e-112">Attribute</span></span>|<span data-ttu-id="d192e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d192e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d192e-114">type</span><span class="sxs-lookup"><span data-stu-id="d192e-114">type</span></span>|<span data-ttu-id="d192e-115">Тип, который является производным от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса.</span><span class="sxs-lookup"><span data-stu-id="d192e-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="d192e-116">Дополнительные сведения о том, как задать пользовательский `type`, в разделе [ссылок на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="d192e-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="d192e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d192e-117">Child Elements</span></span>  
 <span data-ttu-id="d192e-118">Нет</span><span class="sxs-lookup"><span data-stu-id="d192e-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d192e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d192e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d192e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="d192e-120">Element</span></span>|<span data-ttu-id="d192e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="d192e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d192e-122">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="d192e-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="d192e-123">Регистрирует кэши, используемая службой или коллекцию обработчика токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="d192e-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d192e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="d192e-124">Remarks</span></span>  
 <span data-ttu-id="d192e-125">Кэш воспроизведения токена используется для обнаружения воспроизводимой маркеры.</span><span class="sxs-lookup"><span data-stu-id="d192e-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="d192e-126">Обнаружение воспроизведения токенов включено по [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) элемент, указывающий максимальный срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="d192e-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d192e-127">Пример</span><span class="sxs-lookup"><span data-stu-id="d192e-127">Example</span></span>  
 <span data-ttu-id="d192e-128">Следующий код XML показана конфигурация пользовательского кэша для обнаружения воспроизводимой маркеры.</span><span class="sxs-lookup"><span data-stu-id="d192e-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d192e-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d192e-129">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [<span data-ttu-id="d192e-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="d192e-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
