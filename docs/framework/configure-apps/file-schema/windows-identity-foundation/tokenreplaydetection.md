---
title: '&lt;tokenReplayDetection&gt;'
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: bd2272cb83dc0183d5008cfa178e11783f51ca2d
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2018
ms.locfileid: "48031988"
---
# <a name="lttokenreplaydetectiongt"></a><span data-ttu-id="6299a-102">&lt;tokenReplayDetection&gt;</span><span class="sxs-lookup"><span data-stu-id="6299a-102">&lt;tokenReplayDetection&gt;</span></span>
<span data-ttu-id="6299a-103">Включает обнаружение воспроизведения токенов и определяет срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="6299a-103">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="6299a-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="6299a-104">\<system.identityModel></span></span>  
<span data-ttu-id="6299a-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6299a-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6299a-106">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="6299a-106">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6299a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6299a-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="6299a-108">Тип</span><span class="sxs-lookup"><span data-stu-id="6299a-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6299a-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6299a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6299a-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6299a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6299a-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6299a-111">Attributes</span></span>  
  
|<span data-ttu-id="6299a-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6299a-112">Attribute</span></span>|<span data-ttu-id="6299a-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6299a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6299a-114">enabled</span><span class="sxs-lookup"><span data-stu-id="6299a-114">enabled</span></span>|<span data-ttu-id="6299a-115">Значение, указывающее, включено ли обнаружение воспроизведения токенов; «true», чтобы включить маркер обнаружения воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="6299a-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="6299a-116">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="6299a-116">expirationPeriod</span></span>|<span data-ttu-id="6299a-117">Объект <xref:System.TimeSpan> , указывающий максимальное количество времени, прежде чем элемент считается устаревшим и удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="6299a-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="6299a-118">Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, см. в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="6299a-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6299a-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6299a-119">Child Elements</span></span>  
 <span data-ttu-id="6299a-120">Нет</span><span class="sxs-lookup"><span data-stu-id="6299a-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6299a-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6299a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="6299a-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="6299a-122">Element</span></span>|<span data-ttu-id="6299a-123">Описание</span><span class="sxs-lookup"><span data-stu-id="6299a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6299a-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6299a-124">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="6299a-125">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="6299a-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="6299a-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6299a-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="6299a-127">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="6299a-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6299a-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="6299a-128">Remarks</span></span>  
 <span data-ttu-id="6299a-129">Объект `<tokenReplayDetection>` на уровне службы может быть задан элемент `<identityConfiguration>` элемент или на уровне коллекции обработчиков токенов безопасности в разделе `<securityTokenHandlerConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="6299a-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="6299a-130">Переопределить параметры на коллекцию обработчиков токенов, теми, которые указаны в службе.</span><span class="sxs-lookup"><span data-stu-id="6299a-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="6299a-131">Тип кэша повторного использования токенов задается [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="6299a-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
