---
title: '&lt;chunkedCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7220de45-1d14-4aec-a29e-4a2ea8ac861f
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 906a9e7cafca14dc4ee13dcb9eb9e59736464fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltchunkedcookiehandlergt"></a><span data-ttu-id="644aa-102">&lt;chunkedCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="644aa-102">&lt;chunkedCookieHandler&gt;</span></span>
<span data-ttu-id="644aa-103">Настраивает <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span><span class="sxs-lookup"><span data-stu-id="644aa-103">Configures the <xref:System.IdentityModel.Services.ChunkedCookieHandler>.</span></span> <span data-ttu-id="644aa-104">Этот элемент может быть представлен, только если `mode` атрибут `<cookieHandler>` «Default» или «Фрагментированным».</span><span class="sxs-lookup"><span data-stu-id="644aa-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Default" or "Chunked".</span></span>  
  
 <span data-ttu-id="644aa-105">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="644aa-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="644aa-106">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="644aa-106">\<federationConfiguration></span></span>  
<span data-ttu-id="644aa-107">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="644aa-107">\<cookieHandler></span></span>  
<span data-ttu-id="644aa-108">\<chunkedCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="644aa-108">\<chunkedCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="644aa-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="644aa-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="644aa-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="644aa-110">Attributes and Elements</span></span>  
 <span data-ttu-id="644aa-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="644aa-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="644aa-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="644aa-112">Attributes</span></span>  
  
|<span data-ttu-id="644aa-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="644aa-113">Attribute</span></span>|<span data-ttu-id="644aa-114">Описание</span><span class="sxs-lookup"><span data-stu-id="644aa-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="644aa-115">размер фрагмента данных</span><span class="sxs-lookup"><span data-stu-id="644aa-115">chunkSize</span></span>|<span data-ttu-id="644aa-116">Максимальный размер в символах данных файлов cookie HTTP для любого отдельного файла cookie HTTP.</span><span class="sxs-lookup"><span data-stu-id="644aa-116">The maximum size, in characters, of the HTTP cookie data for any one HTTP cookie.</span></span> <span data-ttu-id="644aa-117">Будьте внимательны, чтобы при корректировке размер фрагмента данных.</span><span class="sxs-lookup"><span data-stu-id="644aa-117">You must be careful when adjusting the chunk size.</span></span> <span data-ttu-id="644aa-118">Веб-браузеры имеют различные ограничения на размер файлов cookie и номер, приходящихся на каждый домен.</span><span class="sxs-lookup"><span data-stu-id="644aa-118">Web browsers have different limits on the size of cookies and number allowed per domain.</span></span> <span data-ttu-id="644aa-119">Например, Netscape спецификацию исходных оговорено этих ограничений: 300 файлы cookie всего 4096 байт на заголовке cookie (включая метаданные, не только значение файла cookie) и 20 файлов cookies для каждого домена.</span><span class="sxs-lookup"><span data-stu-id="644aa-119">For example, the original Netscape specification stipulated these limits: 300 cookies total, 4096 bytes per cookie header (including metadata, not just the cookie value), and 20 cookies per domain.</span></span> <span data-ttu-id="644aa-120">Значение по умолчанию — 2000.</span><span class="sxs-lookup"><span data-stu-id="644aa-120">The default is 2000.</span></span> <span data-ttu-id="644aa-121">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="644aa-121">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="644aa-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="644aa-122">Child Elements</span></span>  
 <span data-ttu-id="644aa-123">Нет</span><span class="sxs-lookup"><span data-stu-id="644aa-123">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="644aa-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="644aa-124">Parent Elements</span></span>  
  
|<span data-ttu-id="644aa-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="644aa-125">Element</span></span>|<span data-ttu-id="644aa-126">Описание</span><span class="sxs-lookup"><span data-stu-id="644aa-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="644aa-127">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="644aa-127">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="644aa-128">Настраивает <xref:System.IdentityModel.Services.CookieHandler> , <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) используется для чтения и записи файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="644aa-128">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="644aa-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="644aa-129">Remarks</span></span>  
 <span data-ttu-id="644aa-130">При указании <xref:System.IdentityModel.Services.ChunkedCookieHandler> , установив `mode` атрибут `<cookieHandler>` элемент «Default» или «Chunked» можно указать размер фрагмента данных, используемого обработчиком куки-файл для чтения и записи, включая файлы cookie `<chunkedCookieHandler>` дочерний элемент и Установка его `chunkSize` атрибута.</span><span class="sxs-lookup"><span data-stu-id="644aa-130">When you specify a <xref:System.IdentityModel.Services.ChunkedCookieHandler> by setting the `mode` attribute of the `<cookieHandler>` element to "Default" or "Chunked", you can specify the chunk size that the cookie handler uses to read and write cookies by including a `<chunkedCookieHandler>` child element and setting its `chunkSize` attribute.</span></span> <span data-ttu-id="644aa-131">Если `<chunkedCookieHandler>` элемент отсутствует, используется размер блока по умолчанию 2000 байтов.</span><span class="sxs-lookup"><span data-stu-id="644aa-131">If the `<chunkedCookieHandler>` element is not present, the default chunk size of 2000 bytes is used.</span></span> <span data-ttu-id="644aa-132">Этот элемент не может быть указано при `mode` атрибута задано значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="644aa-132">This element cannot be specified when the `mode` attribute is set to "Custom".</span></span>  
  
 <span data-ttu-id="644aa-133">`<chunkedCookieHandler>` Представлен <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> класса.</span><span class="sxs-lookup"><span data-stu-id="644aa-133">The `<chunkedCookieHandler>` element is represented by the <xref:System.IdentityModel.Services.ChunkedCookieHandlerElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="644aa-134">Пример</span><span class="sxs-lookup"><span data-stu-id="644aa-134">Example</span></span>  
 <span data-ttu-id="644aa-135">В следующем примере настраивается обработчик блочный файл cookie, который записывает файлы cookie фрагментами 3000 байт.</span><span class="sxs-lookup"><span data-stu-id="644aa-135">The following example configures a chunked cookie handler that writes cookies in chunks of 3000 bytes.</span></span>  
  
```xml  
<cookieHandler mode="Chunked">  
    <chunkedCookieHandler chunkSize=3000/>  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="644aa-136">См. также</span><span class="sxs-lookup"><span data-stu-id="644aa-136">See Also</span></span>  
 <xref:System.IdentityModel.Services.ChunkedCookieHandler>
