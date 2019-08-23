---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: ebf1f7f3de1b44dba63977bf524dea9af2690fb1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942782"
---
# <a name="customcookiehandler"></a><span data-ttu-id="3ade8-101">\<Кустомкукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="3ade8-101">\<customCookieHandler></span></span>
<span data-ttu-id="3ade8-102">Задает тип обработчика пользовательских файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="3ade8-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="3ade8-103">Этот элемент может присутствовать только в `mode` том случае, если атрибут `<cookieHandler>` элемента имеет значение Custom.</span><span class="sxs-lookup"><span data-stu-id="3ade8-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="3ade8-104">Пользовательский тип должен быть производным от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="3ade8-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="3ade8-105">\<> System. identityModel. Services</span><span class="sxs-lookup"><span data-stu-id="3ade8-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="3ade8-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3ade8-106">\<federationConfiguration></span></span>  
<span data-ttu-id="3ade8-107">\<Кукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="3ade8-107">\<cookieHandler></span></span>  
<span data-ttu-id="3ade8-108">\<Кустомкукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="3ade8-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ade8-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ade8-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ade8-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3ade8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3ade8-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3ade8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ade8-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3ade8-112">Attributes</span></span>  
  
|<span data-ttu-id="3ade8-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3ade8-113">Attribute</span></span>|<span data-ttu-id="3ade8-114">Описание</span><span class="sxs-lookup"><span data-stu-id="3ade8-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ade8-115">type</span><span class="sxs-lookup"><span data-stu-id="3ade8-115">type</span></span>|<span data-ttu-id="3ade8-116">Указывает пользовательский тип, производный от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="3ade8-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="3ade8-117">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="3ade8-117">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ade8-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3ade8-118">Child Elements</span></span>  
 <span data-ttu-id="3ade8-119">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="3ade8-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ade8-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3ade8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="3ade8-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="3ade8-121">Element</span></span>|<span data-ttu-id="3ade8-122">Описание</span><span class="sxs-lookup"><span data-stu-id="3ade8-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ade8-123">\<Кукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="3ade8-123">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="3ade8-124">Настраивает <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> , что использует для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="3ade8-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ade8-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ade8-125">Remarks</span></span>  
 <span data-ttu-id="3ade8-126">При указании пользовательского обработчика файлов cookie путем присвоения `mode` атрибуту `<cookieHandler>` элемента значения "Custom" необходимо указать тип пользовательского обработчика `<customCookieHandler>` файлов cookie, добавив дочерний элемент, ссылающийся на тип обработчика файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="3ade8-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="3ade8-127">Этот элемент не может быть указан, `mode` если для атрибута задано значение "фрагментированный" или "по умолчанию".</span><span class="sxs-lookup"><span data-stu-id="3ade8-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="3ade8-128">Пользовательские обработчики файлов cookie должны быть производными от <xref:System.IdentityModel.Services.CookieHandler> класса.</span><span class="sxs-lookup"><span data-stu-id="3ade8-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="3ade8-129">`<customCookieHandler>` Элемент представлен<xref:System.IdentityModel.Configuration.CustomTypeElement> классом.</span><span class="sxs-lookup"><span data-stu-id="3ade8-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ade8-130">Пример</span><span class="sxs-lookup"><span data-stu-id="3ade8-130">Example</span></span>  
 <span data-ttu-id="3ade8-131">В следующем примере SAM настраивается для использования пользовательского обработчика файлов cookie типа `MyNamespace.MyCustomCookieHandler`.</span><span class="sxs-lookup"><span data-stu-id="3ade8-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ade8-132">См. также</span><span class="sxs-lookup"><span data-stu-id="3ade8-132">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>
