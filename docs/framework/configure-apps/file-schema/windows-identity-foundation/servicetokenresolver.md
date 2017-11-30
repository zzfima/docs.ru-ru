---
title: '&lt;serviceTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 06e871ee31880a219d9105ff4ce667618bfb78f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="34453-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="34453-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="34453-103">Регистрирует Сопоставитель токена службы, используемой обработчиков в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="34453-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="34453-104">Распознавателю маркеров службы используется для разрешения маркера шифрования для входящих токенов и сообщения.</span><span class="sxs-lookup"><span data-stu-id="34453-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="34453-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="34453-105">\<system.identityModel></span></span>  
<span data-ttu-id="34453-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="34453-106">\<identityConfiguration></span></span>  
<span data-ttu-id="34453-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="34453-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="34453-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="34453-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="34453-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="34453-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34453-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="34453-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <serviceTokenResolver type=xs:string>  
        </serviceTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34453-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="34453-111">Attributes and Elements</span></span>  
 <span data-ttu-id="34453-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="34453-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34453-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="34453-113">Attributes</span></span>  
  
|<span data-ttu-id="34453-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="34453-114">Attribute</span></span>|<span data-ttu-id="34453-115">Описание</span><span class="sxs-lookup"><span data-stu-id="34453-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34453-116">type</span><span class="sxs-lookup"><span data-stu-id="34453-116">type</span></span>|<span data-ttu-id="34453-117">Указывает тип арбитр маркеров службы.</span><span class="sxs-lookup"><span data-stu-id="34453-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="34453-118">Либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> тип или тип, производный от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="34453-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="34453-119">Дополнительные сведения о способах указания `type` см. в разделе [пользовательский тип ссылки].</span><span class="sxs-lookup"><span data-stu-id="34453-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="34453-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="34453-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34453-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="34453-121">Child Elements</span></span>  
 <span data-ttu-id="34453-122">Нет</span><span class="sxs-lookup"><span data-stu-id="34453-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34453-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="34453-123">Parent Elements</span></span>  
  
|<span data-ttu-id="34453-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="34453-124">Element</span></span>|<span data-ttu-id="34453-125">Описание</span><span class="sxs-lookup"><span data-stu-id="34453-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34453-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="34453-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="34453-127">Обеспечивает настройку для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="34453-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34453-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="34453-128">Remarks</span></span>  
 <span data-ttu-id="34453-129">Распознавателю маркеров службы можно использовать для разрешения маркера шифрования на входящих токенов и сообщения.</span><span class="sxs-lookup"><span data-stu-id="34453-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="34453-130">Он используется для получения ключа, который должен использоваться для расшифровки входящих токенов.</span><span class="sxs-lookup"><span data-stu-id="34453-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="34453-131">Необходимо указать `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="34453-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="34453-132">Указанный тип может быть как <xref:System.IdentityModel.Selectors.SecurityTokenResolver> или пользовательский тип, который является производным от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="34453-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="34453-133">Некоторые обработчики маркеров позволяют задавать параметры арбитр маркеров службы в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34453-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="34453-134">Параметры на отдельных обработчиков маркеров переопределить указанных в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="34453-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="34453-135">Указание `<serviceTokenResolver>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="34453-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="34453-136">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="34453-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34453-137">Пример</span><span class="sxs-lookup"><span data-stu-id="34453-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
