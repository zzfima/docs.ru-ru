---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: 2e2159a73ca79fc362a8138eea95dbd173dafb11
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944299"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="ba536-101">\<Токенреплайдетектион ></span><span class="sxs-lookup"><span data-stu-id="ba536-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="ba536-102">Включает обнаружение воспроизведения маркеров и задает срок действия токенов.</span><span class="sxs-lookup"><span data-stu-id="ba536-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
 <span data-ttu-id="ba536-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="ba536-103">\<system.identityModel></span></span>  
<span data-ttu-id="ba536-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ba536-104">\<identityConfiguration></span></span>  
<span data-ttu-id="ba536-105">\<Токенреплайдетектион ></span><span class="sxs-lookup"><span data-stu-id="ba536-105">\<tokenReplayDetection></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba536-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba536-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="ba536-107">Тип</span><span class="sxs-lookup"><span data-stu-id="ba536-107">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba536-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba536-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ba536-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba536-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba536-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba536-110">Attributes</span></span>  
  
|<span data-ttu-id="ba536-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ba536-111">Attribute</span></span>|<span data-ttu-id="ba536-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ba536-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba536-113">enabled</span><span class="sxs-lookup"><span data-stu-id="ba536-113">enabled</span></span>|<span data-ttu-id="ba536-114">Значение типа, указывающее, включено ли обнаружение воспроизведения маркеров. значение true, чтобы включить обнаружение воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="ba536-114">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="ba536-115">експиратионпериод</span><span class="sxs-lookup"><span data-stu-id="ba536-115">expirationPeriod</span></span>|<span data-ttu-id="ba536-116">Значение <xref:System.TimeSpan> типа, указывающее максимальное количество времени, по истечении которого элемент считается просроченным и удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="ba536-116">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="ba536-117">Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="ba536-117">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba536-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba536-118">Child Elements</span></span>  
 <span data-ttu-id="ba536-119">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="ba536-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ba536-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba536-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ba536-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba536-121">Element</span></span>|<span data-ttu-id="ba536-122">Описание</span><span class="sxs-lookup"><span data-stu-id="ba536-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ba536-123">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ba536-123">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="ba536-124">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="ba536-124">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="ba536-125">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="ba536-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="ba536-126">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ba536-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba536-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="ba536-127">Remarks</span></span>  
 <span data-ttu-id="ba536-128">Элемент можно указать на уровне службы `<identityConfiguration>` в элементе или на уровне коллекции `<securityTokenHandlerConfiguration>` обработчика маркеров безопасности под элементом. `<tokenReplayDetection>`</span><span class="sxs-lookup"><span data-stu-id="ba536-128">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ba536-129">Параметры коллекции обработчиков маркеров переопределяют указанные в службе.</span><span class="sxs-lookup"><span data-stu-id="ba536-129">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="ba536-130">Тип кэша воспроизведения токенов задается [ \<элементом > tokenReplayCache](tokenreplaycache.md) .</span><span class="sxs-lookup"><span data-stu-id="ba536-130">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
