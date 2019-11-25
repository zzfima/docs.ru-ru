---
title: Элемент <httpListener> (параметры сети)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 0054be3d2002e4ea5247f25d8094386ac7242422
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088380"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="f54f3-102">Элемент \<httpListener > (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f54f3-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="f54f3-103">Настраивает параметры, используемые классом <xref:System.Net.HttpListener>.</span><span class="sxs-lookup"><span data-stu-id="f54f3-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  

<span data-ttu-id="f54f3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f54f3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f54f3-105">&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f54f3-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="f54f3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](settings-element-network-settings.md) ></span><span class="sxs-lookup"><span data-stu-id="f54f3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>\
<span data-ttu-id="f54f3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<httpListener >**</span><span class="sxs-lookup"><span data-stu-id="f54f3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<httpListener>**</span></span>

## <a name="syntax"></a><span data-ttu-id="f54f3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f54f3-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="f54f3-109">Type</span><span class="sxs-lookup"><span data-stu-id="f54f3-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f54f3-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f54f3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f54f3-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f54f3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f54f3-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f54f3-112">Attributes</span></span>  
  
|<span data-ttu-id="f54f3-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f54f3-113">Attribute</span></span>|<span data-ttu-id="f54f3-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f54f3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f54f3-115">унескаперекуестурл</span><span class="sxs-lookup"><span data-stu-id="f54f3-115">unescapeRequestUrl</span></span>|<span data-ttu-id="f54f3-116">Логическое значение, указывающее, использует ли экземпляр <xref:System.Net.HttpListener> Необработанный универсальный код ресурса (URI) без экранирования вместо преобразованного URI.</span><span class="sxs-lookup"><span data-stu-id="f54f3-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f54f3-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f54f3-117">Child Elements</span></span>  
 <span data-ttu-id="f54f3-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f54f3-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f54f3-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f54f3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f54f3-120">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f54f3-120">**Element**</span></span>|<span data-ttu-id="f54f3-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f54f3-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f54f3-122">Параметры</span><span class="sxs-lookup"><span data-stu-id="f54f3-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="f54f3-123">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="f54f3-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f54f3-124">Заметки</span><span class="sxs-lookup"><span data-stu-id="f54f3-124">Remarks</span></span>  
 <span data-ttu-id="f54f3-125">Атрибут **унескаперекуестурл** указывает, использует ли <xref:System.Net.HttpListener> необработанный неэкранированный универсальный код ресурса (URI) вместо преобразованного универсального кода ресурса (URI), в котором преобразовываются все значения в кодировке% и выполняются другие действия нормализации.</span><span class="sxs-lookup"><span data-stu-id="f54f3-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="f54f3-126">Когда экземпляр <xref:System.Net.HttpListener> получает запрос через службу `http.sys`, он создает экземпляр строки URI, предоставленный `http.sys`, и предоставляет его в качестве свойства <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f54f3-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="f54f3-127">Служба `http.sys` предоставляет две строки URI запроса:</span><span class="sxs-lookup"><span data-stu-id="f54f3-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="f54f3-128">Необработанный URI</span><span class="sxs-lookup"><span data-stu-id="f54f3-128">Raw URI</span></span>  
  
