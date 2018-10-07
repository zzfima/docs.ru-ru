---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 51ca91de5c77727f5f5506118461d19354f12c14
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48836424"
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="59d0a-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="59d0a-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="59d0a-103">Задает тип обработчика пользовательских файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="59d0a-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="59d0a-104">Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` элемент является «Custom».</span><span class="sxs-lookup"><span data-stu-id="59d0a-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="59d0a-105">Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="59d0a-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="59d0a-106">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="59d0a-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="59d0a-107">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="59d0a-107">\<federationConfiguration></span></span>  
<span data-ttu-id="59d0a-108">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="59d0a-108">\<cookieHandler></span></span>  
<span data-ttu-id="59d0a-109">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="59d0a-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59d0a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59d0a-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59d0a-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="59d0a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="59d0a-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="59d0a-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59d0a-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="59d0a-113">Attributes</span></span>  
  
|<span data-ttu-id="59d0a-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="59d0a-114">Attribute</span></span>|<span data-ttu-id="59d0a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="59d0a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59d0a-116">type</span><span class="sxs-lookup"><span data-stu-id="59d0a-116">type</span></span>|<span data-ttu-id="59d0a-117">Задает пользовательский тип, производный от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="59d0a-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="59d0a-118">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="59d0a-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59d0a-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="59d0a-119">Child Elements</span></span>  
 <span data-ttu-id="59d0a-120">Нет</span><span class="sxs-lookup"><span data-stu-id="59d0a-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59d0a-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="59d0a-121">Parent Elements</span></span>  
  
|<span data-ttu-id="59d0a-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="59d0a-122">Element</span></span>|<span data-ttu-id="59d0a-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="59d0a-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59d0a-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="59d0a-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="59d0a-125">Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> используется для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="59d0a-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59d0a-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="59d0a-126">Remarks</span></span>  
 <span data-ttu-id="59d0a-127">При указании пользовательский обработчик файлов cookie, задав `mode` атрибут `<cookieHandler>` элемент на «Пользовательский», необходимо указать тип пользовательский обработчик файлов cookie, включив `<customCookieHandler>` дочерний элемент, ссылающийся на тип обработчика файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="59d0a-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="59d0a-128">Этот элемент не может быть указан при `mode` атрибут имеет значение «Chunked» или «Default».</span><span class="sxs-lookup"><span data-stu-id="59d0a-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="59d0a-129">Обработчики пользовательских файлов cookie должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="59d0a-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="59d0a-130">`<customCookieHandler>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.CustomTypeElement> класса.</span><span class="sxs-lookup"><span data-stu-id="59d0a-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59d0a-131">Пример</span><span class="sxs-lookup"><span data-stu-id="59d0a-131">Example</span></span>  
 <span data-ttu-id="59d0a-132">В следующем примере настраивается SAM, чтобы использовать пользовательский обработчик типа `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="59d0a-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59d0a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="59d0a-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>
