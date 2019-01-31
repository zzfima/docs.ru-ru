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
ms.openlocfilehash: f19c39922105cebe179dd9f26fdc6beac8ddc0ef
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268279"
---
# <a name="httpwebrequest-element-network-settings"></a><span data-ttu-id="5e8b3-102">\<httpWebRequest > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="5e8b3-102">\<httpWebRequest> Element (Network Settings)</span></span>
<span data-ttu-id="5e8b3-103">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-103">Customizes Web request parameters.</span></span>  
  
 <span data-ttu-id="5e8b3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5e8b3-104">\<configuration></span></span>  
<span data-ttu-id="5e8b3-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="5e8b3-105">\<system.net></span></span>  
<span data-ttu-id="5e8b3-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="5e8b3-106">\<settings></span></span>  
<span data-ttu-id="5e8b3-107">\<httpWebRequest></span><span class="sxs-lookup"><span data-stu-id="5e8b3-107">\<httpWebRequest></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e8b3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e8b3-108">Syntax</span></span>  
  
```xml  
<httpWebRequest  
  maximumResponseHeadersLength="size"  
  maximumErrorResponseLength="size"  
  maximumUnauthorizedUploadLength="size"  
  useUnsafeHeaderParsing="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e8b3-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5e8b3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5e8b3-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e8b3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5e8b3-111">Attributes</span></span>  
  
|<span data-ttu-id="5e8b3-112">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="5e8b3-112">**Attribute**</span></span>|<span data-ttu-id="5e8b3-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5e8b3-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`maximumResponseHeadersLength`|<span data-ttu-id="5e8b3-114">Указывает максимальную длину заголовка ответа, в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-114">Specifies the maximum length of a response header, in kilobytes.</span></span> <span data-ttu-id="5e8b3-115">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-115">The default is 64.</span></span> <span data-ttu-id="5e8b3-116">Значение -1 указывает, что нет ограничения размера накладывается на заголовки ответа.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-116">A value of -1 indicates that no size limit will be imposed on the response headers.</span></span>|  
|`maximumErrorResponseLength`|<span data-ttu-id="5e8b3-117">Указывает максимальную длину ответа об ошибке, в килобайтах.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-117">Specifies the maximum length of an error response, in kilobytes.</span></span> <span data-ttu-id="5e8b3-118">Значение по умолчанию — 64.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-118">The default is 64.</span></span> <span data-ttu-id="5e8b3-119">Значение -1 указывает, что нет ограничения размера накладывается на сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-119">A value of -1 indicates that no size limit will be imposed on the error response.</span></span>|  
|`maximumUnauthorizedUploadLength`|<span data-ttu-id="5e8b3-120">Указывает максимальную длину данных, передаваемых в ответ на код ошибки доступа, в байтах.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-120">Specifies the maximum length of an upload in response to an unauthorized error code, in bytes.</span></span> <span data-ttu-id="5e8b3-121">Значение по умолчанию — -1.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-121">The default is -1.</span></span> <span data-ttu-id="5e8b3-122">Значение -1 указывает, что нет ограничения размера накладывается на отправку.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-122">A value of -1 indicates that no size limit will be imposed on the upload.</span></span>|  
|`useUnsafeHeaderParsing`|<span data-ttu-id="5e8b3-123">Указывает, включена ли разбор небезопасных заголовков.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-123">Specifies whether unsafe header parsing is enabled.</span></span> <span data-ttu-id="5e8b3-124">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-124">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e8b3-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5e8b3-125">Child Elements</span></span>  
 <span data-ttu-id="5e8b3-126">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e8b3-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5e8b3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5e8b3-128">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="5e8b3-128">**Element**</span></span>|<span data-ttu-id="5e8b3-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="5e8b3-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5e8b3-130">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e8b3-130">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="5e8b3-131">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-131">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e8b3-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="5e8b3-132">Remarks</span></span>  
 <span data-ttu-id="5e8b3-133">По умолчанию .NET Framework строго контролирует соблюдение RFC 2616 для синтаксического анализа URI.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-133">By default, the .NET Framework strictly enforces RFC 2616 for URI parsing.</span></span> <span data-ttu-id="5e8b3-134">Некоторые ответы сервера могут содержать управляющие символы в запрещенных полях, которые могут вызвать <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> метод выдает исключение <xref:System.Net.WebException>.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-134">Some server responses may include control characters in prohibited fields, which will cause the <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> method to throw a <xref:System.Net.WebException>.</span></span> <span data-ttu-id="5e8b3-135">Если **useUnsafeHeaderParsing** присваивается **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> не вызывает исключение в данном случае; тем не менее, приложение будет уязвимо для некоторых форм синтаксический анализ атаки URI.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-135">If **useUnsafeHeaderParsing** is set to **true**, <xref:System.Net.HttpWebRequest.GetResponse?displayProperty=nameWithType> will not throw in this case; however, your application will be vulnerable to several forms of URI parsing attacks.</span></span> <span data-ttu-id="5e8b3-136">Наилучшим решением является изменение сервера, таким образом, ответ содержит управляющих символов.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-136">The best solution is to change the server so that the response does not include control characters.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="5e8b3-137">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="5e8b3-137">Configuration Files</span></span>  
 <span data-ttu-id="5e8b3-138">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="5e8b3-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e8b3-139">Пример</span><span class="sxs-lookup"><span data-stu-id="5e8b3-139">Example</span></span>  
 <span data-ttu-id="5e8b3-140">В следующем примере показано, как задать большую чем обычно длину заголовка.</span><span class="sxs-lookup"><span data-stu-id="5e8b3-140">The following example shows how to specify a larger than normal maximum header length.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5e8b3-141">См. также</span><span class="sxs-lookup"><span data-stu-id="5e8b3-141">See also</span></span>
- <xref:System.Net.HttpWebRequest.MaximumResponseHeadersLength%2A>
- [<span data-ttu-id="5e8b3-142">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="5e8b3-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
