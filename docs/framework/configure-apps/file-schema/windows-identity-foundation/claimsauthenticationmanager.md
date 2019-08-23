---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 3602a4805e86833ba6070d801cef6758aaee8a5c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941831"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="6cb20-101">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="6cb20-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="6cb20-102">Регистрирует диспетчер проверки подлинности утверждений для входящих утверждений.</span><span class="sxs-lookup"><span data-stu-id="6cb20-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="6cb20-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="6cb20-103">\<system.identityModel></span></span>  
<span data-ttu-id="6cb20-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6cb20-104">\<identityConfiguration></span></span>  
<span data-ttu-id="6cb20-105">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="6cb20-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cb20-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6cb20-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6cb20-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6cb20-107">Attributes and Elements</span></span>  
 <span data-ttu-id="6cb20-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6cb20-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6cb20-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6cb20-109">Attributes</span></span>  
  
|<span data-ttu-id="6cb20-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6cb20-110">Attribute</span></span>|<span data-ttu-id="6cb20-111">Описание</span><span class="sxs-lookup"><span data-stu-id="6cb20-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6cb20-112">type</span><span class="sxs-lookup"><span data-stu-id="6cb20-112">type</span></span>|<span data-ttu-id="6cb20-113">Указывает пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса.</span><span class="sxs-lookup"><span data-stu-id="6cb20-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="6cb20-114">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="6cb20-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6cb20-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6cb20-115">Child Elements</span></span>  
 <span data-ttu-id="6cb20-116">`type` <xref:System.Security.Claims.ClaimsAuthenticationManager> Если атрибут отсутствует или атрибут <xref:System.Security.Claims.ClaimsAuthenticationManager> ссылаетсянакласс,элементнепринимаетдочерниеэлементы,однакоклассы,производныеот,могутопределятьдочерниеэлементыконфигурации.`<claimsAuthenticationManager>` `type`</span><span class="sxs-lookup"><span data-stu-id="6cb20-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6cb20-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6cb20-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6cb20-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="6cb20-118">Element</span></span>|<span data-ttu-id="6cb20-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6cb20-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6cb20-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="6cb20-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="6cb20-121">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="6cb20-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cb20-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="6cb20-122">Remarks</span></span>  
 <span data-ttu-id="6cb20-123">Поведение по умолчанию, предоставляемое <xref:System.Security.Claims.ClaimsAuthenticationManager> классом, отображает входящие утверждения.</span><span class="sxs-lookup"><span data-stu-id="6cb20-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="6cb20-124">Если атрибут не указан или `type` <xref:System.Security.Claims.ClaimsAuthenticationManager> атрибут`<claimsAuthenticationManager>` указывает класс, элемент не принимает дочерние элементы. `type`</span><span class="sxs-lookup"><span data-stu-id="6cb20-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="6cb20-125">Можно указать `type` атрибут для регистрации типа, производного <xref:System.Security.Claims.ClaimsAuthenticationManager> от класса, для реализации пользовательского поведения.</span><span class="sxs-lookup"><span data-stu-id="6cb20-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="6cb20-126">Производные классы могут поддерживать конфигурацию через дочерние `<claimsAuthenticationManager>` элементы элемента путем <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> переопределения метода для работы с этими элементами.</span><span class="sxs-lookup"><span data-stu-id="6cb20-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="6cb20-127">Схема, определенная для дочерних элементов, находится в конструкторе класса.</span><span class="sxs-lookup"><span data-stu-id="6cb20-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="6cb20-128">`<claimsAuthenticationManager>` Элемент<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> задает свойство.</span><span class="sxs-lookup"><span data-stu-id="6cb20-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6cb20-129">Пример</span><span class="sxs-lookup"><span data-stu-id="6cb20-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```
