---
title: <serviceTokenResolver>
ms.date: 03/30/2017
ms.assetid: 6e9001e1-e064-4f47-84b2-46225c177746
author: BrucePerlerMS
ms.openlocfilehash: 69d34cb54c2236f178ac4291ed24a3f5b45db48e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923111"
---
# <a name="servicetokenresolver"></a><span data-ttu-id="f3053-101">\<Сервицетокенресолвер ></span><span class="sxs-lookup"><span data-stu-id="f3053-101">\<serviceTokenResolver></span></span>
<span data-ttu-id="f3053-102">Регистрирует сопоставитель маркеров службы, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="f3053-102">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="f3053-103">Сопоставитель токенов службы используется для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="f3053-103">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="f3053-104">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="f3053-104">\<system.identityModel></span></span>  
<span data-ttu-id="f3053-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="f3053-105">\<identityConfiguration></span></span>  
<span data-ttu-id="f3053-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="f3053-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="f3053-107">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="f3053-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="f3053-108">\<Сервицетокенресолвер ></span><span class="sxs-lookup"><span data-stu-id="f3053-108">\<serviceTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3053-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3053-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3053-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f3053-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f3053-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f3053-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3053-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f3053-112">Attributes</span></span>  
  
|<span data-ttu-id="f3053-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f3053-113">Attribute</span></span>|<span data-ttu-id="f3053-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f3053-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3053-115">type</span><span class="sxs-lookup"><span data-stu-id="f3053-115">type</span></span>|<span data-ttu-id="f3053-116">Указывает тип сопоставителя токенов службы.</span><span class="sxs-lookup"><span data-stu-id="f3053-116">Specifies the type of the service token resolver.</span></span> <span data-ttu-id="f3053-117">Либо тип, либо тип, производный <xref:System.IdentityModel.Selectors.SecurityTokenResolver> от класса. <xref:System.IdentityModel.Selectors.SecurityTokenResolver></span><span class="sxs-lookup"><span data-stu-id="f3053-117">Either the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> type or a type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span> <span data-ttu-id="f3053-118">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="f3053-118">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span> <span data-ttu-id="f3053-119">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f3053-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3053-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f3053-120">Child Elements</span></span>  
 <span data-ttu-id="f3053-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f3053-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3053-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f3053-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f3053-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="f3053-123">Element</span></span>|<span data-ttu-id="f3053-124">Описание</span><span class="sxs-lookup"><span data-stu-id="f3053-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f3053-125">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="f3053-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="f3053-126">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="f3053-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3053-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="f3053-127">Remarks</span></span>  
 <span data-ttu-id="f3053-128">Сопоставитель токенов службы можно использовать для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="f3053-128">The service token resolver can be used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="f3053-129">Он используется для получения ключа, который должен использоваться для расшифровки входящих токенов.</span><span class="sxs-lookup"><span data-stu-id="f3053-129">It is used to retrieve the key that should be used to decrypt incoming tokens.</span></span> <span data-ttu-id="f3053-130">Необходимо указать `type` атрибут.</span><span class="sxs-lookup"><span data-stu-id="f3053-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="f3053-131">Указанный тип может быть либо <xref:System.IdentityModel.Selectors.SecurityTokenResolver> либо пользовательским типом, производным <xref:System.IdentityModel.Selectors.SecurityTokenResolver> от класса.</span><span class="sxs-lookup"><span data-stu-id="f3053-131">The type specified can be either <xref:System.IdentityModel.Selectors.SecurityTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Selectors.SecurityTokenResolver> class.</span></span>  
  
 <span data-ttu-id="f3053-132">Некоторые обработчики маркеров позволяют задавать параметры сопоставителя токенов служб в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f3053-132">Some token handlers allow you to specify service token resolver settings in configuration.</span></span> <span data-ttu-id="f3053-133">Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="f3053-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3053-134">Указание элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости. `<serviceTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="f3053-134">Specifying the `<serviceTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="f3053-135">Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="f3053-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3053-136">Пример</span><span class="sxs-lookup"><span data-stu-id="f3053-136">Example</span></span>  
  
```xml  
<serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
```
