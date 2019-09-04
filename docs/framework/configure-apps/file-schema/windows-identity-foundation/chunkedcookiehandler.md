---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: 6aad95033b99f1472284f838f3ede2e74ea8324c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252107"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="f7417-101">\<Чункедкукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="f7417-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="f7417-102">Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="f7417-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="f7417-103">Этот элемент может присутствовать только в `mode` том случае, если атрибут `<cookieHandler>` элемента имеет значение "default" или "фрагментированный".</span><span class="sxs-lookup"><span data-stu-id="f7417-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
<span data-ttu-id="f7417-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f7417-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f7417-105">&nbsp;&nbsp;[ **\<> System. identityModel. Services**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="f7417-105">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="f7417-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="f7417-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="f7417-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Кукиехандлер >** ](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="f7417-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="f7417-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Чункедкукиехандлер >**</span><span class="sxs-lookup"><span data-stu-id="f7417-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<chunkedCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7417-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7417-109">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Chunked||Default" >  
      <chunkedCookieHandler size=xs:int >  
      </chunkedCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7417-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f7417-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f7417-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f7417-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7417-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f7417-112">Attributes</span></span>  
  
|<span data-ttu-id="f7417-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f7417-113">Attribute</span></span>|<span data-ttu-id="f7417-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f7417-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f7417-115">chunkSize</span><span class="sxs-lookup"><span data-stu-id="f7417-115">chunkSize</span></span>|<span data-ttu-id="f7417-116">Максимальный размер (в символах) данных cookie HTTP для одного файла cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="f7417-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="f7417-117">При изменении размера фрагмента данных необходимо соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="f7417-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="f7417-118">Веб-браузеры имеют разные ограничения на размер файлов cookie и число допустимых для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="f7417-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="f7417-119">Например, исходная спецификация Netscape заменяет эти ограничения: 300 файлов cookie Total, 4096 байт на каждый заголовок файла cookie (включая метаданные, а не только значение cookie) и 20 файлов cookie на домен.</span><span class="sxs-lookup"><span data-stu-id="f7417-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="f7417-120">Значение по умолчанию — 2000.</span><span class="sxs-lookup"><span data-stu-id="f7417-120">The default is 2000.</span></span> <span data-ttu-id="f7417-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="f7417-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f7417-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f7417-122">Child Elements</span></span>  
 <span data-ttu-id="f7417-123">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f7417-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7417-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f7417-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f7417-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f7417-125">Element</span></span>|<span data-ttu-id="f7417-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f7417-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f7417-127">\<Кукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="f7417-127">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="f7417-128">Настраивает <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> , что (SAM) использует для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="f7417-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7417-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7417-129">Remarks</span></span>  
 <span data-ttu-id="f7417-130">При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> с помощью `mode` присвоения атрибуту `<cookieHandler>` элемента значения "по умолчанию" или "фрагментированного" можно указать размер фрагмента, используемый обработчиком файлов cookie `<chunkedCookieHandler>` для чтения и записи файлов cookie, включая дочерний элемент и `chunkSize` задание атрибута.</span><span class="sxs-lookup"><span data-stu-id="f7417-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="f7417-131">`<chunkedCookieHandler>` Если элемент отсутствует, используется размер фрагмента по умолчанию (2000 байт).</span><span class="sxs-lookup"><span data-stu-id="f7417-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="f7417-132">Этот элемент не может быть указан, `mode` если для атрибута задано значение Custom.</span><span class="sxs-lookup"><span data-stu-id="f7417-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="f7417-133">`<chunkedCookieHandler>` Элемент представлен<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> классом.</span><span class="sxs-lookup"><span data-stu-id="f7417-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7417-134">Пример</span><span class="sxs-lookup"><span data-stu-id="f7417-134">Example</span></span>  
 <span data-ttu-id="f7417-135">В следующем примере настраивается обработчик фрагментированных файлов cookie, который записывает файлы cookie в фрагменты 3000 байт.</span><span class="sxs-lookup"><span data-stu-id="f7417-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7417-136">См. также</span><span class="sxs-lookup"><span data-stu-id="f7417-136">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
