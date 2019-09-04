---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 30a53c11b551623311f7ca3f957143fc702568a1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251852"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="857bf-101">\<Сервицетокенресолвер ></span><span class="sxs-lookup"><span data-stu-id="857bf-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="857bf-102">Регистрирует сопоставитель маркеров службы, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="857bf-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="857bf-103">Сопоставитель токенов службы используется для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="857bf-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="857bf-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="857bf-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="857bf-105">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="857bf-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="857bf-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="857bf-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="857bf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="857bf-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="857bf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Секурититокенхандлерконфигуратион >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="857bf-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="857bf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Сервицетокенресолвер >**</span><span class="sxs-lookup"><span data-stu-id="857bf-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="857bf-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="857bf-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="857bf-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="857bf-111">Attributes and Elements</span></span>  
 <span data-ttu-id="857bf-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="857bf-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="857bf-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="857bf-113">Attributes</span></span>  
  
|<span data-ttu-id="857bf-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="857bf-114">Attribute</span></span>|<span data-ttu-id="857bf-115">Описание</span><span class="sxs-lookup"><span data-stu-id="857bf-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="857bf-116">type</span><span class="sxs-lookup"><span data-stu-id="857bf-116">type</span></span>|<span data-ttu-id="857bf-117">Указывает тип сопоставителя токенов службы.</span><span class="sxs-lookup"><span data-stu-id="857bf-117">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="857bf-118">Либо тип, либо тип, производный <xref:System.IdentityModel.Selectors.SecurityTokenResolver> от класса. <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="857bf-118">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="857bf-119">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="857bf-119">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="857bf-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="857bf-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="857bf-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="857bf-121">Child Elements</span></span>  
 <span data-ttu-id="857bf-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="857bf-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="857bf-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="857bf-123">Parent Elements</span></span>  
  
|<span data-ttu-id="857bf-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="857bf-124">Element</span></span>|<span data-ttu-id="857bf-125">Описание</span><span class="sxs-lookup"><span data-stu-id="857bf-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="857bf-126">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="857bf-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="857bf-127">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="857bf-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="857bf-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="857bf-128">Remarks</span></span>  
 <span data-ttu-id="857bf-129">Сопоставитель токенов службы можно использовать для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="857bf-129">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="857bf-130">Он используется для получения ключа, который должен использоваться для расшифровки входящих токенов.</span><span class="sxs-lookup"><span data-stu-id="857bf-130">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="857bf-131">Необходимо указать `type` атрибут.</span><span class="sxs-lookup"><span data-stu-id="857bf-131">You must specify the `type` attribute.</span></span> <span data-ttu-id="857bf-132">Указанный тип может быть либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> либо пользовательским типом, производным <xref:System.IdentityModel.Selectors.SecurityTokenResolver> от класса.</span><span class="sxs-lookup"><span data-stu-id="857bf-132">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="857bf-133">Некоторые обработчики маркеров позволяют задавать параметры сопоставителя токенов служб в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="857bf-133">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="857bf-134">Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="857bf-134">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="857bf-135">Указание элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости. `<serviceTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="857bf-135">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="857bf-136">Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="857bf-136">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="857bf-137">Пример</span><span class="sxs-lookup"><span data-stu-id="857bf-137">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
 