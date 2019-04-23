---
title: <chunkedCookieHandler>
ms.date: 03/30/2017
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
author: BrucePerlerMS
ms.openlocfilehash: d9c81d5de7bea343f0d67fa00037763fbae7b8c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120787"
---
# <a name="chunkedcookiehandler"></a><span data-ttu-id="2be51-101">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="2be51-101">\<chunkedCookieHandler></span></span>
<span data-ttu-id="2be51-102">Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="2be51-102">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="2be51-103">Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` элемент является «Default» или шифрование «фрагментированной».</span><span class="sxs-lookup"><span data-stu-id="2be51-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="2be51-104">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="2be51-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="2be51-105">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="2be51-105">\<federationConfiguration></span></span>  
<span data-ttu-id="2be51-106">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="2be51-106">\<cookieHandler></span></span>  
<span data-ttu-id="2be51-107">\<chunkedCookieHandler></span><span class="sxs-lookup"><span data-stu-id="2be51-107">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2be51-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2be51-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2be51-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2be51-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2be51-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2be51-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2be51-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2be51-111">Attributes</span></span>  
  
|<span data-ttu-id="2be51-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2be51-112">Attribute</span></span>|<span data-ttu-id="2be51-113">Описание</span><span class="sxs-lookup"><span data-stu-id="2be51-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2be51-114">размер фрагмента данных</span><span class="sxs-lookup"><span data-stu-id="2be51-114">chunkSize</span></span>|<span data-ttu-id="2be51-115">Максимальный размер в символах данные файла cookie HTTP для любого отдельного файла cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="2be51-115">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="2be51-116">Будьте внимательны, настраивая размер фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="2be51-116">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="2be51-117">Веб-браузеры имеют различные ограничения на размер файлов cookie и номер, приходящихся на каждый домен.</span><span class="sxs-lookup"><span data-stu-id="2be51-117">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="2be51-118">Например исходная спецификация Netscape оговорено эти ограничения: Общее 300 файлы cookie, 4096 байт в заголовок файла cookie (включая метаданные, не только значение файла cookie) и 20 файлов cookies для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="2be51-118">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="2be51-119">Значение по умолчанию — 2000.</span><span class="sxs-lookup"><span data-stu-id="2be51-119">The default is 2000.</span></span> <span data-ttu-id="2be51-120">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="2be51-120">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2be51-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2be51-121">Child Elements</span></span>  
 <span data-ttu-id="2be51-122">Нет</span><span class="sxs-lookup"><span data-stu-id="2be51-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2be51-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2be51-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2be51-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="2be51-124">Element</span></span>|<span data-ttu-id="2be51-125">Описание</span><span class="sxs-lookup"><span data-stu-id="2be51-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2be51-126">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="2be51-126">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="2be51-127">Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) используется для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="2be51-127">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2be51-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="2be51-128">Remarks</span></span>  
 <span data-ttu-id="2be51-129">При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> , задав `mode` атрибут `<cookieHandler>` элемент «Default» или «Chunked» можно указать размер фрагмента данных, который использует обработчик файлов cookie для чтения и записи файлов cookie, включив `<chunkedCookieHandler>` дочерний элемент и Установка его `chunkSize` атрибута.</span><span class="sxs-lookup"><span data-stu-id="2be51-129">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="2be51-130">Если `<chunkedCookieHandler>` элемент отсутствует, используется размер блока по умолчанию 2000 байтов.</span><span class="sxs-lookup"><span data-stu-id="2be51-130">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="2be51-131">Этот элемент не может быть указан при `mode` атрибут имеет значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="2be51-131">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="2be51-132">`<chunkedCookieHandler>` Элемент, представленный объектом <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> класса.</span><span class="sxs-lookup"><span data-stu-id="2be51-132">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2be51-133">Пример</span><span class="sxs-lookup"><span data-stu-id="2be51-133">Example</span></span>  
 <span data-ttu-id="2be51-134">В следующем примере настраивается фрагментированный обработчик файлов cookie, записывает файлы cookie в виде фрагментов 3000 байтов.</span><span class="sxs-lookup"><span data-stu-id="2be51-134">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2be51-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2be51-135">See also</span></span>

- <xref:System.IdentityModel.Services.ChunkedCookieHandler>
