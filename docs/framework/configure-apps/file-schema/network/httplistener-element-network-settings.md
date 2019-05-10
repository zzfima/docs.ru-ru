---
title: Элемент <httpListener> (параметры сети)
ms.date: 03/30/2017
ms.assetid: 62f121fd-3f2e-4033-bb39-48ae996bfbd9
ms.openlocfilehash: 8257b0311e18a21fbc04185f8297ee8e5f38b86b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592746"
---
# <a name="httplistener-element-network-settings"></a><span data-ttu-id="0b36e-102">\<httpListener > (сетевые параметры)</span><span class="sxs-lookup"><span data-stu-id="0b36e-102">\<httpListener> Element (Network Settings)</span></span>
<span data-ttu-id="0b36e-103">Настраивает параметры, используемые <xref:System.Net.HttpListener> класса.</span><span class="sxs-lookup"><span data-stu-id="0b36e-103">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>  
  
 <span data-ttu-id="0b36e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0b36e-104">\<configuration></span></span>  
<span data-ttu-id="0b36e-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="0b36e-105">\<system.net></span></span>  
<span data-ttu-id="0b36e-106">\<Параметры ></span><span class="sxs-lookup"><span data-stu-id="0b36e-106">\<settings></span></span>  
<span data-ttu-id="0b36e-107">\<httpListener></span><span class="sxs-lookup"><span data-stu-id="0b36e-107">\<httpListener></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b36e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b36e-108">Syntax</span></span>  
  
```xml  
<httpListener  
  unescapeRequestUrl="true|false"  
/>  
```  
  
## <a name="type"></a><span data-ttu-id="0b36e-109">Тип</span><span class="sxs-lookup"><span data-stu-id="0b36e-109">Type</span></span>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b36e-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b36e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="0b36e-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b36e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b36e-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b36e-112">Attributes</span></span>  
  
|<span data-ttu-id="0b36e-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0b36e-113">Attribute</span></span>|<span data-ttu-id="0b36e-114">Описание</span><span class="sxs-lookup"><span data-stu-id="0b36e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0b36e-115">unescapeRequestUrl</span><span class="sxs-lookup"><span data-stu-id="0b36e-115">unescapeRequestUrl</span></span>|<span data-ttu-id="0b36e-116">Логическое значение, указывающее, если <xref:System.Net.HttpListener> экземпляр использует преобразованный в escape-последовательность URI вместо преобразованного.</span><span class="sxs-lookup"><span data-stu-id="0b36e-116">A Boolean value that indicates if a <xref:System.Net.HttpListener> instance uses the raw unescaped URI instead of the converted URI.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b36e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b36e-117">Child Elements</span></span>  
 <span data-ttu-id="0b36e-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0b36e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b36e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b36e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0b36e-120">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="0b36e-120">**Element**</span></span>|<span data-ttu-id="0b36e-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0b36e-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="0b36e-122">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b36e-122">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="0b36e-123">Настраивает основные параметры сети для пространства имен <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="0b36e-123">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b36e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b36e-124">Remarks</span></span>  
 <span data-ttu-id="0b36e-125">**UnescapeRequestUrl** атрибут указывает, если <xref:System.Net.HttpListener> использует преобразованный в escape-последовательность URI вместо преобразованного где преобразуются значения, закодированные и других нормализации действия предпринимаются.</span><span class="sxs-lookup"><span data-stu-id="0b36e-125">The **unescapeRequestUrl** attribute indicates if <xref:System.Net.HttpListener> uses the raw unescaped URI instead of the converted URI where any percent-encoded values are converted and other normalization steps are taken.</span></span>  
  
 <span data-ttu-id="0b36e-126">Когда <xref:System.Net.HttpListener> экземпляр получает запрос через `http.sys` службы, она создает экземпляр в строке URI, предоставляемые `http.sys`и предоставляет его как <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="0b36e-126">When a <xref:System.Net.HttpListener> instance receives a request through the `http.sys` service, it creates an instance of the URI string provided by `http.sys`, and exposes it as the <xref:System.Net.HttpListenerRequest.Url%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="0b36e-127">`http.sys` Служба предоставляет две строки URI запроса:</span><span class="sxs-lookup"><span data-stu-id="0b36e-127">The `http.sys` service exposes two request URI strings:</span></span>  
  
- <span data-ttu-id="0b36e-128">Преобразованный в URI</span><span class="sxs-lookup"><span data-stu-id="0b36e-128">Raw URI</span></span>  
  