- <span data-ttu-id="f54f3-129">Преобразованный URI</span><span class="sxs-lookup"><span data-stu-id="f54f3-129">Converted URI</span></span>  
  
 <span data-ttu-id="f54f3-130">Необработанный URI является <xref:System.Uri?displayProperty=nameWithType>, указанным в строке запроса HTTP-запроса:</span><span class="sxs-lookup"><span data-stu-id="f54f3-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="f54f3-131">Необработанный URI, предоставленный `http.sys` для запроса, указанного выше, — "/Пас/".</span><span class="sxs-lookup"><span data-stu-id="f54f3-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="f54f3-132">Представляет строку, следующую за HTTP-командой в том виде, в котором она была отправлена по сети.</span><span class="sxs-lookup"><span data-stu-id="f54f3-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="f54f3-133">Служба `http.sys` создает преобразованный универсальный код ресурса (URI) из информации, предоставленной в запросе, используя URI, указанный в строке запроса HTTP, и заголовок узла для определения сервера-источника, на который должен быть перенаправлен запрос.</span><span class="sxs-lookup"><span data-stu-id="f54f3-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="f54f3-134">Это делается путем сравнения информации из запроса с набором зарегистрированных префиксов URI.</span><span class="sxs-lookup"><span data-stu-id="f54f3-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="f54f3-135">В документации по пакету SDK для HTTP-сервера этот преобразованный универсальный код ресурса (URI) называется структурой HTTP_COOKED_URL.</span><span class="sxs-lookup"><span data-stu-id="f54f3-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="f54f3-136">Чтобы иметь возможность сравнить запрос с зарегистрированными префиксами URI, необходимо выполнить некоторую нормализацию запроса.</span><span class="sxs-lookup"><span data-stu-id="f54f3-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="f54f3-137">Для примера выше преобразованный URI будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f54f3-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="f54f3-138">Служба `http.sys` объединяет значение свойства <xref:System.Uri.Host%2A?displayProperty=nameWithType> и строку в строке запроса для создания преобразованного универсального кода ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="f54f3-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="f54f3-139">Кроме того, `http.sys` и класс <xref:System.Uri?displayProperty=nameWithType> также выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="f54f3-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="f54f3-140">Отменяет экранирование всех закодированных в процентах значений.</span><span class="sxs-lookup"><span data-stu-id="f54f3-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="f54f3-141">Преобразует символы, не входящие в набор ASCII, в кодировку UTF-16 в символьное представление.</span><span class="sxs-lookup"><span data-stu-id="f54f3-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="f54f3-142">Обратите внимание, что символы UTF-8 и ANSI/DBCS поддерживаются, а также символы Юникода (Кодировка Юникода с использованием формата% Укскскскс).</span><span class="sxs-lookup"><span data-stu-id="f54f3-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="f54f3-143">Выполняет другие шаги нормализации, например сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="f54f3-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="f54f3-144">Поскольку запрос не содержит никаких сведений о кодировке, используемой для значений, закодированных в процентах, возможно, вам не удастся определить правильную кодировку путем анализа значений, закодированных в процентах.</span><span class="sxs-lookup"><span data-stu-id="f54f3-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="f54f3-145">Поэтому `http.sys` предоставляет два раздела реестра для изменения процесса:</span><span class="sxs-lookup"><span data-stu-id="f54f3-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="f54f3-146">Раздел реестра .</span><span class="sxs-lookup"><span data-stu-id="f54f3-146">Registry Key</span></span>|<span data-ttu-id="f54f3-147">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f54f3-147">Default Value</span></span>|<span data-ttu-id="f54f3-148">Описание</span><span class="sxs-lookup"><span data-stu-id="f54f3-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="f54f3-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="f54f3-149">EnableNonUTF8</span></span>|<span data-ttu-id="f54f3-150">1</span><span class="sxs-lookup"><span data-stu-id="f54f3-150">1</span></span>|<span data-ttu-id="f54f3-151">Если значение равно нулю, `http.sys` принимает только URL-адреса в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f54f3-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="f54f3-152">Если не равен нулю, `http.sys` также принимает в запросах URL-адреса в кодировке ANSI или в кодировке DBCS.</span><span class="sxs-lookup"><span data-stu-id="f54f3-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="f54f3-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="f54f3-153">FavorUTF8</span></span>|<span data-ttu-id="f54f3-154">1</span><span class="sxs-lookup"><span data-stu-id="f54f3-154">1</span></span>|<span data-ttu-id="f54f3-155">Если не равен нулю, `http.sys` всегда пытается декодировать URL-адрес как UTF-8. Если преобразование завершается неудачно и EnableNonUTF8 имеет ненулевое значение, HTTP. sys пытается декодировать его как ANSI или DBCS.</span><span class="sxs-lookup"><span data-stu-id="f54f3-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="f54f3-156">Если ноль (и EnableNonUTF8 не равен нулю), `http.sys` пытается декодировать его как ANSI или DBCS; Если это не удалось, то пытается выполнить преобразование UTF-8.</span><span class="sxs-lookup"><span data-stu-id="f54f3-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="f54f3-157">Когда <xref:System.Net.HttpListener> получает запрос, он использует преобразованный универсальный код ресурса (URI) из `http.sys` в качестве входных данных для свойства <xref:System.Net.HttpListenerRequest.Url%2A>.</span><span class="sxs-lookup"><span data-stu-id="f54f3-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="f54f3-158">Есть необходимость в поддержке символов помимо символов и чисел в URI.</span><span class="sxs-lookup"><span data-stu-id="f54f3-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="f54f3-159">Примером является следующий универсальный код ресурса (URI), который используется для получения сведений о клиенте для номера клиента «1/3812»:</span><span class="sxs-lookup"><span data-stu-id="f54f3-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="f54f3-160">Обратите внимание на косую черту в формате URI (% 2F).</span><span class="sxs-lookup"><span data-stu-id="f54f3-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="f54f3-161">Это необходимо, поскольку в данном случае символ косой черты представляет данные, а не разделитель пути.</span><span class="sxs-lookup"><span data-stu-id="f54f3-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="f54f3-162">Передача строки в конструктор URI приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="f54f3-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="f54f3-163">Разделение пути на сегменты приведет к следующим элементам:</span><span class="sxs-lookup"><span data-stu-id="f54f3-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="f54f3-164">Это не цель отправителя запроса.</span><span class="sxs-lookup"><span data-stu-id="f54f3-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="f54f3-165">Если атрибут **унескаперекуестурл** имеет значение **false**, то когда <xref:System.Net.HttpListener> получает запрос, он использует необработанный универсальный код ресурса (URI) вместо преобразованного URI из `http.sys` в качестве входных данных для свойства <xref:System.Net.HttpListenerRequest.Url%2A>.</span><span class="sxs-lookup"><span data-stu-id="f54f3-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="f54f3-166">Значение по умолчанию для атрибута **унескаперекуестурл** — **true**.</span><span class="sxs-lookup"><span data-stu-id="f54f3-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="f54f3-167">Свойство <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> можно использовать для получения текущего значения атрибута **унескаперекуестурл** из применимых файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f54f3-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f54f3-168">Пример</span><span class="sxs-lookup"><span data-stu-id="f54f3-168">Example</span></span>  
 <span data-ttu-id="f54f3-169">В следующем примере показано, как настроить класс <xref:System.Net.HttpListener> при получении запроса на использование необработанного URI вместо преобразованного универсального кода ресурса (URI) из `http.sys` в качестве входных данных для свойства <xref:System.Net.HttpListenerRequest.Url%2A>.</span><span class="sxs-lookup"><span data-stu-id="f54f3-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <httpListener  
        unescapeRequestUrl="false"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="f54f3-170">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="f54f3-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="f54f3-171">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="f54f3-171">Namespace</span></span>|<span data-ttu-id="f54f3-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="f54f3-172">System.Net</span></span>|  
|<span data-ttu-id="f54f3-173">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="f54f3-173">Schema Name</span></span>||  
|<span data-ttu-id="f54f3-174">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="f54f3-174">Validation File</span></span>||  
|<span data-ttu-id="f54f3-175">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="f54f3-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="f54f3-176">См. также</span><span class="sxs-lookup"><span data-stu-id="f54f3-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="f54f3-177">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f54f3-177">Network Settings Schema</span></span>](index.md)
