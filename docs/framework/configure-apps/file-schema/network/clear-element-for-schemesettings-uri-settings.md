---
title: '&lt;Очистить&gt; элемент для schemeSettings (параметры Uri)'
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 32c7a9e07b48536584f7ca5588226fb4479bacb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="b08f7-102">&lt;Очистить&gt; элемент для schemeSettings (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="b08f7-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="b08f7-103">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="b08f7-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="b08f7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b08f7-104">\<configuration></span></span>  
<span data-ttu-id="b08f7-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="b08f7-105">\<uri></span></span>  
<span data-ttu-id="b08f7-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="b08f7-106">\<schemeSettings></span></span>  
<span data-ttu-id="b08f7-107">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="b08f7-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b08f7-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b08f7-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b08f7-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b08f7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="b08f7-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b08f7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b08f7-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b08f7-111">Attributes</span></span>  
 <span data-ttu-id="b08f7-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b08f7-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b08f7-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b08f7-113">Child Elements</span></span>  
 <span data-ttu-id="b08f7-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b08f7-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b08f7-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b08f7-115">Parent Elements</span></span>  
  
|<span data-ttu-id="b08f7-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="b08f7-116">Element</span></span>|<span data-ttu-id="b08f7-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b08f7-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b08f7-118">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="b08f7-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="b08f7-119">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="b08f7-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b08f7-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="b08f7-120">Remarks</span></span>  
 <span data-ttu-id="b08f7-121">По умолчанию <xref:System.Uri?displayProperty=nameWithType> процентов класс un-escape-символы в кодировке разделители пути до выполнения сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="b08f7-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="b08f7-122">Это было реализовано в качестве механизма защиты от атак на систему следующим образом:</span><span class="sxs-lookup"><span data-stu-id="b08f7-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b08f7-123">Если этот URI передается вниз к модулям не обрабатывает процентов символы в кодировке правильно, это может привести в следующей команде, выполняемой на сервере:</span><span class="sxs-lookup"><span data-stu-id="b08f7-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="b08f7-124">По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути un-escape-последовательности, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="b08f7-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="b08f7-125">Результат передачи вредоносного URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:</span><span class="sxs-lookup"><span data-stu-id="b08f7-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="b08f7-126">Можно изменить это поведение по умолчанию для не разделители un escape-символ процента закодированный путь, с помощью параметра конфигурации schemeSettings для нужной раскладки.</span><span class="sxs-lookup"><span data-stu-id="b08f7-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="b08f7-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="b08f7-127">Configuration Files</span></span>  
 <span data-ttu-id="b08f7-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b08f7-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b08f7-129">Пример</span><span class="sxs-lookup"><span data-stu-id="b08f7-129">Example</span></span>  
 <span data-ttu-id="b08f7-130">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс, который удаляет все параметры схемы, а затем добавляет поддержку не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="b08f7-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <clear/>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b08f7-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b08f7-131">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="b08f7-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="b08f7-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
