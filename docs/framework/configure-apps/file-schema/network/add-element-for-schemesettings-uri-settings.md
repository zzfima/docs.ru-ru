---
title: Элемент <add> для schemeSettings (параметры URI)
ms.date: 03/30/2017
ms.assetid: 594a7b3b-af23-4cfa-b616-0b2dddb1a705
ms.openlocfilehash: ed40098e8d4c2d1298771e67a618b8d04f59c912
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087719"
---
# <a name="add-element-for-schemesettings-uri-settings"></a><span data-ttu-id="8e9e3-102">\<добавить элемент > для schemeSettings (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="8e9e3-102">\<add> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="8e9e3-103">Добавляет параметр схемы для имени схемы.</span><span class="sxs-lookup"><span data-stu-id="8e9e3-103">Adds a scheme setting for a scheme name.</span></span>  

<span data-ttu-id="8e9e3-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8e9e3-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="8e9e3-105">&nbsp;&nbsp;[ **\<> uri**](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8e9e3-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>\
<span data-ttu-id="8e9e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<schemeSettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8e9e3-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>\
<span data-ttu-id="8e9e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**</span><span class="sxs-lookup"><span data-stu-id="8e9e3-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8e9e3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e9e3-108">Syntax</span></span>  
  
```xml  
<add
  name="http|https"
  genericUriParserOptions="DontUnescapePathDotsAndSlashes"
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e9e3-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8e9e3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8e9e3-110">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8e9e3-110">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e9e3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e9e3-111">Attributes</span></span>  
  
|<span data-ttu-id="8e9e3-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8e9e3-112">Attribute</span></span>|<span data-ttu-id="8e9e3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8e9e3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e9e3-114">имя</span><span class="sxs-lookup"><span data-stu-id="8e9e3-114">name</span></span>|<span data-ttu-id="8e9e3-115">Имя схемы, к которой применяется этот параметр.</span><span class="sxs-lookup"><span data-stu-id="8e9e3-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="8e9e3-116">Поддерживаются только значения Name = "http" и Name = "HTTPS".</span><span class="sxs-lookup"><span data-stu-id="8e9e3-116">The only supported values are name="http" and name="https".</span></span>|  
  
## <a name="attribute-name-attribute"></a><span data-ttu-id="8e9e3-117">{Имя атрибута} Версию</span><span class="sxs-lookup"><span data-stu-id="8e9e3-117">{Attribute name} Attribute</span></span>  
  
|<span data-ttu-id="8e9e3-118">значения</span><span class="sxs-lookup"><span data-stu-id="8e9e3-118">Value</span></span>|<span data-ttu-id="8e9e3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8e9e3-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8e9e3-120">женерикурипарсероптионс</span><span class="sxs-lookup"><span data-stu-id="8e9e3-120">genericUriParserOptions</span></span>|<span data-ttu-id="8e9e3-121">Параметры средства синтаксического анализа для этой схемы.</span><span class="sxs-lookup"><span data-stu-id="8e9e3-121">The parser options for this scheme.</span></span> <span data-ttu-id="8e9e3-122">Единственное поддерживаемое значение — Женерикурипарсероптионс = "Донтунескапепасдотсандслашес".</span><span class="sxs-lookup"><span data-stu-id="8e9e3-122">The only supported value is genericUriParserOptions= "DontUnescapePathDotsAndSlashes".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e9e3-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8e9e3-123">Child Elements</span></span>  
 <span data-ttu-id="8e9e3-124">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="8e9e3-124">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e9e3-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8e9e3-125">Parent Elements</span></span>  
  
|<span data-ttu-id="8e9e3-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e9e3-126">Element</span></span>|<span data-ttu-id="8e9e3-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8e9e3-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e9e3-128">Элемент \<schemeSettings> (параметры URI)</span><span class="sxs-lookup"><span data-stu-id="8e9e3-128">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="8e9e3-129">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="8e9e3-129">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8e9e3-130">Заметки</span><span class="sxs-lookup"><span data-stu-id="8e9e3-130">Remarks</span></span>  
 <span data-ttu-id="8e9e3-131">По умолчанию класс <xref:System.Uri?displayProperty=nameWithType> отменяет escape-символы в процентах от разделителей закодированного пути перед выполнением сжатия пути.</span><span class="sxs-lookup"><span data-stu-id="8e9e3-131">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="8e9e3-132">Это было реализовано в качестве механизма безопасности для атак, подобных следующим:</span><span class="sxs-lookup"><span data-stu-id="8e9e3-132">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="8e9e3-133">Если этот URI передается в модули, которые неправильно обрабатывают закодированные символы процента, это может привести к выполнению следующей команды на сервере:</span><span class="sxs-lookup"><span data-stu-id="8e9e3-133">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="8e9e3-134">По этой причине <xref:System.Uri?displayProperty=nameWithType> класс сначала отменяет escape-разделители путей, а затем применяет сжатие пути.</span><span class="sxs-lookup"><span data-stu-id="8e9e3-134">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="8e9e3-135">Результат передачи вредоносного URL-адреса выше в <xref:System.Uri?displayProperty=nameWithType> конструктор класса приводит к следующему URI:</span><span class="sxs-lookup"><span data-stu-id="8e9e3-135">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="8e9e3-136">Это поведение по умолчанию можно изменить, чтобы не отменять escape-символы в процентах с помощью параметра конфигурации schemeSettings для определенной схемы.</span><span class="sxs-lookup"><span data-stu-id="8e9e3-136">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8e9e3-137">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="8e9e3-137">Configuration Files</span></span>  
 <span data-ttu-id="8e9e3-138">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="8e9e3-138">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e9e3-139">Пример</span><span class="sxs-lookup"><span data-stu-id="8e9e3-139">Example</span></span>  
 <span data-ttu-id="8e9e3-140">В следующем примере показана конфигурация, используемая классом <xref:System.Uri> для поддержки не экранирования разделителей пути в кодировке% для схемы HTTP.</span><span class="sxs-lookup"><span data-stu-id="8e9e3-140">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8e9e3-141">См. также</span><span class="sxs-lookup"><span data-stu-id="8e9e3-141">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="8e9e3-142">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="8e9e3-142">Network Settings Schema</span></span>](index.md)
