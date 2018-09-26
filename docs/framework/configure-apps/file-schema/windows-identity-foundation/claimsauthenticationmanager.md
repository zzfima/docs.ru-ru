---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 0ec7e44363f87e54eae97b70352f520fe87540be
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47074957"
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="18774-102">&lt;claimsAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="18774-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="18774-103">Регистрирует диспетчер аутентификации утверждений для входящих утверждений.</span><span class="sxs-lookup"><span data-stu-id="18774-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="18774-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="18774-104">\<system.identityModel></span></span>  
<span data-ttu-id="18774-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="18774-105">\<identityConfiguration></span></span>  
<span data-ttu-id="18774-106">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="18774-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18774-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18774-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="18774-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="18774-108">Attributes and Elements</span></span>  
 <span data-ttu-id="18774-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="18774-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="18774-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="18774-110">Attributes</span></span>  
  
|<span data-ttu-id="18774-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="18774-111">Attribute</span></span>|<span data-ttu-id="18774-112">Описание</span><span class="sxs-lookup"><span data-stu-id="18774-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="18774-113">type</span><span class="sxs-lookup"><span data-stu-id="18774-113">type</span></span>|<span data-ttu-id="18774-114">Задает пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса.</span><span class="sxs-lookup"><span data-stu-id="18774-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="18774-115">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [пользовательский тип ссылки].</span><span class="sxs-lookup"><span data-stu-id="18774-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="18774-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="18774-116">Child Elements</span></span>  
 <span data-ttu-id="18774-117">Если не `type` атрибут, или если `type` ссылки на атрибуты <xref:System.Security.Claims.ClaimsAuthenticationManager> класс, `<claimsAuthenticationManager>` элемент выполняет только дочерние элементы; тем не менее, классы, производные от <xref:System.Security.Claims.ClaimsAuthenticationManager> можно определить дочерние элементы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="18774-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="18774-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="18774-118">Parent Elements</span></span>  
  
|<span data-ttu-id="18774-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="18774-119">Element</span></span>|<span data-ttu-id="18774-120">Описание</span><span class="sxs-lookup"><span data-stu-id="18774-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="18774-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="18774-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="18774-122">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="18774-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18774-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="18774-123">Remarks</span></span>  
 <span data-ttu-id="18774-124">Поведение по умолчанию, предоставляемых <xref:System.Security.Claims.ClaimsAuthenticationManager> класс выводит входящие утверждения.</span><span class="sxs-lookup"><span data-stu-id="18774-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="18774-125">Если не `type` атрибут указан или если `type` атрибут задает <xref:System.Security.Claims.ClaimsAuthenticationManager> класс, `<claimsAuthenticationManager>` элемент выполняет только дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="18774-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="18774-126">Можно указать `type` атрибут для регистрации типа производным от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса, чтобы реализовать пользовательское поведение.</span><span class="sxs-lookup"><span data-stu-id="18774-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="18774-127">Производные классы могут поддерживает настройку с помощью дочерних элементов `<claimsAuthenticationManager>` элемент путем переопределения <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> метод для обработки этих элементов.</span><span class="sxs-lookup"><span data-stu-id="18774-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="18774-128">В схеме, определенной для дочерних элементов зависит от конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="18774-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="18774-129">`<claimsAuthenticationManager>` Наборов элементов <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="18774-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="18774-130">Пример</span><span class="sxs-lookup"><span data-stu-id="18774-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
