---
title: Элемент <add> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: efd52557ea8b617a39e685ff8ad69bab01322a7a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699598"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="675ff-102">Элемент > @no__t 0add для schemeSettings (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="675ff-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="675ff-103">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="675ff-103">Adds a scheme setting for a scheme name.</span></span>  
  
[<span data-ttu-id="675ff-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="675ff-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="675ff-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="675ff-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="675ff-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="675ff-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>  
<span data-ttu-id="675ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="675ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="675ff-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="675ff-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="675ff-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="675ff-109">Attributes and Elements</span></span>  
 <span data-ttu-id="675ff-110">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="675ff-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="675ff-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="675ff-111">Attributes</span></span>  
  
|<span data-ttu-id="675ff-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="675ff-112">Attribute</span></span>|<span data-ttu-id="675ff-113">Описание</span><span class="sxs-lookup"><span data-stu-id="675ff-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="675ff-114">имя</span><span class="sxs-lookup"><span data-stu-id="675ff-114">name</span></span>|<span data-ttu-id="675ff-115">Имя схемы, к которой применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="675ff-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="675ff-116">Поддерживаются только значения Name = "http" и Name = "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="675ff-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="675ff-117">{Имя атрибута} Версию</span><span class="sxs-lookup"><span data-stu-id="675ff-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="675ff-118">Значение</span><span class="sxs-lookup"><span data-stu-id="675ff-118">Value</span></span>|<span data-ttu-id="675ff-119">Описание</span><span class="sxs-lookup"><span data-stu-id="675ff-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="675ff-120">женерикурипарсероптионс</span><span class="sxs-lookup"><span data-stu-id="675ff-120">genericUriParserOptions</span></span>|<span data-ttu-id="675ff-121">Параметры средства синтаксического анализа для этой схемы.</span><span class="sxs-lookup"><span data-stu-id="675ff-121">The parser options for this scheme.</span></span> <span data-ttu-id="675ff-122">Единственное поддерживаемое значение — Женерикурипарсероптионс = "Донтунескапепасдотсандслашес".</span><span class="sxs-lookup"><span data-stu-id="675ff-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="675ff-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="675ff-123">Child Elements</span></span>  
 <span data-ttu-id="675ff-124">None</span><span class="sxs-lookup"><span data-stu-id="675ff-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="675ff-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="675ff-125">Parent Elements</span></span>  
  
|<span data-ttu-id="675ff-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="675ff-126">Element</span></span>|<span data-ttu-id="675ff-127">Описание</span><span class="sxs-lookup"><span data-stu-id="675ff-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="675ff-128">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="675ff-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="675ff-129">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="675ff-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="675ff-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="675ff-130">Remarks</span></span>  
 <span data-ttu-id="675ff-131">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах, закодированные разделителями, перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="675ff-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="675ff-132">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="675ff-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="675ff-133">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="675ff-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="675ff-134">По этой причине класс <xref:System.Uri?displayProperty=nameWithType> сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="675ff-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="675ff-135">Результат передачи вредоносного URL-адреса выше в конструктор класса <xref:System.Uri?displayProperty=nameWithType> приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="675ff-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="675ff-136">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="675ff-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="675ff-137">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="675ff-137">Configuration Files</span></span>  
 <span data-ttu-id="675ff-138">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="675ff-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="675ff-139">Пример</span><span class="sxs-lookup"><span data-stu-id="675ff-139">Example</span></span>  
 <span data-ttu-id="675ff-140">В следующем примере показана конфигурация, используемая классом <xref:System.Uri> для поддержки не экранирования разделителей пути в кодировке% для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="675ff-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="675ff-141">См. также</span><span class="sxs-lookup"><span data-stu-id="675ff-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="675ff-142">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="675ff-142">Network Settings Schema</span></span>](index.md)
