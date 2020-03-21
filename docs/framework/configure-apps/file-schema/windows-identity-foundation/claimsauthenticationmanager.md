---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152753"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="039a6-101">\<претензииAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="039a6-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="039a6-102">Регистрирует менеджера проверки подлинности претензий для входящих претензий.</span><span class="sxs-lookup"><span data-stu-id="039a6-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="039a6-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="039a6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="039a6-104">&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="039a6-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="039a6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="039a6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="039a6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<претензииAuthenticationManager>**</span><span class="sxs-lookup"><span data-stu-id="039a6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="039a6-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="039a6-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="039a6-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="039a6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="039a6-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="039a6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="039a6-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="039a6-110">Attributes</span></span>  
  
|<span data-ttu-id="039a6-111">attribute</span><span class="sxs-lookup"><span data-stu-id="039a6-111">Attribute</span></span>|<span data-ttu-id="039a6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="039a6-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="039a6-113">type</span><span class="sxs-lookup"><span data-stu-id="039a6-113">type</span></span>|<span data-ttu-id="039a6-114">Определяет пользовательский тип, который вытекает <xref:System.Security.Claims.ClaimsAuthenticationManager> из класса.</span><span class="sxs-lookup"><span data-stu-id="039a6-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="039a6-115">Для получения дополнительной информации `type` о том, как указать атрибут, см.</span><span class="sxs-lookup"><span data-stu-id="039a6-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="039a6-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="039a6-116">Child Elements</span></span>  
 <span data-ttu-id="039a6-117">`type` Если нет атрибута, или `type` если атрибут <xref:System.Security.Claims.ClaimsAuthenticationManager> ссылается `<claimsAuthenticationManager>` на класс, элемент не принимает элементы ребенка; однако классы, <xref:System.Security.Claims.ClaimsAuthenticationManager> полученные из элементов конфигурации ребенка, могут определять элементы конфигурации ребенка.</span><span class="sxs-lookup"><span data-stu-id="039a6-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="039a6-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="039a6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="039a6-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="039a6-119">Element</span></span>|<span data-ttu-id="039a6-120">Описание</span><span class="sxs-lookup"><span data-stu-id="039a6-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="039a6-121">\<идентичностьНастройка></span><span class="sxs-lookup"><span data-stu-id="039a6-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="039a6-122">Определяет настройки удостоверения уровня обслуживания.</span><span class="sxs-lookup"><span data-stu-id="039a6-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="039a6-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="039a6-123">Remarks</span></span>  
 <span data-ttu-id="039a6-124">Поведение по умолчанию, предоставляемое через класс, <xref:System.Security.Claims.ClaimsAuthenticationManager> перекликается с входящими претензиями.</span><span class="sxs-lookup"><span data-stu-id="039a6-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="039a6-125">Если `type` атрибут не указан `type` или если атрибут <xref:System.Security.Claims.ClaimsAuthenticationManager> определяет класс, `<claimsAuthenticationManager>` элемент не принимает элементы ребенка.</span><span class="sxs-lookup"><span data-stu-id="039a6-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="039a6-126">Можно указать `type` атрибут для регистрации типа, полученного из <xref:System.Security.Claims.ClaimsAuthenticationManager> класса, для реализации пользовательского поведения.</span><span class="sxs-lookup"><span data-stu-id="039a6-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="039a6-127">Полученные классы могут поддерживать конфигурацию через элемент детского элемента, `<claimsAuthenticationManager>` переопределяя <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> метод обработки этих элементов.</span><span class="sxs-lookup"><span data-stu-id="039a6-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="039a6-128">Схема, определенная для элементов ребенка, до дизайнера класса.</span><span class="sxs-lookup"><span data-stu-id="039a6-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="039a6-129">Элемент `<claimsAuthenticationManager>` устанавливает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="039a6-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="039a6-130">Пример</span><span class="sxs-lookup"><span data-stu-id="039a6-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```
