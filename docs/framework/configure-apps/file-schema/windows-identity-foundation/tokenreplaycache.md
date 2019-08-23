---
title: <tokenReplayCache>
ms.date: 03/30/2017
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
author: BrucePerlerMS
ms.openlocfilehash: 5747a4cfa93118dd41292904b168bbef02fec415
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944081"
---
# <a name="tokenreplaycache"></a><span data-ttu-id="42cd5-101">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="42cd5-101">\<tokenReplayCache></span></span>
<span data-ttu-id="42cd5-102">Регистрирует кэш воспроизведения токенов с помощью службы или коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="42cd5-102">Registers a token replay cache with a service or a security token handler collection.</span></span>  
  
 <span data-ttu-id="42cd5-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="42cd5-103">\<system.identityModel></span></span>  
<span data-ttu-id="42cd5-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="42cd5-104">\<identityConfiguration></span></span>  
<span data-ttu-id="42cd5-105">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="42cd5-105">\<caches></span></span>  
<span data-ttu-id="42cd5-106">\<tokenReplayCache ></span><span class="sxs-lookup"><span data-stu-id="42cd5-106">\<tokenReplayCache></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42cd5-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42cd5-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42cd5-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="42cd5-108">Attributes and Elements</span></span>  
 <span data-ttu-id="42cd5-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="42cd5-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42cd5-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="42cd5-110">Attributes</span></span>  
  
|<span data-ttu-id="42cd5-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="42cd5-111">Attribute</span></span>|<span data-ttu-id="42cd5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="42cd5-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42cd5-113">type</span><span class="sxs-lookup"><span data-stu-id="42cd5-113">type</span></span>|<span data-ttu-id="42cd5-114">Тип, производный от <xref:System.IdentityModel.Tokens.TokenReplayCache> класса.</span><span class="sxs-lookup"><span data-stu-id="42cd5-114">A type that derives from the <xref:System.IdentityModel.Tokens.TokenReplayCache> class.</span></span> <span data-ttu-id="42cd5-115">Дополнительные сведения о том, как указать пользовательский `type`параметр, см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="42cd5-115">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>
  
### <a name="child-elements"></a><span data-ttu-id="42cd5-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="42cd5-116">Child Elements</span></span>  
 <span data-ttu-id="42cd5-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="42cd5-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42cd5-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="42cd5-118">Parent Elements</span></span>  
  
|<span data-ttu-id="42cd5-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="42cd5-119">Element</span></span>|<span data-ttu-id="42cd5-120">Описание</span><span class="sxs-lookup"><span data-stu-id="42cd5-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42cd5-121">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="42cd5-121">\<caches></span></span>](caches.md)|<span data-ttu-id="42cd5-122">Регистрирует кэши, используемые службой или коллекцией обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="42cd5-122">Registers the caches used by a service or a security token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42cd5-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="42cd5-123">Remarks</span></span>  
 <span data-ttu-id="42cd5-124">Кэш воспроизведения токенов используется для обнаружения воспроизводимых токенов.</span><span class="sxs-lookup"><span data-stu-id="42cd5-124">The token replay cache is used to detect replayed tokens.</span></span> <span data-ttu-id="42cd5-125">Обнаружение воспроизведения токенов включено [ \<элементом токенреплайдетектион >](tokenreplaydetection.md) , который также указывает максимальный срок действия токенов.</span><span class="sxs-lookup"><span data-stu-id="42cd5-125">Token replay detection is enabled by the [\<tokenReplayDetection>](tokenreplaydetection.md) element, which also specifies the maximum expiration time for tokens.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42cd5-126">Пример</span><span class="sxs-lookup"><span data-stu-id="42cd5-126">Example</span></span>  
 <span data-ttu-id="42cd5-127">В следующем коде XML показана конфигурация пользовательского кэша для обнаружения воспроизводимых токенов.</span><span class="sxs-lookup"><span data-stu-id="42cd5-127">The following XML shows the configuration of a custom cache for detecting replayed tokens.</span></span>  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42cd5-128">См. также</span><span class="sxs-lookup"><span data-stu-id="42cd5-128">See also</span></span>

- <xref:System.IdentityModel.Tokens.TokenReplayCache>
- [<span data-ttu-id="42cd5-129">\<Токенреплайдетектион ></span><span class="sxs-lookup"><span data-stu-id="42cd5-129">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)
