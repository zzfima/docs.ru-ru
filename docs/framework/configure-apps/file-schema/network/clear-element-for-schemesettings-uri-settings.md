---
title: '&lt;Очистить&gt; элемент для schemeSettings (параметры Uri)'
ms.date: 03/30/2017
ms.assetid: 65098332-ce61-4542-ab8d-e7dc0257d31f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: f0daa689ba09fa39ffe0f38d769112f0f095592a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47230843"
---
# <a name="ltcleargt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="f03f1-102">&lt;Очистить&gt; элемент для schemeSettings (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="f03f1-102">&lt;clear&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="f03f1-103">Удаляет все существующие параметры схемы.</span><span class="sxs-lookup"><span data-stu-id="f03f1-103">Clears all existing scheme settings.</span></span>  
  
 <span data-ttu-id="f03f1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f03f1-104">\<configuration></span></span>  
<span data-ttu-id="f03f1-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="f03f1-105">\<uri></span></span>  
<span data-ttu-id="f03f1-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="f03f1-106">\<schemeSettings></span></span>  
<span data-ttu-id="f03f1-107">\<Очистить ></span><span class="sxs-lookup"><span data-stu-id="f03f1-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f03f1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f03f1-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f03f1-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f03f1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="f03f1-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f03f1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f03f1-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f03f1-111">Attributes</span></span>  
 <span data-ttu-id="f03f1-112">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f03f1-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f03f1-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f03f1-113">Child Elements</span></span>  
 <span data-ttu-id="f03f1-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f03f1-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f03f1-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f03f1-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f03f1-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="f03f1-116">Element</span></span>|<span data-ttu-id="f03f1-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f03f1-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f03f1-118">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="f03f1-118">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="f03f1-119">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="f03f1-119">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f03f1-120">Примечания</span><span class="sxs-lookup"><span data-stu-id="f03f1-120">Remarks</span></span>  
 <span data-ttu-id="f03f1-121">По умолчанию <xref:System.Uri?displayProperty=nameWithType> знаком процента Отмена переходов класс разделители пути до выполнения сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="f03f1-121">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="f03f1-122">Это было реализовано в качестве механизма защиты от атак, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f03f1-122">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="f03f1-123">Если этот URI передается вниз, чтобы модули не обрабатывает процентов символы в кодировке неправильно, это может привести в следующей команде, выполняемой на сервере:</span><span class="sxs-lookup"><span data-stu-id="f03f1-123">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="f03f1-124">По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути Отмена переходов, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="f03f1-124">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="f03f1-125">Результат передачи вредоносных URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:</span><span class="sxs-lookup"><span data-stu-id="f03f1-125">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="f03f1-126">Можно изменить это поведение по умолчанию для не разделители отмены escape процента закодированный путь, с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="f03f1-126">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f03f1-127">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="f03f1-127">Configuration Files</span></span>  
 <span data-ttu-id="f03f1-128">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f03f1-128">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f03f1-129">Пример</span><span class="sxs-lookup"><span data-stu-id="f03f1-129">Example</span></span>  
 <span data-ttu-id="f03f1-130">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс, который удаляет все параметры схемы, а затем добавляет поддержку не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="f03f1-130">The following example shows a configuration used by the <xref:System.Uri> class that clears all scheme settings and then adds support for not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f03f1-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f03f1-131">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="f03f1-132">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f03f1-132">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
