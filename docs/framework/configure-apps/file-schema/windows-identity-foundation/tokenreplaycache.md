---
title: '&lt;tokenReplayCache&gt;'
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 1e89afc5764dbdb86e87d2307425299dff57c686
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525175"
---
# <a name="lttokenreplaycachegt"></a><span data-ttu-id="2ae10-102">&lt;tokenReplayCache&gt;</span><span class="sxs-lookup"><span data-stu-id="2ae10-102">&lt;tokenReplayCache&gt;</span></span>
<span data-ttu-id="2ae10-103">Регистрирует кэш повторного использования токенов службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="2ae10-103">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="2ae10-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="2ae10-104">\<system.identityModel></span></span>  
<span data-ttu-id="2ae10-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="2ae10-105">\<identityConfiguration></span></span>  
<span data-ttu-id="2ae10-106">\<caches></span><span class="sxs-lookup"><span data-stu-id="2ae10-106">\<caches></span></span>  
<span data-ttu-id="2ae10-107">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="2ae10-107">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae10-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ae10-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ae10-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2ae10-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2ae10-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ae10-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ae10-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ae10-111">Attributes</span></span>  
  
|<span data-ttu-id="2ae10-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2ae10-112">Attribute</span></span>|<span data-ttu-id="2ae10-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2ae10-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ae10-114">type</span><span class="sxs-lookup"><span data-stu-id="2ae10-114">type</span></span>|<span data-ttu-id="2ae10-115">Тип, который является производным от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса.</span><span class="sxs-lookup"><span data-stu-id="2ae10-115">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="2ae10-116">Дополнительные сведения о том, как задать пользовательский `type`, см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="2ae10-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="2ae10-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ae10-117">Child Elements</span></span>  
 <span data-ttu-id="2ae10-118">Нет</span><span class="sxs-lookup"><span data-stu-id="2ae10-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ae10-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ae10-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2ae10-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ae10-120">Element</span></span>|<span data-ttu-id="2ae10-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="2ae10-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ae10-122">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="2ae10-122">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="2ae10-123">Регистрирует кэши, используемые службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="2ae10-123">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ae10-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ae10-124">Remarks</span></span>  
 <span data-ttu-id="2ae10-125">Кэш повторного использования токенов используется для обнаружения переигранных токенов.</span><span class="sxs-lookup"><span data-stu-id="2ae10-125">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="2ae10-126">Обнаружение воспроизведения токенов включено по [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) элемент, который также указывает максимальный срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="2ae10-126">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ae10-127">Пример</span><span class="sxs-lookup"><span data-stu-id="2ae10-127">Example</span></span>  
 <span data-ttu-id="2ae10-128">Следующий код XML показана конфигурация пользовательского кэша за обнаружение повторно используемых токенов.</span><span class="sxs-lookup"><span data-stu-id="2ae10-128">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2ae10-129">См. также</span><span class="sxs-lookup"><span data-stu-id="2ae10-129">See also</span></span>
- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="2ae10-130">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="2ae10-130">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
