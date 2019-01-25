---
title: '&lt;Добавление&gt; элемент для schemeSettings (параметры Uri)'
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: d64744cf3c88d5ec0f0edf1a31cdf184c3c8277e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54524108"
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="eabf0-102">&lt;Добавление&gt; элемент для schemeSettings (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="eabf0-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="eabf0-103">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="eabf0-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="eabf0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="eabf0-104">\<configuration></span></span>  
<span data-ttu-id="eabf0-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="eabf0-105">\<uri></span></span>  
<span data-ttu-id="eabf0-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="eabf0-106">\<schemeSettings></span></span>  
<span data-ttu-id="eabf0-107">\<add></span><span class="sxs-lookup"><span data-stu-id="eabf0-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eabf0-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eabf0-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eabf0-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eabf0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eabf0-110">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eabf0-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eabf0-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eabf0-111">Attributes</span></span>  
  
|<span data-ttu-id="eabf0-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eabf0-112">Attribute</span></span>|<span data-ttu-id="eabf0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="eabf0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eabf0-114">имя</span><span class="sxs-lookup"><span data-stu-id="eabf0-114">name</span></span>|<span data-ttu-id="eabf0-115">Имя схемы, к которому применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="eabf0-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="eabf0-116">Только поддерживаемые значения: имя = «http» и имя = «https».</span><span class="sxs-lookup"><span data-stu-id="eabf0-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="eabf0-117">{Атрибут name} Атрибут</span><span class="sxs-lookup"><span data-stu-id="eabf0-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="eabf0-118">Значение</span><span class="sxs-lookup"><span data-stu-id="eabf0-118">Value</span></span>|<span data-ttu-id="eabf0-119">Описание</span><span class="sxs-lookup"><span data-stu-id="eabf0-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eabf0-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="eabf0-120">genericUriParserOptions</span></span>|<span data-ttu-id="eabf0-121">Параметры средства синтаксического анализа для этой схемы.</span><span class="sxs-lookup"><span data-stu-id="eabf0-121">The parser options for this scheme.</span></span> <span data-ttu-id="eabf0-122">Поддерживается только значение genericUriParserOptions = «DontUnescapePathDotsAndSlashes».</span><span class="sxs-lookup"><span data-stu-id="eabf0-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eabf0-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eabf0-123">Child Elements</span></span>  
 <span data-ttu-id="eabf0-124">Нет</span><span class="sxs-lookup"><span data-stu-id="eabf0-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eabf0-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eabf0-125">Parent Elements</span></span>  
  
|<span data-ttu-id="eabf0-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="eabf0-126">Element</span></span>|<span data-ttu-id="eabf0-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="eabf0-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eabf0-128">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="eabf0-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="eabf0-129">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="eabf0-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eabf0-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="eabf0-130">Remarks</span></span>  
 <span data-ttu-id="eabf0-131">По умолчанию <xref:System.Uri?displayProperty=nameWithType> знаком процента Отмена переходов класс разделители пути до выполнения сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="eabf0-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="eabf0-132">Это было реализовано в качестве механизма защиты от атак, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eabf0-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="eabf0-133">Если этот URI передается вниз, чтобы модули не обрабатывает процентов символы в кодировке неправильно, это может привести в следующей команде, выполняемой на сервере:</span><span class="sxs-lookup"><span data-stu-id="eabf0-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="eabf0-134">По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути Отмена переходов, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="eabf0-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="eabf0-135">Результат передачи вредоносных URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:</span><span class="sxs-lookup"><span data-stu-id="eabf0-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="eabf0-136">Можно изменить это поведение по умолчанию для не разделители отмены escape процента закодированный путь, с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="eabf0-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="eabf0-137">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="eabf0-137">Configuration Files</span></span>  
 <span data-ttu-id="eabf0-138">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="eabf0-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eabf0-139">Пример</span><span class="sxs-lookup"><span data-stu-id="eabf0-139">Example</span></span>  
 <span data-ttu-id="eabf0-140">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="eabf0-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eabf0-141">См. также</span><span class="sxs-lookup"><span data-stu-id="eabf0-141">See also</span></span>
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="eabf0-142">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="eabf0-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
