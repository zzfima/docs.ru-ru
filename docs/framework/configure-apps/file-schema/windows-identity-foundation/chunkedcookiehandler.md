---
title: '&lt;chunkedCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: f5592e0fd02d34b2882182196e0aa9425672a8fe
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2018
ms.locfileid: "48244944"
---
# <a name="ltchunkedcookiehandlergt"></a><span data-ttu-id="fedcf-102">&lt;chunkedCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="fedcf-102">&lt;chunkedCookieHandler&gt;</span></span>
<span data-ttu-id="fedcf-103">Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="fedcf-103">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="fedcf-104">Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` элемент является «Default» или шифрование «фрагментированной».</span><span class="sxs-lookup"><span data-stu-id="fedcf-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="fedcf-105">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="fedcf-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="fedcf-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fedcf-106">\<federationConfiguration></span></span>  
<span data-ttu-id="fedcf-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="fedcf-107">\<cookieHandler></span></span>  
<span data-ttu-id="fedcf-108">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="fedcf-108">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fedcf-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fedcf-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fedcf-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fedcf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fedcf-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fedcf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fedcf-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fedcf-112">Attributes</span></span>  
  
|<span data-ttu-id="fedcf-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fedcf-113">Attribute</span></span>|<span data-ttu-id="fedcf-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fedcf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fedcf-115">размер фрагмента данных</span><span class="sxs-lookup"><span data-stu-id="fedcf-115">chunkSize</span></span>|<span data-ttu-id="fedcf-116">Максимальный размер в символах данные файла cookie HTTP для любого отдельного файла cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="fedcf-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="fedcf-117">Будьте внимательны, настраивая размер фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="fedcf-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="fedcf-118">Веб-браузеры имеют различные ограничения на размер файлов cookie и номер, приходящихся на каждый домен.</span><span class="sxs-lookup"><span data-stu-id="fedcf-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="fedcf-119">Например, исходная спецификация Netscape оговорено эти ограничения: всего 300 файлы cookie, 4096 байт в заголовок файла cookie (включая метаданные, не только значение файла cookie) и 20 файлов cookies для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="fedcf-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="fedcf-120">Значение по умолчанию — 2000.</span><span class="sxs-lookup"><span data-stu-id="fedcf-120">The default is 2000.</span></span> <span data-ttu-id="fedcf-121">Обязательно.</span><span class="sxs-lookup"><span data-stu-id="fedcf-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fedcf-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fedcf-122">Child Elements</span></span>  
 <span data-ttu-id="fedcf-123">Нет</span><span class="sxs-lookup"><span data-stu-id="fedcf-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fedcf-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fedcf-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fedcf-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="fedcf-125">Element</span></span>|<span data-ttu-id="fedcf-126">Описание</span><span class="sxs-lookup"><span data-stu-id="fedcf-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fedcf-127">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="fedcf-127">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="fedcf-128">Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) используется для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="fedcf-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fedcf-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="fedcf-129">Remarks</span></span>  
 <span data-ttu-id="fedcf-130">При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> , задав `mode` атрибут `<cookieHandler>` элемент «Default» или «Chunked» можно указать размер фрагмента данных, который использует обработчик файлов cookie для чтения и записи файлов cookie, включив `<chunkedCookieHandler>` дочерний элемент и Установка его `chunkSize` атрибута.</span><span class="sxs-lookup"><span data-stu-id="fedcf-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="fedcf-131">Если `<chunkedCookieHandler>` элемент отсутствует, используется размер блока по умолчанию 2000 байтов.</span><span class="sxs-lookup"><span data-stu-id="fedcf-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="fedcf-132">Этот элемент не может быть указан при `mode` атрибут имеет значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="fedcf-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="fedcf-133">`<chunkedCookieHandler>` Элемент, представленный объектом <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> класса.</span><span class="sxs-lookup"><span data-stu-id="fedcf-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fedcf-134">Пример</span><span class="sxs-lookup"><span data-stu-id="fedcf-134">Example</span></span>  
 <span data-ttu-id="fedcf-135">В следующем примере настраивается фрагментированный обработчик файлов cookie, записывает файлы cookie в виде фрагментов 3000 байтов.</span><span class="sxs-lookup"><span data-stu-id="fedcf-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fedcf-136">См. также</span><span class="sxs-lookup"><span data-stu-id="fedcf-136">See Also</span></span>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
