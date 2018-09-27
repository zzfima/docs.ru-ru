---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: f5592e0fd02d34b2882182196e0aa9425672a8fe
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2018
ms.locfileid: "47400820"
---
# <a name="ltchunkedcookiehandlergt"></a><span data-ttu-id="2aa93-102">&lt;chunkedCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="2aa93-102">&lt;chunkedCookieHandler&gt;</span></span>
<span data-ttu-id="2aa93-103">Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="2aa93-103">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="2aa93-104">Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` элемент является «Default» или шифрование «фрагментированной».</span><span class="sxs-lookup"><span data-stu-id="2aa93-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="2aa93-105">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="2aa93-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="2aa93-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="2aa93-106">\<federationConfiguration></span></span>  
<span data-ttu-id="2aa93-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="2aa93-107">\<cookieHandler></span></span>  
<span data-ttu-id="2aa93-108">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="2aa93-108">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2aa93-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2aa93-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2aa93-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2aa93-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2aa93-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2aa93-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2aa93-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2aa93-112">Attributes</span></span>  
  
|<span data-ttu-id="2aa93-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2aa93-113">Attribute</span></span>|<span data-ttu-id="2aa93-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2aa93-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2aa93-115">размер фрагмента данных</span><span class="sxs-lookup"><span data-stu-id="2aa93-115">chunkSize</span></span>|<span data-ttu-id="2aa93-116">Максимальный размер в символах данные файла cookie HTTP для любого отдельного файла cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="2aa93-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="2aa93-117">Будьте внимательны, настраивая размер фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="2aa93-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="2aa93-118">Веб-браузеры имеют различные ограничения на размер файлов cookie и номер, приходящихся на каждый домен.</span><span class="sxs-lookup"><span data-stu-id="2aa93-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="2aa93-119">Например, исходная спецификация Netscape оговорено эти ограничения: всего 300 файлы cookie, 4096 байт в заголовок файла cookie (включая метаданные, не только значение файла cookie) и 20 файлов cookies для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="2aa93-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="2aa93-120">Значение по умолчанию — 2000.</span><span class="sxs-lookup"><span data-stu-id="2aa93-120">The default is 2000.</span></span> <span data-ttu-id="2aa93-121">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="2aa93-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2aa93-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2aa93-122">Child Elements</span></span>  
 <span data-ttu-id="2aa93-123">Нет</span><span class="sxs-lookup"><span data-stu-id="2aa93-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2aa93-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2aa93-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2aa93-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="2aa93-125">Element</span></span>|<span data-ttu-id="2aa93-126">Описание</span><span class="sxs-lookup"><span data-stu-id="2aa93-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2aa93-127">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="2aa93-127">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="2aa93-128">Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) используется для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="2aa93-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2aa93-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="2aa93-129">Remarks</span></span>  
 <span data-ttu-id="2aa93-130">При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> , задав `mode` атрибут `<cookieHandler>` элемент «Default» или «Chunked» можно указать размер фрагмента данных, который использует обработчик файлов cookie для чтения и записи файлов cookie, включив `<chunkedCookieHandler>` дочерний элемент и Установка его `chunkSize` атрибута.</span><span class="sxs-lookup"><span data-stu-id="2aa93-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="2aa93-131">Если `<chunkedCookieHandler>` элемент отсутствует, используется размер блока по умолчанию 2000 байтов.</span><span class="sxs-lookup"><span data-stu-id="2aa93-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="2aa93-132">Этот элемент не может быть указан при `mode` атрибут имеет значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="2aa93-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="2aa93-133">`<chunkedCookieHandler>` Элемент, представленный объектом <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> класса.</span><span class="sxs-lookup"><span data-stu-id="2aa93-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aa93-134">Пример</span><span class="sxs-lookup"><span data-stu-id="2aa93-134">Example</span></span>  
 <span data-ttu-id="2aa93-135">В следующем примере настраивается фрагментированный обработчик файлов cookie, записывает файлы cookie в виде фрагментов 3000 байтов.</span><span class="sxs-lookup"><span data-stu-id="2aa93-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2aa93-136">См. также</span><span class="sxs-lookup"><span data-stu-id="2aa93-136">See Also</span></span>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
