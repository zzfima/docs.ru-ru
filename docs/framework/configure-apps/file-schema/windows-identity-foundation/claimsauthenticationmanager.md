---
title: '&lt;claimsAuthenticationManager&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: b7d68c2fe89b5ca56319df2f24fadd51f329f5ab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="e976d-102">&lt;claimsAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="e976d-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="e976d-103">Регистрирует диспетчер проверки подлинности утверждений входящие утверждения.</span><span class="sxs-lookup"><span data-stu-id="e976d-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="e976d-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="e976d-104">\<system.identityModel></span></span>  
<span data-ttu-id="e976d-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e976d-105">\<identityConfiguration></span></span>  
<span data-ttu-id="e976d-106">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="e976d-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e976d-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e976d-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e976d-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e976d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e976d-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e976d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e976d-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e976d-110">Attributes</span></span>  
  
|<span data-ttu-id="e976d-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e976d-111">Attribute</span></span>|<span data-ttu-id="e976d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e976d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e976d-113">type</span><span class="sxs-lookup"><span data-stu-id="e976d-113">type</span></span>|<span data-ttu-id="e976d-114">Задает пользовательский тип, который является производным от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса.</span><span class="sxs-lookup"><span data-stu-id="e976d-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="e976d-115">Дополнительные сведения о способах указания `type` см. в разделе [пользовательский тип ссылки].</span><span class="sxs-lookup"><span data-stu-id="e976d-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e976d-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e976d-116">Child Elements</span></span>  
 <span data-ttu-id="e976d-117">При наличии не `type` атрибут, или если `type` ссылки на атрибуты <xref:System.Security.Claims.ClaimsAuthenticationManager> класса `<claimsAuthenticationManager>` элемент не принимает дочерних элементов; Однако классы, производные от <xref:System.Security.Claims.ClaimsAuthenticationManager> можно определить дочерние элементы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e976d-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e976d-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e976d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e976d-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="e976d-119">Element</span></span>|<span data-ttu-id="e976d-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="e976d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e976d-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e976d-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="e976d-122">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="e976d-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e976d-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="e976d-123">Remarks</span></span>  
 <span data-ttu-id="e976d-124">Поведение по умолчанию, предоставленные с помощью <xref:System.Security.Claims.ClaimsAuthenticationManager> класс выводит входящих утверждений.</span><span class="sxs-lookup"><span data-stu-id="e976d-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="e976d-125">Если не `type` указан атрибут или если `type` атрибут задает <xref:System.Security.Claims.ClaimsAuthenticationManager> класса, `<claimsAuthenticationManager>` элемент не принимает дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="e976d-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="e976d-126">Можно указать `type` атрибут, чтобы зарегистрировать тип производным от <xref:System.Security.Claims.ClaimsAuthenticationManager> класса, чтобы реализовать пользовательское поведение.</span><span class="sxs-lookup"><span data-stu-id="e976d-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="e976d-127">Производные классы могут поддерживать конфигурацию с помощью дочерних элементов `<claimsAuthenticationManager>` элемент путем переопределения <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> метод для обработки этих элементов.</span><span class="sxs-lookup"><span data-stu-id="e976d-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="e976d-128">Схемы, определенных для дочерних элементов зависит от конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="e976d-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="e976d-129">`<claimsAuthenticationManager>` Наборы элементов <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="e976d-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e976d-130">Пример</span><span class="sxs-lookup"><span data-stu-id="e976d-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```
