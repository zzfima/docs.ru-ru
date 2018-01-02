---
title: "&lt;Добавить&gt; элемент для schemeSettings (параметры Uri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2d617e78231bd0b9f4e332c4b7fbe58b78598868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-element-for-schemesettings-uri-settings"></a><span data-ttu-id="95a43-102">&lt;Добавить&gt; элемент для schemeSettings (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="95a43-102">&lt;add&gt; Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="95a43-103">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="95a43-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="95a43-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="95a43-104">\<configuration></span></span>  
<span data-ttu-id="95a43-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="95a43-105">\<uri></span></span>  
<span data-ttu-id="95a43-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="95a43-106">\<schemeSettings></span></span>  
<span data-ttu-id="95a43-107">\<add></span><span class="sxs-lookup"><span data-stu-id="95a43-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95a43-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95a43-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95a43-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="95a43-109">Attributes and Elements</span></span>  
 <span data-ttu-id="95a43-110">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="95a43-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95a43-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="95a43-111">Attributes</span></span>  
  
|<span data-ttu-id="95a43-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="95a43-112">Attribute</span></span>|<span data-ttu-id="95a43-113">Описание</span><span class="sxs-lookup"><span data-stu-id="95a43-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95a43-114">имя</span><span class="sxs-lookup"><span data-stu-id="95a43-114">name</span></span>|<span data-ttu-id="95a43-115">Имя схемы, к которому применяется эта политика.</span><span class="sxs-lookup"><span data-stu-id="95a43-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="95a43-116">Только поддерживаемые значения: имя = «http» и имя = «https».</span><span class="sxs-lookup"><span data-stu-id="95a43-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="95a43-117">{Имя_атрибута} Атрибут</span><span class="sxs-lookup"><span data-stu-id="95a43-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="95a43-118">Значение</span><span class="sxs-lookup"><span data-stu-id="95a43-118">Value</span></span>|<span data-ttu-id="95a43-119">Описание</span><span class="sxs-lookup"><span data-stu-id="95a43-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="95a43-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="95a43-120">genericUriParserOptions</span></span>|<span data-ttu-id="95a43-121">Параметры средства синтаксического анализа для этой схемы.</span><span class="sxs-lookup"><span data-stu-id="95a43-121">The parser options for this scheme.</span></span> <span data-ttu-id="95a43-122">Поддерживается только значение genericUriParserOptions = «DontUnescapePathDotsAndSlashes».</span><span class="sxs-lookup"><span data-stu-id="95a43-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95a43-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="95a43-123">Child Elements</span></span>  
 <span data-ttu-id="95a43-124">Нет</span><span class="sxs-lookup"><span data-stu-id="95a43-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="95a43-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="95a43-125">Parent Elements</span></span>  
  
|<span data-ttu-id="95a43-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="95a43-126">Element</span></span>|<span data-ttu-id="95a43-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="95a43-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95a43-128">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="95a43-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="95a43-129">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="95a43-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95a43-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="95a43-130">Remarks</span></span>  
 <span data-ttu-id="95a43-131">По умолчанию <xref:System.Uri?displayProperty=nameWithType> процентов класс un-escape-символы в кодировке разделители пути до выполнения сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="95a43-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="95a43-132">Это было реализовано в качестве механизма защиты от атак на систему следующим образом:</span><span class="sxs-lookup"><span data-stu-id="95a43-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="95a43-133">Если этот URI передается вниз к модулям не обрабатывает процентов символы в кодировке правильно, это может привести в следующей команде, выполняемой на сервере:</span><span class="sxs-lookup"><span data-stu-id="95a43-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="95a43-134">По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути un-escape-последовательности, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="95a43-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="95a43-135">Результат передачи вредоносного URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:</span><span class="sxs-lookup"><span data-stu-id="95a43-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="95a43-136">Можно изменить это поведение по умолчанию для не разделители un escape-символ процента закодированный путь, с помощью параметра конфигурации schemeSettings для нужной раскладки.</span><span class="sxs-lookup"><span data-stu-id="95a43-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="95a43-137">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="95a43-137">Configuration Files</span></span>  
 <span data-ttu-id="95a43-138">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="95a43-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="95a43-139">Пример</span><span class="sxs-lookup"><span data-stu-id="95a43-139">Example</span></span>  
 <span data-ttu-id="95a43-140">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="95a43-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95a43-141">См. также</span><span class="sxs-lookup"><span data-stu-id="95a43-141">See Also</span></span>  
 <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>  
 <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection?displayProperty=nameWithType>  
 <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>  
 <xref:System.GenericUriParserOptions?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 [<span data-ttu-id="95a43-142">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="95a43-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
