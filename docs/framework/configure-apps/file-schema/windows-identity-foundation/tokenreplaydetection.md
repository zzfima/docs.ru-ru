---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: bd2272cb83dc0183d5008cfa178e11783f51ca2d
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47205935"
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="f7e6c-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="f7e6c-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="f7e6c-103">Включает обнаружение воспроизведения токенов и определяет срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="f7e6c-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="f7e6c-104">\<system.identityModel></span></span>  
<span data-ttu-id="f7e6c-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f7e6c-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f7e6c-106">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="f7e6c-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e6c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7e6c-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="f7e6c-108">Тип</span><span class="sxs-lookup"><span data-stu-id="f7e6c-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7e6c-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f7e6c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f7e6c-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7e6c-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f7e6c-111">Attributes</span></span>  
  
|<span data-ttu-id="f7e6c-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f7e6c-112">Attribute</span></span>|<span data-ttu-id="f7e6c-113">Описание</span><span class="sxs-lookup"><span data-stu-id="f7e6c-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7e6c-114">enabled</span><span class="sxs-lookup"><span data-stu-id="f7e6c-114">enabled</span></span>|<span data-ttu-id="f7e6c-115">Значение, указывающее, включено ли обнаружение воспроизведения токенов; «true», чтобы включить маркер обнаружения воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="f7e6c-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="f7e6c-116">expirationPeriod</span></span>|<span data-ttu-id="f7e6c-117">Объект <xref:System.TimeSpan> , указывающий максимальное количество времени, прежде чем элемент считается устаревшим и удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="f7e6c-118">Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, см. в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="f7e6c-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7e6c-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f7e6c-119">Child Elements</span></span>  
 <span data-ttu-id="f7e6c-120">Нет</span><span class="sxs-lookup"><span data-stu-id="f7e6c-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7e6c-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f7e6c-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f7e6c-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="f7e6c-122">Element</span></span>|<span data-ttu-id="f7e6c-123">Описание</span><span class="sxs-lookup"><span data-stu-id="f7e6c-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7e6c-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f7e6c-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="f7e6c-125">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="f7e6c-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f7e6c-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="f7e6c-127">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7e6c-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7e6c-128">Remarks</span></span>  
 <span data-ttu-id="f7e6c-129">Объект `<tokenReplayDetection>` на уровне службы может быть задан элемент `<identityConfiguration>` элемент или на уровне коллекции обработчиков токенов безопасности в разделе `<securityTokenHandlerConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="f7e6c-130">Переопределить параметры на коллекцию обработчиков токенов, теми, которые указаны в службе.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="f7e6c-131">Тип кэша повторного использования токенов задается [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="f7e6c-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
