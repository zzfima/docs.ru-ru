---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: b3b4cf0d7c2748079af7a94534622b1dbadd3ab5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941896"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="8ce52-101">\<Чункедкукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="8ce52-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="8ce52-102">Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="8ce52-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="8ce52-103">Этот элемент может присутствовать только в `mode` том случае, если атрибут `<cookieHandler>` элемента имеет значение "default" или "фрагментированный".</span><span class="sxs-lookup"><span data-stu-id="8ce52-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="8ce52-104">\<> System. identityModel. Services</span><span class="sxs-lookup"><span data-stu-id="8ce52-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="8ce52-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8ce52-105">\<federationConfiguration></span></span>  
<span data-ttu-id="8ce52-106">\<Кукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="8ce52-106">\<cookieHandler></span></span>  
<span data-ttu-id="8ce52-107">\<Чункедкукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="8ce52-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ce52-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8ce52-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8ce52-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8ce52-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8ce52-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8ce52-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8ce52-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8ce52-111">Attributes</span></span>  
  
|<span data-ttu-id="8ce52-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8ce52-112">Attribute</span></span>|<span data-ttu-id="8ce52-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8ce52-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8ce52-114">chunkSize</span><span class="sxs-lookup"><span data-stu-id="8ce52-114">chunkSize</span></span>|<span data-ttu-id="8ce52-115">Максимальный размер (в символах) данных cookie HTTP для одного файла cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="8ce52-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="8ce52-116">При изменении размера фрагмента данных необходимо соблюдать осторожность.</span><span class="sxs-lookup"><span data-stu-id="8ce52-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="8ce52-117">Веб-браузеры имеют разные ограничения на размер файлов cookie и число допустимых для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="8ce52-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="8ce52-118">Например, исходная спецификация Netscape заменяет эти ограничения: 300 файлов cookie Total, 4096 байт на каждый заголовок файла cookie (включая метаданные, а не только значение cookie) и 20 файлов cookie на домен.</span><span class="sxs-lookup"><span data-stu-id="8ce52-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="8ce52-119">Значение по умолчанию — 2000.</span><span class="sxs-lookup"><span data-stu-id="8ce52-119">The default is 2000.</span></span> <span data-ttu-id="8ce52-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="8ce52-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8ce52-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8ce52-121">Child Elements</span></span>  
 <span data-ttu-id="8ce52-122">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="8ce52-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8ce52-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8ce52-123">Parent Elements</span></span>  
  
|<span data-ttu-id="8ce52-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="8ce52-124">Element</span></span>|<span data-ttu-id="8ce52-125">Описание</span><span class="sxs-lookup"><span data-stu-id="8ce52-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8ce52-126">\<Кукиехандлер ></span><span class="sxs-lookup"><span data-stu-id="8ce52-126">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="8ce52-127">Настраивает <xref:System.IdentityModel.Services.CookieHandler> <xref:System.IdentityModel.Services.SessionAuthenticationModule> , что (SAM) использует для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="8ce52-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8ce52-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="8ce52-128">Remarks</span></span>  
 <span data-ttu-id="8ce52-129">При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> с помощью `mode` присвоения атрибуту `<cookieHandler>` элемента значения "по умолчанию" или "фрагментированного" можно указать размер фрагмента, используемый обработчиком файлов cookie `<chunkedCookieHandler>` для чтения и записи файлов cookie, включая дочерний элемент и `chunkSize` задание атрибута.</span><span class="sxs-lookup"><span data-stu-id="8ce52-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="8ce52-130">`<chunkedCookieHandler>` Если элемент отсутствует, используется размер фрагмента по умолчанию (2000 байт).</span><span class="sxs-lookup"><span data-stu-id="8ce52-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="8ce52-131">Этот элемент не может быть указан, `mode` если для атрибута задано значение Custom.</span><span class="sxs-lookup"><span data-stu-id="8ce52-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="8ce52-132">`<chunkedCookieHandler>` Элемент представлен<xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> классом.</span><span class="sxs-lookup"><span data-stu-id="8ce52-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ce52-133">Пример</span><span class="sxs-lookup"><span data-stu-id="8ce52-133">Example</span></span>  
 <span data-ttu-id="8ce52-134">В следующем примере настраивается обработчик фрагментированных файлов cookie, который записывает файлы cookie в фрагменты 3000 байт.</span><span class="sxs-lookup"><span data-stu-id="8ce52-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ce52-135">См. также</span><span class="sxs-lookup"><span data-stu-id="8ce52-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
