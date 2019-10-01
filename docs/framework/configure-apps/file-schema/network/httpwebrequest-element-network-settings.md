---
title: Элемент <httpWebRequest> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/httpWebRequest
- http://schemas.microsoft.com/.NetConfiguration/v2.0#httpWebRequest
helpviewer_keywords:
- <httpWebRequest> element
- httpWebRequest element
ms.assetid: 52acd9d2-5bdc-4dc4-9c2a-f0a476ccbb31
ms.openlocfilehash: fa00aed2cd1e96ec788d4bc9c1c63f20561d8d1c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698182"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="e6d3f-102">Элемент > @no__t 0httpWebRequest (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="e6d3f-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="e6d3f-103">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-103">Customizes Web request parameters.</span></span>  
  
[<span data-ttu-id="e6d3f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="e6d3f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="e6d3f-105">&nbsp; @ no__t-1[ **@no__t -4system. NET >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e6d3f-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="e6d3f-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="e6d3f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="e6d3f-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<httpWebRequest >**</span><span class="sxs-lookup"><span data-stu-id="e6d3f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpWebRequest>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6d3f-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6d3f-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e6d3f-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e6d3f-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e6d3f-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e6d3f-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e6d3f-111">Attributes</span></span>  
  
|<span data-ttu-id="e6d3f-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="e6d3f-112">**Attribute**</span></span>|<span data-ttu-id="e6d3f-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e6d3f-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="e6d3f-114">Задает максимальную длину заголовка ответа в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="e6d3f-115">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-115">The default is 64.</span></span> <span data-ttu-id="e6d3f-116">Значение-1 указывает на то, что в заголовках ответа ограничение размера не накладывается.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="e6d3f-117">Указывает максимальную длину ответа на ошибку в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="e6d3f-118">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-118">The default is 64.</span></span> <span data-ttu-id="e6d3f-119">Значение-1 указывает, что в ответе на ошибку не будет накладывается никаких ограничений на размер.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="e6d3f-120">Указывает максимальную длину отправки в ответ на несанкционированный код ошибки в байтах.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="e6d3f-121">Значение по умолчанию — -1.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-121">The default is -1.</span></span> <span data-ttu-id="e6d3f-122">Значение-1 указывает на то, что для передачи не будет наложено ограничение размера.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="e6d3f-123">Указывает, включен ли анализ ненадежных заголовков.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="e6d3f-124">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e6d3f-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e6d3f-125">Child Elements</span></span>  
 <span data-ttu-id="e6d3f-126">Нет.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e6d3f-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e6d3f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="e6d3f-128">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="e6d3f-128">**Element**</span></span>|<span data-ttu-id="e6d3f-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e6d3f-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e6d3f-130">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6d3f-130">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="e6d3f-131">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6d3f-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="e6d3f-132">Remarks</span></span>  
 <span data-ttu-id="e6d3f-133">По умолчанию .NET Framework строго применяет RFC 2616 для синтаксического анализа URI.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="e6d3f-134">Некоторые серверные ответы могут содержать управляющие символы в запрещенных полях, что приведет к тому, что метод <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> выдаст <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="e6d3f-135">Если **усеунсафехеадерпарсинг** имеет значение **true**, то <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> не будет вызывать исключение в этом случае; Однако приложение будет уязвимо для нескольких форм атак с синтаксическим анализом URI.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="e6d3f-136">Лучшим решением является изменение сервера, чтобы ответ не включал управляющие символы.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e6d3f-137">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="e6d3f-137">Configuration Files</span></span>  
 <span data-ttu-id="e6d3f-138">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e6d3f-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6d3f-139">Пример</span><span class="sxs-lookup"><span data-stu-id="e6d3f-139">Example</span></span>  
 <span data-ttu-id="e6d3f-140">В следующем примере показано, как задать большую, чем нормальную максимальную длину заголовка.</span><span class="sxs-lookup"><span data-stu-id="e6d3f-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpWebRequest  
        maximumResponseHeadersLength="128"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e6d3f-141">См. также</span><span class="sxs-lookup"><span data-stu-id="e6d3f-141">See also</span></span>

- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="e6d3f-142">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="e6d3f-142">Network Settings Schema</span></span>](index.md)
