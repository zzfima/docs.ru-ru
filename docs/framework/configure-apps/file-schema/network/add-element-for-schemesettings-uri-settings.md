---
title: Элемент <add> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: e7606a1185d406384a926ca4dcb7c42586461574
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139936"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="61814-102">\<Добавить > элемент для schemeSettings (параметры Uri)</span><span class="sxs-lookup"><span data-stu-id="61814-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="61814-103">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="61814-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="61814-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="61814-104">\<configuration></span></span>  
<span data-ttu-id="61814-105">\<URI ></span><span class="sxs-lookup"><span data-stu-id="61814-105">\<uri></span></span>  
<span data-ttu-id="61814-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="61814-106">\<schemeSettings></span></span>  
<span data-ttu-id="61814-107">\<add></span><span class="sxs-lookup"><span data-stu-id="61814-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61814-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61814-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="61814-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="61814-109">Attributes and Elements</span></span>  
 <span data-ttu-id="61814-110">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="61814-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="61814-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="61814-111">Attributes</span></span>  
  
|<span data-ttu-id="61814-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="61814-112">Attribute</span></span>|<span data-ttu-id="61814-113">Описание</span><span class="sxs-lookup"><span data-stu-id="61814-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="61814-114">имя</span><span class="sxs-lookup"><span data-stu-id="61814-114">name</span></span>|<span data-ttu-id="61814-115">Имя схемы, к которому применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="61814-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="61814-116">Только поддерживаемые значения: имя = «http» и имя = «https».</span><span class="sxs-lookup"><span data-stu-id="61814-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="61814-117">{Атрибут name} Атрибут</span><span class="sxs-lookup"><span data-stu-id="61814-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="61814-118">Значение</span><span class="sxs-lookup"><span data-stu-id="61814-118">Value</span></span>|<span data-ttu-id="61814-119">Описание</span><span class="sxs-lookup"><span data-stu-id="61814-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="61814-120">genericUriParserOptions</span><span class="sxs-lookup"><span data-stu-id="61814-120">genericUriParserOptions</span></span>|<span data-ttu-id="61814-121">Параметры средства синтаксического анализа для этой схемы.</span><span class="sxs-lookup"><span data-stu-id="61814-121">The parser options for this scheme.</span></span> <span data-ttu-id="61814-122">Поддерживается только значение genericUriParserOptions = «DontUnescapePathDotsAndSlashes».</span><span class="sxs-lookup"><span data-stu-id="61814-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="61814-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="61814-123">Child Elements</span></span>  
 <span data-ttu-id="61814-124">Нет</span><span class="sxs-lookup"><span data-stu-id="61814-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="61814-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="61814-125">Parent Elements</span></span>  
  
|<span data-ttu-id="61814-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="61814-126">Element</span></span>|<span data-ttu-id="61814-127">Описание</span><span class="sxs-lookup"><span data-stu-id="61814-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="61814-128">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="61814-128">\<schemeSettings> Element (Uri Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|<span data-ttu-id="61814-129">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="61814-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61814-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="61814-130">Remarks</span></span>  
 <span data-ttu-id="61814-131">По умолчанию <xref:System.Uri?displayProperty=nameWithType> знаком процента Отмена переходов класс разделители пути до выполнения сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="61814-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="61814-132">Это было реализовано в качестве механизма защиты от атак, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="61814-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="61814-133">Если этот URI передается вниз, чтобы модули не обрабатывает процентов символы в кодировке неправильно, это может привести в следующей команде, выполняемой на сервере:</span><span class="sxs-lookup"><span data-stu-id="61814-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="61814-134">По этой причине <xref:System.Uri?displayProperty=nameWithType> класса первый разделители пути Отмена переходов, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="61814-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="61814-135">Результат передачи вредоносных URL-адрес выше <xref:System.Uri?displayProperty=nameWithType> класса конструктор результаты в следующий URI:</span><span class="sxs-lookup"><span data-stu-id="61814-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="61814-136">Можно изменить это поведение по умолчанию для не разделители отмены escape процента закодированный путь, с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="61814-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="61814-137">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="61814-137">Configuration Files</span></span>  
 <span data-ttu-id="61814-138">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="61814-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="61814-139">Пример</span><span class="sxs-lookup"><span data-stu-id="61814-139">Example</span></span>  
 <span data-ttu-id="61814-140">В следующем примере показано конфигурацию, используемую <xref:System.Uri> класс для поддержки не экранирования разделителей закодированные пути для схемы http.</span><span class="sxs-lookup"><span data-stu-id="61814-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="61814-141">См. также</span><span class="sxs-lookup"><span data-stu-id="61814-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="61814-142">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="61814-142">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
