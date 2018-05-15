---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7f0cef2590bb301e6897aa4922454942ecdd0957
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="472fa-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="472fa-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="472fa-103">Включает обнаружение воспроизведения токенов и определяет время жизни токенов.</span><span class="sxs-lookup"><span data-stu-id="472fa-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="472fa-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="472fa-104">\<system.identityModel></span></span>  
<span data-ttu-id="472fa-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="472fa-105">\<identityConfiguration></span></span>  
<span data-ttu-id="472fa-106">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="472fa-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="472fa-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="472fa-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="472fa-108">Тип</span><span class="sxs-lookup"><span data-stu-id="472fa-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="472fa-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="472fa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="472fa-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="472fa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="472fa-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="472fa-111">Attributes</span></span>  
  
|<span data-ttu-id="472fa-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="472fa-112">Attribute</span></span>|<span data-ttu-id="472fa-113">Описание</span><span class="sxs-lookup"><span data-stu-id="472fa-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="472fa-114">enabled</span><span class="sxs-lookup"><span data-stu-id="472fa-114">enabled</span></span>|<span data-ttu-id="472fa-115">Значение, указывающее, включено ли обнаружение воспроизведения токенов; «true», чтобы включить токен обнаружения воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="472fa-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="472fa-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="472fa-116">expirationPeriod</span></span>|<span data-ttu-id="472fa-117">Объект <xref:System.TimeSpan> , указывающее максимальное количество времени, прежде чем элемент считается истек и удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="472fa-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="472fa-118">Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="472fa-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="472fa-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="472fa-119">Child Elements</span></span>  
 <span data-ttu-id="472fa-120">Нет</span><span class="sxs-lookup"><span data-stu-id="472fa-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="472fa-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="472fa-121">Parent Elements</span></span>  
  
|<span data-ttu-id="472fa-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="472fa-122">Element</span></span>|<span data-ttu-id="472fa-123">Описание</span><span class="sxs-lookup"><span data-stu-id="472fa-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="472fa-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="472fa-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="472fa-125">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="472fa-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="472fa-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="472fa-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="472fa-127">Обеспечивает настройку для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="472fa-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="472fa-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="472fa-128">Remarks</span></span>  
 <span data-ttu-id="472fa-129">A `<tokenReplayDetection>` элемент можно задать на уровне службы под `<identityConfiguration>` элемент, либо на уровне коллекции обработчик маркеров безопасности в разделе `<securityTokenHandlerConfiguration>` элемента.</span><span class="sxs-lookup"><span data-stu-id="472fa-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="472fa-130">Параметры в коллекцию обработчика токенов переопределяют алгоритмам, заданным в службе.</span><span class="sxs-lookup"><span data-stu-id="472fa-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="472fa-131">Тип кэша воспроизведения токена определяется [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="472fa-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
