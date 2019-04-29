---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 1567c669b5e682a7a771d7bedc95a8effa474e36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790511"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="6796a-101">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="6796a-101">\<tokenReplayCache></span></span>
<span data-ttu-id="6796a-102">Регистрирует кэш повторного использования токенов службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="6796a-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="6796a-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6796a-103">\<system.identityModel></span></span>  
<span data-ttu-id="6796a-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6796a-104">\<identityConfiguration></span></span>  
<span data-ttu-id="6796a-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="6796a-105">\<caches></span></span>  
<span data-ttu-id="6796a-106">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="6796a-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6796a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6796a-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6796a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6796a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6796a-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6796a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6796a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6796a-110">Attributes</span></span>  
  
|<span data-ttu-id="6796a-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6796a-111">Attribute</span></span>|<span data-ttu-id="6796a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6796a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6796a-113">type</span><span class="sxs-lookup"><span data-stu-id="6796a-113">type</span></span>|<span data-ttu-id="6796a-114">Тип, который является производным от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса.</span><span class="sxs-lookup"><span data-stu-id="6796a-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="6796a-115">Дополнительные сведения о том, как задать пользовательский `type`, см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="6796a-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="6796a-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6796a-116">Child Elements</span></span>  
 <span data-ttu-id="6796a-117">Нет</span><span class="sxs-lookup"><span data-stu-id="6796a-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6796a-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6796a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6796a-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="6796a-119">Element</span></span>|<span data-ttu-id="6796a-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6796a-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6796a-121">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="6796a-121">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="6796a-122">Регистрирует кэши, используемые службы или коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="6796a-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6796a-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="6796a-123">Remarks</span></span>  
 <span data-ttu-id="6796a-124">Кэш повторного использования токенов используется для обнаружения переигранных токенов.</span><span class="sxs-lookup"><span data-stu-id="6796a-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="6796a-125">Обнаружение воспроизведения токенов включено по [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) элемент, который также указывает максимальный срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="6796a-125">Token replay detection is enabled by the [\<tokenReplayDetection>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6796a-126">Пример</span><span class="sxs-lookup"><span data-stu-id="6796a-126">Example</span></span>  
 <span data-ttu-id="6796a-127">Следующий код XML показана конфигурация пользовательского кэша за обнаружение повторно используемых токенов.</span><span class="sxs-lookup"><span data-stu-id="6796a-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6796a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="6796a-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="6796a-129">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="6796a-129">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
