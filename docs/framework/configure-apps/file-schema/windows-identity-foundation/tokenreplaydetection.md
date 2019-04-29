---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 4deeb1d84f2621adb7ff1b649a505138b6856ec1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790498"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="c402b-101">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="c402b-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="c402b-102">Включает обнаружение воспроизведения токенов и определяет срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="c402b-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="c402b-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c402b-103">\<system.identityModel></span></span>  
<span data-ttu-id="c402b-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c402b-104">\<identityConfiguration></span></span>  
<span data-ttu-id="c402b-105">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="c402b-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c402b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c402b-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="c402b-107">Тип</span><span class="sxs-lookup"><span data-stu-id="c402b-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c402b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c402b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c402b-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c402b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c402b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c402b-110">Attributes</span></span>  
  
|<span data-ttu-id="c402b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c402b-111">Attribute</span></span>|<span data-ttu-id="c402b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c402b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c402b-113">enabled</span><span class="sxs-lookup"><span data-stu-id="c402b-113">enabled</span></span>|<span data-ttu-id="c402b-114">Значение, указывающее, включено ли обнаружение воспроизведения токенов; «true», чтобы включить маркер обнаружения воспроизведения.</span><span class="sxs-lookup"><span data-stu-id="c402b-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="c402b-115">expirationPeriod</span><span class="sxs-lookup"><span data-stu-id="c402b-115">expirationPeriod</span></span>|<span data-ttu-id="c402b-116">Объект <xref:System.TimeSpan> , указывающий максимальное количество времени, прежде чем элемент считается устаревшим и удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="c402b-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="c402b-117">Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, см. в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="c402b-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c402b-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c402b-118">Child Elements</span></span>  
 <span data-ttu-id="c402b-119">Нет</span><span class="sxs-lookup"><span data-stu-id="c402b-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c402b-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c402b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c402b-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="c402b-121">Element</span></span>|<span data-ttu-id="c402b-122">Описание</span><span class="sxs-lookup"><span data-stu-id="c402b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c402b-123">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c402b-123">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="c402b-124">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="c402b-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="c402b-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="c402b-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="c402b-126">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="c402b-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c402b-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="c402b-127">Remarks</span></span>  
 <span data-ttu-id="c402b-128">Объект `<tokenReplayDetection>` на уровне службы может быть задан элемент `<identityConfiguration>` элемент или на уровне коллекции обработчиков токенов безопасности в разделе `<securityTokenHandlerConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="c402b-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="c402b-129">Переопределить параметры на коллекцию обработчиков токенов, теми, которые указаны в службе.</span><span class="sxs-lookup"><span data-stu-id="c402b-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="c402b-130">Тип кэша повторного использования токенов задается [ \<tokenReplayCache >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c402b-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md) element.</span></span>
