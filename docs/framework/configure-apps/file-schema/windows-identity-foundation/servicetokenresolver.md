---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 1143717882652fc8a03947327b5f1ea89dde7373
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793813"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="97402-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="97402-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="97402-102">Регистрирует Сопоставитель токенов служб, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="97402-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="97402-103">Сопоставитель токенов служб используется для разрешения токена шифрования на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="97402-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="97402-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="97402-104">\<system.identityModel></span></span>  
<span data-ttu-id="97402-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="97402-105">\<identityConfiguration></span></span>  
<span data-ttu-id="97402-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="97402-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="97402-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="97402-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="97402-108">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="97402-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97402-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97402-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="97402-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="97402-110">Attributes and Elements</span></span>  
 <span data-ttu-id="97402-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="97402-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="97402-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="97402-112">Attributes</span></span>  
  
|<span data-ttu-id="97402-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="97402-113">Attribute</span></span>|<span data-ttu-id="97402-114">Описание</span><span class="sxs-lookup"><span data-stu-id="97402-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="97402-115">type</span><span class="sxs-lookup"><span data-stu-id="97402-115">type</span></span>|<span data-ttu-id="97402-116">Указывает тип Сопоставитель токенов служб.</span><span class="sxs-lookup"><span data-stu-id="97402-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="97402-117">Либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> типом или типом, который является производным от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="97402-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="97402-118">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [пользовательский тип ссылки].</span><span class="sxs-lookup"><span data-stu-id="97402-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="97402-119">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="97402-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="97402-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="97402-120">Child Elements</span></span>  
 <span data-ttu-id="97402-121">Нет</span><span class="sxs-lookup"><span data-stu-id="97402-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="97402-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="97402-122">Parent Elements</span></span>  
  
|<span data-ttu-id="97402-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="97402-123">Element</span></span>|<span data-ttu-id="97402-124">Описание</span><span class="sxs-lookup"><span data-stu-id="97402-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="97402-125">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="97402-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="97402-126">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="97402-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97402-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="97402-127">Remarks</span></span>  
 <span data-ttu-id="97402-128">Сопоставитель токенов служб можно использовать для разрешения токена шифрования на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="97402-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="97402-129">Он используется для извлечения ключа, который должен использоваться для расшифровки входящих маркеров.</span><span class="sxs-lookup"><span data-stu-id="97402-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="97402-130">Необходимо указать `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="97402-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="97402-131">Указанный тип может быть либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> или пользовательский тип, производный от <xref:System.IdentityModel.Selectors.SecurityTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="97402-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="97402-132">Некоторые обработчики маркеров позволяют пользователю указать параметры Сопоставитель токена службы в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="97402-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="97402-133">Параметры на отдельных обработчиков маркеров в переопределите указанных в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="97402-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97402-134">Указание `<serviceTokenResolver>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="97402-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="97402-135">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="97402-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97402-136">Пример</span><span class="sxs-lookup"><span data-stu-id="97402-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
