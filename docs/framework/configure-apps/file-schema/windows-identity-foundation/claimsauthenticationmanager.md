---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252095"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="b3998-101">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="b3998-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="b3998-102">Регистрирует диспетчер проверки подлинности утверждений для входящих утверждений.</span><span class="sxs-lookup"><span data-stu-id="b3998-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="b3998-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b3998-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b3998-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="b3998-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="b3998-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b3998-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="b3998-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimsAuthenticationManager >**</span><span class="sxs-lookup"><span data-stu-id="b3998-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3998-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3998-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b3998-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b3998-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b3998-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b3998-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b3998-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b3998-110">Attributes</span></span>  
  
|<span data-ttu-id="b3998-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b3998-111">Attribute</span></span>|<span data-ttu-id="b3998-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b3998-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b3998-113">type</span><span class="sxs-lookup"><span data-stu-id="b3998-113">type</span></span>|<span data-ttu-id="b3998-114">Указывает пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса.</span><span class="sxs-lookup"><span data-stu-id="b3998-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="b3998-115">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="b3998-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b3998-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b3998-116">Child Elements</span></span>  
 <span data-ttu-id="b3998-117">`type` <xref:System.Security.Claims.ClaimsAuthenticationManager> Если атрибут отсутствует или атрибут <xref:System.Security.Claims.ClaimsAuthenticationManager> ссылаетсянакласс,элементнепринимаетдочерниеэлементы,однакоклассы,производныеот,могутопределятьдочерниеэлементыконфигурации.`<claimsAuthenticationManager>` `type`</span><span class="sxs-lookup"><span data-stu-id="b3998-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b3998-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b3998-118">Parent Elements</span></span>  
  
|<span data-ttu-id="b3998-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="b3998-119">Element</span></span>|<span data-ttu-id="b3998-120">Описание</span><span class="sxs-lookup"><span data-stu-id="b3998-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b3998-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="b3998-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="b3998-122">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="b3998-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3998-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3998-123">Remarks</span></span>  
 <span data-ttu-id="b3998-124">Поведение по умолчанию, предоставляемое <xref:System.Security.Claims.ClaimsAuthenticationManager> классом, отображает входящие утверждения.</span><span class="sxs-lookup"><span data-stu-id="b3998-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="b3998-125">Если атрибут не указан или `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> атрибут`<claimsAuthenticationManager>` указывает класс, элемент не принимает дочерние элементы. `type`</span><span class="sxs-lookup"><span data-stu-id="b3998-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="b3998-126">Можно указать `type` атрибут для регистрации типа, производного <xref:System.Security.Claims.ClaimsAuthenticationManager> от класса, для реализации пользовательского поведения.</span><span class="sxs-lookup"><span data-stu-id="b3998-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="b3998-127">Производные классы могут поддерживать конфигурацию через дочерние `<claimsAuthenticationManager>` элементы элемента путем <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> переопределения метода для работы с этими элементами.</span><span class="sxs-lookup"><span data-stu-id="b3998-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="b3998-128">Схема, определенная для дочерних элементов, находится в конструкторе класса.</span><span class="sxs-lookup"><span data-stu-id="b3998-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="b3998-129">`<claimsAuthenticationManager>` Элемент<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> задает свойство.</span><span class="sxs-lookup"><span data-stu-id="b3998-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3998-130">Пример</span><span class="sxs-lookup"><span data-stu-id="b3998-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
