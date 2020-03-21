---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 0983380e553acfe246d6b987784d818b8ae85b17
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152584"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="d62e6-101">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="d62e6-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="d62e6-102">Регистрирует разрешителер маркеров службы, используемый обработчиками в коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="d62e6-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="d62e6-103">Разрешители токенов службы используются для разрешения маркера шифрования на входящих токенах и сообщениях.</span><span class="sxs-lookup"><span data-stu-id="d62e6-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="d62e6-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d62e6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d62e6-105">&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d62e6-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d62e6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d62e6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d62e6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="d62e6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="d62e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenhandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d62e6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="d62e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span><span class="sxs-lookup"><span data-stu-id="d62e6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d62e6-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d62e6-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d62e6-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d62e6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d62e6-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d62e6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d62e6-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d62e6-113">Attributes</span></span>  
  
|<span data-ttu-id="d62e6-114">attribute</span><span class="sxs-lookup"><span data-stu-id="d62e6-114">Attribute</span></span>|<span data-ttu-id="d62e6-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d62e6-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d62e6-116">type</span><span class="sxs-lookup"><span data-stu-id="d62e6-116">type</span></span>|<span data-ttu-id="d62e6-117">Определяет тип разрешительного маркера токенов службы.</span><span class="sxs-lookup"><span data-stu-id="d62e6-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="d62e6-118"><xref:System.IdentityModel.Selectors.SecurityTokenResolver> Тип или тип, который вытекает <xref:System.IdentityModel.Selectors.SecurityTokenResolver> из класса.</span><span class="sxs-lookup"><span data-stu-id="d62e6-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="d62e6-119">Для получения дополнительной информации `type` о том, как указать атрибут, см.</span><span class="sxs-lookup"><span data-stu-id="d62e6-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="d62e6-120">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="d62e6-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d62e6-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d62e6-121">Child Elements</span></span>  
 <span data-ttu-id="d62e6-122">None</span><span class="sxs-lookup"><span data-stu-id="d62e6-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d62e6-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d62e6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d62e6-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="d62e6-124">Element</span></span>|<span data-ttu-id="d62e6-125">Описание</span><span class="sxs-lookup"><span data-stu-id="d62e6-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d62e6-126">\<securityTokenhandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="d62e6-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="d62e6-127">Обеспечивает конфигурацию для сбора обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d62e6-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d62e6-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="d62e6-128">Remarks</span></span>  
 <span data-ttu-id="d62e6-129">Разрешители токенов службы могут быть использованы для разрешения маркера шифрования на входящих токенах и сообщениях.</span><span class="sxs-lookup"><span data-stu-id="d62e6-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="d62e6-130">Он используется для получения ключа, который должен быть использован для расшифровки входящих токенов.</span><span class="sxs-lookup"><span data-stu-id="d62e6-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="d62e6-131">Необходимо указать `type` атрибут.</span><span class="sxs-lookup"><span data-stu-id="d62e6-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="d62e6-132">Указанный тип может <xref:System.IdentityModel.Selectors.SecurityTokenResolver> быть либо или пользовательским <xref:System.IdentityModel.Selectors.SecurityTokenResolver> типом, который вытекает из класса.</span><span class="sxs-lookup"><span data-stu-id="d62e6-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="d62e6-133">Некоторые обработчики маркеров позволяют указать настройки разрешителя маркеров службы в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d62e6-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="d62e6-134">Настройки отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d62e6-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d62e6-135">Определение элемента `<serviceTokenResolver>` в качестве элемента ребенка [ \<идентификационных конфигураций>](identityconfiguration.md) элемента было изуродовано, но по-прежнему поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="d62e6-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="d62e6-136">Настройки элемента `<securityTokenHandlerConfiguration>` переопределяют элементы на элементе. `<identityConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="d62e6-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d62e6-137">Пример</span><span class="sxs-lookup"><span data-stu-id="d62e6-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