- <span data-ttu-id="0b36e-129">Преобразованный URI</span><span class="sxs-lookup"><span data-stu-id="0b36e-129">Converted URI</span></span>  
  
 <span data-ttu-id="0b36e-130">Необработанный URL-адрес является <xref:System.Uri?displayProperty=nameWithType> в строке запроса HTTP-запроса:</span><span class="sxs-lookup"><span data-stu-id="0b36e-130">The raw URI is the <xref:System.Uri?displayProperty=nameWithType> provided in the request line of a HTTP request:</span></span>  
  
 `GET /path/`  
  
 `Host: www.contoso.com`  
  
 <span data-ttu-id="0b36e-131">Преобразованный в URI, предоставляемые `http.sys` для запроса, упомянутого выше, является «/ path /».</span><span class="sxs-lookup"><span data-stu-id="0b36e-131">The raw URI provided by `http.sys` for the request mentioned above, is "/path/".</span></span> <span data-ttu-id="0b36e-132">Представляет строку, следующую команду HTTP, так как он был отправлен по сети.</span><span class="sxs-lookup"><span data-stu-id="0b36e-132">This represents the string following the HTTP verb as it was sent over the network.</span></span>  
  
 <span data-ttu-id="0b36e-133">`http.sys` Служба создает преобразованный URI из сведений, предоставленных в запросе с помощью URI, предоставленный в строке запроса HTTP и должны быть переадресованы заголовок узла для определения сервера-источника запроса.</span><span class="sxs-lookup"><span data-stu-id="0b36e-133">The `http.sys` service creates a converted URI from the information provided in the request by using the URI provided in the HTTP request line and the Host header to determine the origin server the request should be forwarded to.</span></span> <span data-ttu-id="0b36e-134">Это делается путем сравнения сведений из запроса с помощью набора зарегистрированных префиксов URI.</span><span class="sxs-lookup"><span data-stu-id="0b36e-134">This is done by comparing the information from the request with a set of registered URI prefixes.</span></span> <span data-ttu-id="0b36e-135">В документации пакета SDK сервера HTTP ссылается на этот преобразованный URI как HTTP_COOKED_URL структуры.</span><span class="sxs-lookup"><span data-stu-id="0b36e-135">The HTTP Server SDK documentation refers to this converted URI as the HTTP_COOKED_URL structure.</span></span>  
  
 <span data-ttu-id="0b36e-136">Чтобы иметь возможность сравнить запрос с зарегистрированными префиксами URI, необходимо сделать некоторые нормализацию в запросе.</span><span class="sxs-lookup"><span data-stu-id="0b36e-136">In order to be able to compare the request with registered URI prefixes, some normalization to the request needs to be done.</span></span> <span data-ttu-id="0b36e-137">Для примера выше преобразованный URI будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="0b36e-137">For the sample above the converted URI would be as follows:</span></span>  
  
 `http://www.contoso.com/path/`  
  
 <span data-ttu-id="0b36e-138">`http.sys` Службы объединяет <xref:System.Uri.Host%2A?displayProperty=nameWithType> значение свойства и строку в строку запроса для создания преобразованный URI.</span><span class="sxs-lookup"><span data-stu-id="0b36e-138">The `http.sys` service combines the <xref:System.Uri.Host%2A?displayProperty=nameWithType> property value and the string in the request line to create a converted URI.</span></span> <span data-ttu-id="0b36e-139">Кроме того `http.sys` и <xref:System.Uri?displayProperty=nameWithType> класс также выполняет следующее:</span><span class="sxs-lookup"><span data-stu-id="0b36e-139">In addition, `http.sys` and the <xref:System.Uri?displayProperty=nameWithType> class also does the following:</span></span>  
  
- <span data-ttu-id="0b36e-140">Отмена переходов все процентные значения.</span><span class="sxs-lookup"><span data-stu-id="0b36e-140">Un-escapes all percent encoded values.</span></span>  
  
- <span data-ttu-id="0b36e-141">Преобразует закодированные символы не из набора ASCII в представление символов UTF-16.</span><span class="sxs-lookup"><span data-stu-id="0b36e-141">Converts percent-encoded non-ASCII characters into a UTF-16 character representation.</span></span> <span data-ttu-id="0b36e-142">Обратите внимание на то, что символы UTF-8 и ANSI/DBCS поддерживаются, а также символы Юникода (кодировка Юникод с использованием формата % uXXXX).</span><span class="sxs-lookup"><span data-stu-id="0b36e-142">Note that UTF-8 and ANSI/DBCS characters are supported as well as Unicode characters (Unicode encoding using the %uXXXX format).</span></span>  
  
