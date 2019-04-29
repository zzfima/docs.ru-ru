---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 0129c63fe17b63889a77ea1a56c0d7e657def859
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791733"
---
# <a name="customcookiehandler"></a><span data-ttu-id="42529-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="42529-101">\<customCookieHandler></span></span>
<span data-ttu-id="42529-102">Задает тип обработчика пользовательских файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="42529-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="42529-103">Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` элемент является «Custom».</span><span class="sxs-lookup"><span data-stu-id="42529-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="42529-104">Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="42529-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="42529-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="42529-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="42529-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="42529-106">\<federationConfiguration></span></span>  
<span data-ttu-id="42529-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="42529-107">\<cookieHandler></span></span>  
<span data-ttu-id="42529-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="42529-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42529-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="42529-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42529-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="42529-110">Attributes and Elements</span></span>  
 <span data-ttu-id="42529-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="42529-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42529-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="42529-112">Attributes</span></span>  
  
|<span data-ttu-id="42529-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="42529-113">Attribute</span></span>|<span data-ttu-id="42529-114">Описание</span><span class="sxs-lookup"><span data-stu-id="42529-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="42529-115">type</span><span class="sxs-lookup"><span data-stu-id="42529-115">type</span></span>|<span data-ttu-id="42529-116">Задает пользовательский тип, производный от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="42529-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="42529-117">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="42529-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42529-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="42529-118">Child Elements</span></span>  
 <span data-ttu-id="42529-119">Нет</span><span class="sxs-lookup"><span data-stu-id="42529-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42529-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="42529-120">Parent Elements</span></span>  
  
|<span data-ttu-id="42529-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="42529-121">Element</span></span>|<span data-ttu-id="42529-122">Описание</span><span class="sxs-lookup"><span data-stu-id="42529-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="42529-123">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="42529-123">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="42529-124">Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> используется для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="42529-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42529-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="42529-125">Remarks</span></span>  
 <span data-ttu-id="42529-126">При указании пользовательский обработчик файлов cookie, задав `mode` атрибут `<cookieHandler>` элемент на «Пользовательский», необходимо указать тип пользовательский обработчик файлов cookie, включив `<customCookieHandler>` дочерний элемент, ссылающийся на тип обработчика файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="42529-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="42529-127">Этот элемент не может быть указан при `mode` атрибут имеет значение «Chunked» или «Default».</span><span class="sxs-lookup"><span data-stu-id="42529-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="42529-128">Обработчики пользовательских файлов cookie должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="42529-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="42529-129">`<customCookieHandler>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.CustomTypeElement> класса.</span><span class="sxs-lookup"><span data-stu-id="42529-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42529-130">Пример</span><span class="sxs-lookup"><span data-stu-id="42529-130">Example</span></span>  
 <span data-ttu-id="42529-131">В следующем примере настраивается SAM, чтобы использовать пользовательский обработчик типа `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="42529-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42529-132">См. также</span><span class="sxs-lookup"><span data-stu-id="42529-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
