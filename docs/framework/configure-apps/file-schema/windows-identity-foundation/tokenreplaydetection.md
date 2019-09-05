---
title: <tokenReplayDetection>
ms.date: 03/30/2017
ms.assetid: ac3f588e-5f75-4275-b969-2d492ecc3b47
author: BrucePerlerMS
ms.openlocfilehash: a4454042e1d97fb3cc2d6f2735104dadda6e7b5a
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251774"
---
# <a name="tokenreplaydetection"></a><span data-ttu-id="05690-101">\<Токенреплайдетектион ></span><span class="sxs-lookup"><span data-stu-id="05690-101">\<tokenReplayDetection></span></span>
<span data-ttu-id="05690-102">Включает обнаружение воспроизведения маркеров и задает срок действия токенов.</span><span class="sxs-lookup"><span data-stu-id="05690-102">Enables token replay detection and specifies the expiration time for tokens.</span></span>  
  
<span data-ttu-id="05690-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="05690-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="05690-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="05690-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="05690-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="05690-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="05690-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Токенреплайдетектион >**</span><span class="sxs-lookup"><span data-stu-id="05690-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tokenReplayDetection>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05690-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05690-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <tokenReplayDetection enabled=xs:boolean expirationPeriod=TimeSpan>  
    </tokenReplayDetection>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="type"></a><span data-ttu-id="05690-108">Тип</span><span class="sxs-lookup"><span data-stu-id="05690-108">Type</span></span>  
 <xref:System.IdentityModel.Configuration.TokenReplayDetectionElement>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05690-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="05690-109">Attributes and Elements</span></span>  
 <span data-ttu-id="05690-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="05690-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05690-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="05690-111">Attributes</span></span>  
  
|<span data-ttu-id="05690-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="05690-112">Attribute</span></span>|<span data-ttu-id="05690-113">Описание</span><span class="sxs-lookup"><span data-stu-id="05690-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="05690-114">enabled</span><span class="sxs-lookup"><span data-stu-id="05690-114">enabled</span></span>|<span data-ttu-id="05690-115">Значение типа, указывающее, включено ли обнаружение воспроизведения маркеров. значение true, чтобы включить обнаружение воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="05690-115">A value that specifies whether token replay detection is enabled; "true" to enable token replay detection.</span></span>|  
|<span data-ttu-id="05690-116">експиратионпериод</span><span class="sxs-lookup"><span data-stu-id="05690-116">expirationPeriod</span></span>|<span data-ttu-id="05690-117">Значение <xref:System.TimeSpan> типа, указывающее максимальное количество времени, по истечении которого элемент считается просроченным и удаляется из кэша.</span><span class="sxs-lookup"><span data-stu-id="05690-117">A <xref:System.TimeSpan> that specifies the maximum amount of time before an item is considered expired and removed from the cache.</span></span>  <span data-ttu-id="05690-118">Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="05690-118">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05690-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="05690-119">Child Elements</span></span>  
 <span data-ttu-id="05690-120">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="05690-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05690-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="05690-121">Parent Elements</span></span>  
  
|<span data-ttu-id="05690-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="05690-122">Element</span></span>|<span data-ttu-id="05690-123">Описание</span><span class="sxs-lookup"><span data-stu-id="05690-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="05690-124">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="05690-124">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="05690-125">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="05690-125">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="05690-126">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="05690-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="05690-127">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="05690-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05690-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="05690-128">Remarks</span></span>  
 <span data-ttu-id="05690-129">Элемент можно указать на уровне службы `<identityConfiguration>` в элементе или на уровне коллекции `<securityTokenHandlerConfiguration>` обработчика маркеров безопасности под элементом. `<tokenReplayDetection>`</span><span class="sxs-lookup"><span data-stu-id="05690-129">A `<tokenReplayDetection>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="05690-130">Параметры коллекции обработчиков маркеров переопределяют указанные в службе.</span><span class="sxs-lookup"><span data-stu-id="05690-130">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="05690-131">Тип кэша воспроизведения токенов задается [ \<элементом > tokenReplayCache](tokenreplaycache.md) .</span><span class="sxs-lookup"><span data-stu-id="05690-131">The type of the token replay cache is specified by the [\<tokenReplayCache>](tokenreplaycache.md) element.</span></span>
