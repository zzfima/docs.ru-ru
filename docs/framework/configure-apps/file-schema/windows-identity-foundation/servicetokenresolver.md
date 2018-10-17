---
title: '&lt;serviceTokenResolver&gt;'
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: d4b64e2c88e153834b7cf5a83bd6258b6dfd471f
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347531"
---
# <a name="ltservicetokenresolvergt"></a><span data-ttu-id="f915c-102">&lt;serviceTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="f915c-102">&lt;serviceTokenResolver&gt;</span></span>
<span data-ttu-id="f915c-103">Регистрирует Сопоставитель токенов служб, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="f915c-103">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f915c-104">Сопоставитель токенов служб используется для разрешения токена шифрования на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="f915c-104">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="f915c-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="f915c-105">\<system.identityModel></span></span>  
<span data-ttu-id="f915c-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f915c-106">\<identityConfiguration></span></span>  
<span data-ttu-id="f915c-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="f915c-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f915c-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f915c-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="f915c-109">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="f915c-109">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f915c-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f915c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f915c-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f915c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f915c-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f915c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f915c-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f915c-113">Attributes</span></span>  
  
|<span data-ttu-id="f915c-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f915c-114">Attribute</span></span>|<span data-ttu-id="f915c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="f915c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f915c-116">type</span><span class="sxs-lookup"><span data-stu-id="f915c-116">type</span></span>|<span data-ttu-id="f915c-117">Указывает тип Сопоставитель токенов служб.</span><span class="sxs-lookup"><span data-stu-id="f915c-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="f915c-118">Либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> типом или типом, который является производным от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="f915c-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="f915c-119">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [пользовательский тип ссылки].</span><span class="sxs-lookup"><span data-stu-id="f915c-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="f915c-120">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="f915c-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f915c-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f915c-121">Child Elements</span></span>  
 <span data-ttu-id="f915c-122">Нет</span><span class="sxs-lookup"><span data-stu-id="f915c-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f915c-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f915c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f915c-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="f915c-124">Element</span></span>|<span data-ttu-id="f915c-125">Описание</span><span class="sxs-lookup"><span data-stu-id="f915c-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f915c-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f915c-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="f915c-127">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="f915c-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f915c-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="f915c-128">Remarks</span></span>  
 <span data-ttu-id="f915c-129">Сопоставитель токенов служб можно использовать для разрешения токена шифрования на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="f915c-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="f915c-130">Он используется для извлечения ключа, который должен использоваться для расшифровки входящих маркеров.</span><span class="sxs-lookup"><span data-stu-id="f915c-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="f915c-131">Необходимо указать `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="f915c-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="f915c-132">Указанный тип может быть либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> или пользовательский тип, производный от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="f915c-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="f915c-133">Некоторые обработчики маркеров позволяют пользователю указать параметры Сопоставитель токена службы в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f915c-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="f915c-134">Параметры на отдельных обработчиков маркеров в переопределите указанных в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="f915c-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f915c-135">Указание `<serviceTokenResolver>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="f915c-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="f915c-136">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="f915c-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f915c-137">Пример</span><span class="sxs-lookup"><span data-stu-id="f915c-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
