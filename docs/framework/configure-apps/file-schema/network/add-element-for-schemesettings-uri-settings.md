---
title: Элемент <add> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: 027c7aaffea7950739f532309255d77afa031ada
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659544"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="227cc-102">\<Добавление элемента > для schemeSettings (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="227cc-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="227cc-103">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="227cc-103">Adds a scheme setting for a scheme name.</span></span>  
  
 <span data-ttu-id="227cc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="227cc-104">\<configuration></span></span>  
<span data-ttu-id="227cc-105">\<> URI</span><span class="sxs-lookup"><span data-stu-id="227cc-105">\<uri></span></span>  
<span data-ttu-id="227cc-106">\<schemeSettings ></span><span class="sxs-lookup"><span data-stu-id="227cc-106">\<schemeSettings></span></span>  
<span data-ttu-id="227cc-107">\<add></span><span class="sxs-lookup"><span data-stu-id="227cc-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="227cc-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="227cc-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="227cc-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="227cc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="227cc-110">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="227cc-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="227cc-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="227cc-111">Attributes</span></span>  
  
|<span data-ttu-id="227cc-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="227cc-112">Attribute</span></span>|<span data-ttu-id="227cc-113">Описание</span><span class="sxs-lookup"><span data-stu-id="227cc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="227cc-114">имя</span><span class="sxs-lookup"><span data-stu-id="227cc-114">name</span></span>|<span data-ttu-id="227cc-115">Имя схемы, к которой применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="227cc-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="227cc-116">Поддерживаются только значения Name = "http" и Name = "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="227cc-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="227cc-117">{Имя атрибута} Версию</span><span class="sxs-lookup"><span data-stu-id="227cc-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="227cc-118">Значение</span><span class="sxs-lookup"><span data-stu-id="227cc-118">Value</span></span>|<span data-ttu-id="227cc-119">Описание</span><span class="sxs-lookup"><span data-stu-id="227cc-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="227cc-120">женерикурипарсероптионс</span><span class="sxs-lookup"><span data-stu-id="227cc-120">genericUriParserOptions</span></span>|<span data-ttu-id="227cc-121">Параметры средства синтаксического анализа для этой схемы.</span><span class="sxs-lookup"><span data-stu-id="227cc-121">The parser options for this scheme.</span></span> <span data-ttu-id="227cc-122">Единственное поддерживаемое значение — Женерикурипарсероптионс = "Донтунескапепасдотсандслашес".</span><span class="sxs-lookup"><span data-stu-id="227cc-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="227cc-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="227cc-123">Child Elements</span></span>  
 <span data-ttu-id="227cc-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="227cc-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="227cc-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="227cc-125">Parent Elements</span></span>  
  
|<span data-ttu-id="227cc-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="227cc-126">Element</span></span>|<span data-ttu-id="227cc-127">Описание</span><span class="sxs-lookup"><span data-stu-id="227cc-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="227cc-128">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="227cc-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="227cc-129">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="227cc-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="227cc-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="227cc-130">Remarks</span></span>  
 <span data-ttu-id="227cc-131">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="227cc-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="227cc-132">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="227cc-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="227cc-133">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="227cc-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="227cc-134">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="227cc-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="227cc-135">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="227cc-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="227cc-136">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="227cc-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="227cc-137">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="227cc-137">Configuration Files</span></span>  
 <span data-ttu-id="227cc-138">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="227cc-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="227cc-139">Пример</span><span class="sxs-lookup"><span data-stu-id="227cc-139">Example</span></span>  
 <span data-ttu-id="227cc-140">В следующем примере показана конфигурация, используемая <xref:System.Uri> классом для поддержки неэкранированных разделителей пути в кодировке% для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="227cc-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="227cc-141">См. также</span><span class="sxs-lookup"><span data-stu-id="227cc-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="227cc-142">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="227cc-142">Network Settings Schema</span></span>](index.md)
