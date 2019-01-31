---
title: Элемент <add> для schemeSettings (Параметры URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 672d279f35db64bec7f5b26bd1930d7048c406f1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55279592"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="7ec79-102">\<Добавить > элемент для schemeSettings (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="7ec79-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="7ec79-103">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="7ec79-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="7ec79-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7ec79-104">\<configuration></span></span>  
<span data-ttu-id="7ec79-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="7ec79-105">\<uri></span></span>  
<span data-ttu-id="7ec79-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="7ec79-106">\<schemeSettings></span></span>  
<span data-ttu-id="7ec79-107">\<add></span><span class="sxs-lookup"><span data-stu-id="7ec79-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec79-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7ec79-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7ec79-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7ec79-109">Attributes and Elements</span></span>  
 <span data-ttu-id="7ec79-110">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7ec79-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7ec79-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7ec79-111">Attributes</span></span>  
  
|<span data-ttu-id="7ec79-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7ec79-112">Attribute</span></span>|<span data-ttu-id="7ec79-113">Описание</span><span class="sxs-lookup"><span data-stu-id="7ec79-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7ec79-114">имя</span><span class="sxs-lookup"><span data-stu-id="7ec79-114">name</span></span>|<span data-ttu-id="7ec79-115">Имя схемы, к которому применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="7ec79-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="7ec79-116">Только поддерживаемые значения: имя = «http» и имя = «https».</span><span class="sxs-lookup"><span data-stu-id="7ec79-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="7ec79-117">{Атрибут name} Атрибут</span><span class="sxs-lookup"><span data-stu-id="7ec79-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="7ec79-118">Значение</span><span class="sxs-lookup"><span data-stu-id="7ec79-118">Value</span></span>|<span data-ttu-id="7ec79-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="7ec79-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7ec79-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="7ec79-120">genericUriParserOptions</span></span>|<span data-ttu-id="7ec79-121">Параметры средства синтаксического анализа для этой схемы.</span><span class="sxs-lookup"><span data-stu-id="7ec79-121">The parser options for this scheme.</span></span> <span data-ttu-id="7ec79-122">Поддерживается только значение genericUriParserOptions = «DontUnescapePathDotsAndSlashes».</span><span class="sxs-lookup"><span data-stu-id="7ec79-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7ec79-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7ec79-123">Child Elements</span></span>  
 <span data-ttu-id="7ec79-124">Нет</span><span class="sxs-lookup"><span data-stu-id="7ec79-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7ec79-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7ec79-125">Parent Elements</span></span>  
  
|<span data-ttu-id="7ec79-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="7ec79-126">Element</span></span>|<span data-ttu-id="7ec79-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="7ec79-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7ec79-128">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="7ec79-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="7ec79-129">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="7ec79-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ec79-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ec79-130">Remarks</span></span>  
 <span data-ttu-id="7ec79-131">По умолчанию <xref:System.Uri?displayProperty=nameWithType> знаком процента Отмена переходов класс разделители пути до выполнения сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="7ec79-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="7ec79-132">Это было реализовано в качестве механизма защиты от атак, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="7ec79-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7ec79-133">Если этот URI передается вниз, чтобы модули не обрабатывает процентов символы в кодировке неправильно, это может привести в следующей команде, выполняемой на сервере:</span><span class="sxs-lookup"><span data-stu-id="7ec79-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="7ec79-134">По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути Отмена переходов, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="7ec79-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="7ec79-135">Результат передачи вредоносных URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:</span><span class="sxs-lookup"><span data-stu-id="7ec79-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="7ec79-136">Можно изменить это поведение по умолчанию для не разделители отмены escape процента закодированный путь, с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="7ec79-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7ec79-137">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="7ec79-137">Configuration Files</span></span>  
 <span data-ttu-id="7ec79-138">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="7ec79-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ec79-139">Пример</span><span class="sxs-lookup"><span data-stu-id="7ec79-139">Example</span></span>  
 <span data-ttu-id="7ec79-140">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="7ec79-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ec79-141">См. также</span><span class="sxs-lookup"><span data-stu-id="7ec79-141">See also</span></span>
- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="7ec79-142">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="7ec79-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
