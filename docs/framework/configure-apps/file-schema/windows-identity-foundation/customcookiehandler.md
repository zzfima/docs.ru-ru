---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252021"
---
# <a name="customcookiehandler"></a><span data-ttu-id="d5d28-101">\<Кустомкукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="d5d28-101">\<customCookieHandler></span></span>
<span data-ttu-id="d5d28-102">Задает тип обработчика пользовательских файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="d5d28-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="d5d28-103">Этот элемент может присутствовать только в `mode` том случае, если атрибут `<cookieHandler>` элемента имеет значение Custom.</span><span class="sxs-lookup"><span data-stu-id="d5d28-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="d5d28-104">Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="d5d28-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
<span data-ttu-id="d5d28-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d5d28-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d5d28-106">&nbsp;&nbsp;[ **\<> System. identityModel. Services**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="d5d28-106">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="d5d28-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d5d28-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="d5d28-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Кукиехандлер >** ](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="d5d28-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="d5d28-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Кустомкукиехандлер >**</span><span class="sxs-lookup"><span data-stu-id="d5d28-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d28-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d5d28-110">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5d28-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d5d28-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d5d28-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d5d28-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5d28-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d5d28-113">Attributes</span></span>  
  
|<span data-ttu-id="d5d28-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d5d28-114">Attribute</span></span>|<span data-ttu-id="d5d28-115">Описание</span><span class="sxs-lookup"><span data-stu-id="d5d28-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d5d28-116">type</span><span class="sxs-lookup"><span data-stu-id="d5d28-116">type</span></span>|<span data-ttu-id="d5d28-117">Указывает пользовательский тип, производный от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="d5d28-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="d5d28-118">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="d5d28-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5d28-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d5d28-119">Child Elements</span></span>  
 <span data-ttu-id="d5d28-120">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="d5d28-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5d28-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d5d28-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d5d28-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="d5d28-122">Element</span></span>|<span data-ttu-id="d5d28-123">Описание</span><span class="sxs-lookup"><span data-stu-id="d5d28-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d5d28-124">\<Кукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="d5d28-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="d5d28-125">Настраивает <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> , что использует для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="d5d28-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5d28-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="d5d28-126">Remarks</span></span>  
 <span data-ttu-id="d5d28-127">При указании пользовательского обработчика файлов cookie путем присвоения `mode` атрибуту `<cookieHandler>` элемента значения "Custom" необходимо указать тип пользовательского обработчика `<customCookieHandler>` файлов cookie, добавив дочерний элемент, ссылающийся на тип обработчика файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="d5d28-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="d5d28-128">Этот элемент не может быть указан, `mode` если для атрибута задано значение "фрагментированный" или "по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="d5d28-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="d5d28-129">Пользовательские обработчики файлов cookie должны быть производными от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="d5d28-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="d5d28-130">`<customCookieHandler>` Элемент представлен<xref:System.IdentityModel.Configuration.CustomTypeElement> классом.</span><span class="sxs-lookup"><span data-stu-id="d5d28-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5d28-131">Пример</span><span class="sxs-lookup"><span data-stu-id="d5d28-131">Example</span></span>  
 <span data-ttu-id="d5d28-132">В следующем примере SAM настраивается для использования пользовательского обработчика файлов cookie типа `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="d5d28-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d5d28-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d5d28-133">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