- <span data-ttu-id="0b36e-143">Выполняет другие действия нормализации, такие как сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="0b36e-143">Executes other normalization steps, like path compression.</span></span>  
  
 <span data-ttu-id="0b36e-144">Так как запрос не содержит никакой информации о кодировку, используемую для значения, закодированные процентами, может оказаться невозможно определить правильную кодировку просто, путем синтаксического анализа закодированные значения.</span><span class="sxs-lookup"><span data-stu-id="0b36e-144">Since the request doesn't contain any information about the encoding used for percent-encoded values, it may not be possible to determine the correct encoding just by parsing the percent-encoded values.</span></span>  
  
 <span data-ttu-id="0b36e-145">Таким образом `http.sys` предоставляет два раздела реестра для изменения процесса:</span><span class="sxs-lookup"><span data-stu-id="0b36e-145">Therefore `http.sys` provides two registry keys for modifying the process:</span></span>  
  
|<span data-ttu-id="0b36e-146">Раздел реестра .</span><span class="sxs-lookup"><span data-stu-id="0b36e-146">Registry Key</span></span>|<span data-ttu-id="0b36e-147">Значение по умолчанию</span><span class="sxs-lookup"><span data-stu-id="0b36e-147">Default Value</span></span>|<span data-ttu-id="0b36e-148">Описание</span><span class="sxs-lookup"><span data-stu-id="0b36e-148">Description</span></span>|  
|------------------|-------------------|-----------------|  
|<span data-ttu-id="0b36e-149">EnableNonUTF8</span><span class="sxs-lookup"><span data-stu-id="0b36e-149">EnableNonUTF8</span></span>|<span data-ttu-id="0b36e-150">1</span><span class="sxs-lookup"><span data-stu-id="0b36e-150">1</span></span>|<span data-ttu-id="0b36e-151">Если значение равно нулю, `http.sys` принимает только URL-адреса в кодировке UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0b36e-151">If zero, `http.sys` accepts only UTF-8-encoded URLs.</span></span><br /><br /> <span data-ttu-id="0b36e-152">Если ненулевое значение, `http.sys` также принимает URL-адреса в кодировке ANSI или кодировке (DBCS) в запросах.</span><span class="sxs-lookup"><span data-stu-id="0b36e-152">If non-zero, `http.sys` also accepts ANSI-encoded or DBCS-encoded URLs in requests.</span></span>|  
|<span data-ttu-id="0b36e-153">FavorUTF8</span><span class="sxs-lookup"><span data-stu-id="0b36e-153">FavorUTF8</span></span>|<span data-ttu-id="0b36e-154">1</span><span class="sxs-lookup"><span data-stu-id="0b36e-154">1</span></span>|<span data-ttu-id="0b36e-155">Если ненулевое значение, `http.sys` всегда пытается декодировать URL-адрес как UTF-8; Если это преобразование завершается неудачей и EnableNonUTF8 не равно нулю, Http.sys, а затем пытается декодировать его как ANSI или DBCS.</span><span class="sxs-lookup"><span data-stu-id="0b36e-155">If non-zero, `http.sys` always tries to decode a URL as UTF-8 first; if that conversion fails and EnableNonUTF8 is non-zero, Http.sys then tries to decode it as ANSI or DBCS.</span></span><br /><br /> <span data-ttu-id="0b36e-156">Если значение равно нулю (и EnableNonUTF8 не равно нулю), `http.sys` пытается декодировать его как ANSI или DBCS; Если это не обнаруживаются, осуществляется попытка преобразования UTF-8.</span><span class="sxs-lookup"><span data-stu-id="0b36e-156">If zero (and EnableNonUTF8 is non-zero), `http.sys` tries to decode it as ANSI or DBCS; if that is not successful, it tries a UTF-8 conversion.</span></span>|  
  
 <span data-ttu-id="0b36e-157">Когда <xref:System.Net.HttpListener> получает запрос, он использует URI, преобразованное из `http.sys` качестве входных данных для <xref:System.Net.HttpListenerRequest.Url%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0b36e-157">When <xref:System.Net.HttpListener> receives a request, it uses the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="0b36e-158">Нет необходимости поддерживать символы помимо символов и цифр в URI.</span><span class="sxs-lookup"><span data-stu-id="0b36e-158">There is a need for supporting characters besides characters and numbers in URIs.</span></span> <span data-ttu-id="0b36e-159">Например, следующий URI, который используется для получения данных о заказчике для клиента номер «1/3812»:</span><span class="sxs-lookup"><span data-stu-id="0b36e-159">An example is the following URI, which is used to retrieve customer information for customer number "1/3812":</span></span>  
  
 `http://www.contoso.com/Customer('1%2F3812')/`  
  
 <span data-ttu-id="0b36e-160">Обратите внимание, закодированные процентами косую черту в Uri (% 2F).</span><span class="sxs-lookup"><span data-stu-id="0b36e-160">Note the percent-encoded slash in the Uri (%2F).</span></span> <span data-ttu-id="0b36e-161">Это необходимо, так как в этом случае косая черта представляет данные, а не завершает путь.</span><span class="sxs-lookup"><span data-stu-id="0b36e-161">This is necessary, since in this case the slash character represents data and not a path delimiter.</span></span>  
  
 <span data-ttu-id="0b36e-162">Передачи строки конструктору Uri приведет к следующим URI:</span><span class="sxs-lookup"><span data-stu-id="0b36e-162">Passing the string to Uri constructor will lead to the following URI:</span></span>  
  
 `http://www.contoso.com/Customer('1/3812')/`  
  
 <span data-ttu-id="0b36e-163">Разделение на сегменты пути приведет к появлению следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="0b36e-163">Splitting the path into its segments would result in the following elements:</span></span>  
  
 `Customer('1`  
  
 `3812')`  
  
 <span data-ttu-id="0b36e-164">Это не является целью отправителя запроса.</span><span class="sxs-lookup"><span data-stu-id="0b36e-164">This is not the intent of the sender of the request.</span></span>  
  
 <span data-ttu-id="0b36e-165">Если **unescapeRequestUrl** атрибуту присваивается **false**, то при <xref:System.Net.HttpListener> получает запрос, он использует преобразованный URI вместо преобразованного из `http.sys` как входные данные <xref:System.Net.HttpListenerRequest.Url%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0b36e-165">If the **unescapeRequestUrl** attribute is set to **false**, then when the <xref:System.Net.HttpListener> receives a request, it uses the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
 <span data-ttu-id="0b36e-166">Значение по умолчанию для **unescapeRequestUrl** атрибут **true**.</span><span class="sxs-lookup"><span data-stu-id="0b36e-166">The default value for the **unescapeRequestUrl** attribute is **true**.</span></span>  
  
 <span data-ttu-id="0b36e-167"><xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> Свойство может использоваться для получения текущего значения **unescapeRequestUrl** атрибут из применимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0b36e-167">The <xref:System.Net.Configuration.HttpListenerElement.UnescapeRequestUrl%2A> property can be used to get the current value of the **unescapeRequestUrl** attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b36e-168">Пример</span><span class="sxs-lookup"><span data-stu-id="0b36e-168">Example</span></span>  
 <span data-ttu-id="0b36e-169">В следующем примере показано, как настроить <xref:System.Net.HttpListener> класс при получении запроса для использования необработанных URI вместо преобразованного из `http.sys` качестве входных данных для <xref:System.Net.HttpListenerRequest.Url%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0b36e-169">The following example shows how to configure the <xref:System.Net.HttpListener> class when it receives a request to use the raw URI instead of the converted URI from `http.sys` as input to the <xref:System.Net.HttpListenerRequest.Url%2A> property.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="0b36e-170">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="0b36e-170">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="0b36e-171">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="0b36e-171">Namespace</span></span>|<span data-ttu-id="0b36e-172">System.Net</span><span class="sxs-lookup"><span data-stu-id="0b36e-172">System.Net</span></span>|  
|<span data-ttu-id="0b36e-173">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="0b36e-173">Schema Name</span></span>||  
|<span data-ttu-id="0b36e-174">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="0b36e-174">Validation File</span></span>||  
|<span data-ttu-id="0b36e-175">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="0b36e-175">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="0b36e-176">См. также</span><span class="sxs-lookup"><span data-stu-id="0b36e-176">See also</span></span>

- <xref:System.Net.Configuration.HttpListenerElement>
- <xref:System.Net.HttpListener>
- <xref:System.Net.HttpListenerRequest.Url%2A>
- [<span data-ttu-id="0b36e-177">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="0b36e-177">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
